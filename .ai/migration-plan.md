# Migration Plan: Docsify → Astro Starlight

> **Goal**: Migrate from client-side Docsify to SSR Astro Starlight for better SEO
> **Deployment**: GitHub Actions → VPS (auto-deploy on push to `main`)
> **Estimated Time**: 3-4 hours

---

## Phase 1: Project Setup

### 1.1 Initialize Starlight Project

```bash
# In the parent directory of current konte-docs
npm create astro@latest konte-docs-new -- --template starlight
cd konte-docs-new
```

When prompted:
- Install dependencies? **Yes**
- Initialize git repository? **No** (already have one)

### 1.2 Install Additional Dependencies

```bash
npm install
```

### 1.3 Project Structure Overview

After initialization, you'll have:

```
konte-docs-new/
├── public/                 # Static assets (images, favicon, etc.)
├── src/
│   ├── assets/            # CSS, images used in components
│   ├── content/
│   │   └── docs/          # Your markdown documentation files
│   ├── content.config.ts  # Content collection configuration
│   └── env.d.ts
├── astro.config.mjs       # Main configuration file
├── package.json
└── tsconfig.json
```

---

## Phase 2: Content Migration

### 2.1 Move Markdown Files

Move all `.md` files preserving folder structure:

```bash
# From the OLD konte-docs directory to NEW konte-docs-new
# Run these commands from the parent directory containing both folders

# Copy all markdown files preserving structure
rsync -avz --include='*/' --include='*.md' --exclude='*' \
  konte-docs/ konte-docs-new/src/content/docs/

# Exclude these files (they're Docsify-specific)
rm konte-docs-new/src/content/docs/_sidebar.md
rm konte-docs-new/src/content/docs/_navbar.md
rm konte-docs-new/src/content/docs/README.md
rm konte-docs-new/src/content/docs/index.html
```

### 2.2 Move Images

```bash
# Move _images folder to public/
cp -r konte-docs/_images konte-docs-new/public/images
```

### 2.3 Add Frontmatter to All Markdown Files

Each markdown file needs frontmatter. Create a script to add it:

```bash
#!/bin/bash
# add-frontmatter.sh - Run from src/content/docs/ directory

find . -name "*.md" -type f | while read -r file; do
  # Check if file already has frontmatter
  if ! head -1 "$file" | grep -q "^---$"; then
    # Extract filename without extension for title
    filename=$(basename "$file" .md)
    # Convert kebab-case to Title Case
    title=$(echo "$filename" | sed 's/-/ /g' | sed 's/\b\(.\)/\u\1/g')
    
    # Add frontmatter
    temp_file=$(mktemp)
    echo "---" > "$temp_file"
    echo "title: \"$title\"" >> "$temp_file"
    echo "---" >> "$temp_file"
    echo "" >> "$temp_file"
    cat "$file" >> "$temp_file"
    mv "$temp_file" "$file"
  fi
done
```

**Or manually add frontmatter** to key files:

```yaml
---
title: Introduction
---
```

### 2.4 Update Internal Links

Starlight uses clean URLs without `.md` extension.

**Before (Docsify):**
```markdown
[Installation](installation/install-theme.md)
```

**After (Starlight):**
```markdown
[Installation](/installation/install-theme/)
```

Create a script to update links:

```bash
#!/bin/bash
# update-links.sh - Run from src/content/docs/ directory

find . -name "*.md" -type f | while read -r file; do
  # Replace .md links with clean URLs
  sed -i '' 's/\]\([^)]*\)\.md)/\]\1\//g' "$file"
done
```

### 2.5 Update Image Paths

**Before (Docsify):**
```markdown
![Screenshot](_images/screenshot.png)
```

**After (Starlight):**
```markdown
![Screenshot](/images/screenshot.png)
```

```bash
#!/bin/bash
# update-images.sh - Run from src/content/docs/ directory

find . -name "*.md" -type f | while read -r file; do
  # Update _images paths to /images/
  sed -i '' 's/(_images\//(/images\//g' "$file"
  sed -i '' 's/\](_images\//](/images\//g' "$file"
done
```

---

## Phase 3: Configuration

### 3.1 Configure `astro.config.mjs`

```javascript
import { defineConfig } from 'astro/config';
import starlight from '@astrojs/starlight';

export default defineConfig({
  site: 'https://docs.yourdomain.com', // Replace with your actual domain
  integrations: [
    starlight({
      title: 'Konte Documentation',
      logo: {
        src: './public/logo.svg', // Add your logo if needed
      },
      social: {
        // Add social links if needed
        // github: 'https://github.com/your-repo',
      },
      sidebar: [
        // Getting Started
        {
          label: 'Getting Started',
          items: [
            { label: 'Introduction', link: '/getting-started/introduction/' },
            { label: 'WordPress Information', link: '/getting-started/wordpress-information/' },
            { label: 'Theme Requirements', link: '/getting-started/requirements/' },
            { label: 'File Included', link: '/getting-started/file-included/' },
            { label: 'Theme License', link: '/getting-started/theme-license/' },
            { label: 'Plugins License', link: '/getting-started/plugins-license/' },
            { label: 'Theme Support', link: '/getting-started/support/' },
          ],
        },
        // Installation
        {
          label: 'Installation',
          items: [
            { label: 'Step 1 - Download Theme', link: '/installation/download-theme/' },
            { label: 'Step 2 - Install Theme', link: '/installation/install-theme/' },
            { label: 'Step 3 - Install Plugins', link: '/installation/install-plugins/' },
            { label: 'Step 4 - Config Image Sizes', link: '/installation/config-plugins/' },
            { label: 'Step 5 - Enable Portfolio Support', link: '/installation/enable-portfolio-support/' },
            { label: 'Step 6 - Import Demo', link: '/installation/import-demo/' },
          ],
        },
        // Theme Options
        {
          label: 'Theme Options',
          items: [
            { label: 'Customizer', link: '/theme-options/customizer/' },
            { label: 'General', link: '/theme-options/general/' },
            { label: 'Maintenance', link: '/theme-options/maintenance/' },
            { label: 'Layout', link: '/theme-options/layout/' },
            { label: 'Typography', link: '/theme-options/typhography/' },
            { label: 'Colors', link: '/theme-options/colors/' },
            { label: 'Menus', link: '/theme-options/menus/' },
            { label: 'Widgets', link: '/theme-options/widgets/' },
            { label: 'Additional CSS', link: '/theme-options/additional-css/' },
            { label: 'Header', link: '/theme-options/header/' },
            { label: 'Blog', link: '/theme-options/blog/' },
            { label: 'Page', link: '/theme-options/page/' },
            { label: 'Shop', link: '/theme-options/shop/' },
            { label: 'Portfolio', link: '/theme-options/portfolio/' },
            { label: 'Footer', link: '/theme-options/footer/' },
            { label: 'Mobile', link: '/theme-options/mobile/' },
          ],
        },
        // Elementor
        {
          label: 'Elementor',
          items: [
            { label: 'Knowledge Base', link: '/elementor/knowledge-base/' },
            { label: 'Templates', link: '/elementor/templates/' },
          ],
        },
        // WPBakery Page Builder
        {
          label: 'WPBakery Page Builder',
          items: [
            { label: 'Knowledge Base', link: '/wpb-page-builder/knowledge-base/' },
            { label: 'Enable for Products', link: '/wpb-page-builder/enable-for-products/' },
            { label: 'Templates', link: '/wpb-page-builder/templates/' },
          ],
        },
        // Header
        {
          label: 'Header',
          items: [
            { label: 'Topbar', link: '/header/topbar/' },
            { label: 'Header Layout', link: '/header/layout/' },
            { label: 'Header Builder', link: '/header/builder/' },
            { label: 'Logo', link: '/header/logo/' },
            { label: 'Menus', link: '/header/menus/' },
          ],
        },
        // Sliders
        {
          label: 'Sliders',
          items: [
            { label: 'Knowledge Base', link: '/slider/knowledge-base/' },
            { label: 'Exported Sliders', link: '/slider/exported-sliders/' },
            { label: 'More Sample Sliders', link: '/slider/sample-sliders/' },
            { label: 'Social Icons', link: '/slider/social-icons/' },
          ],
        },
        // Pages
        {
          label: 'Pages',
          items: [
            { label: 'Create A New Page', link: '/page/create-new-page/' },
            { label: 'Page Templates', link: '/page/page-templates/' },
            { label: 'Display Settings', link: '/page/display-settings/' },
            { label: 'Homepages', link: '/page/homepages/' },
          ],
        },
        // Shop
        {
          label: 'Shop',
          items: [
            { label: 'Setup WooCommerce', link: '/shop/setup-woocommerce/' },
            { label: 'Order Tracking Page', link: '/shop/order-tracking/' },
            { label: 'Account', link: '/shop/account/' },
            { label: 'Wishlist', link: '/shop/wishlist/' },
            { label: 'Currency', link: '/shop/currency/' },
            { label: 'Shop Display', link: '/shop/shop/' },
            { label: 'Product Page', link: '/shop/product/' },
            { label: 'Size Guide', link: '/shop/side-guide/' },
            { label: 'Variation Swatches', link: '/shop/variation-swatches/' },
          ],
        },
        // Portfolio
        {
          label: 'Portfolio',
          items: [
            { label: 'Enable Portfolio', link: '/portfolio/enable/' },
            { label: 'Manage Projects', link: '/portfolio/manage-projects/' },
            { label: 'Create Portfolio Page', link: '/portfolio/create-portfolio-page/' },
            { label: 'Change Portfolio Link', link: '/portfolio/change-permalink/' },
            { label: 'Portfolio Page Display', link: '/portfolio/portfolio-display/' },
            { label: 'Portfolio Header', link: '/portfolio/portfolio-header/' },
            { label: 'Project Page Display', link: '/portfolio/project-display/' },
          ],
        },
        // Footer
        {
          label: 'Footer',
          items: [
            { label: 'Footer Layout', link: '/footer/footer-layout/' },
            { label: 'Footer Extra Content', link: '/footer/footer-content/' },
            { label: 'Footer Widgets', link: '/footer/footer-widgets/' },
            { label: 'Footer Instagram', link: '/footer/footer-instagram/' },
            { label: 'Footer Main', link: '/footer/footer-main/' },
          ],
        },
        // Translation
        {
          label: 'Translation',
          items: [
            { label: 'Setup Language', link: '/translate/setup-language/' },
            { label: 'Translate Your Site', link: '/translate/translate-site/' },
            { label: 'Use Loco Translate', link: '/translate/loco-translate/' },
            { label: 'Use Poedit', link: '/translate/poedit/' },
            { label: 'Store Translation Files', link: '/translate/store-translations/' },
            { label: 'Multilingual', link: '/translate/multilingual/' },
          ],
        },
        // Customize Theme
        {
          label: 'Customize Theme',
          items: [
            { label: 'Child Theme', link: '/customize/child-theme/' },
            { label: 'Customize with Plugins', link: '/customize/customize-with-plugins/' },
            { label: 'Edit Texts', link: '/customize/edit-texts/' },
            { label: 'Add Custom Fonts', link: '/customize/add-custom-fonts/' },
          ],
        },
        // Other
        {
          label: 'Other',
          items: [
            { label: 'Preloader', link: '/misc/preloader/' },
            { label: 'Popup', link: '/misc/popup/' },
            { label: 'Instagram', link: '/misc/instagram/' },
            { label: 'Google Maps', link: '/misc/google-maps/' },
            { label: 'Site Speed', link: '/misc/site-speed/' },
          ],
        },
        // Updates
        {
          label: 'Updates',
          items: [
            { label: 'Update Theme', link: '/update/update-theme/' },
            { label: 'Update Plugins', link: '/update/update-plugins/' },
            { label: 'Changelog', link: '/update/changelog/' },
          ],
        },
      ],
    }),
  ],
});
```

### 3.2 Custom Styling

Create `src/assets/custom.css`:

```css
/* Image styling from original Docsify theme */
img {
  padding: 4px;
  border: 1px solid #ccc;
}

/* Image alignment classes */
@media (min-width: 600px) {
  img[src$="alignright"],
  .image-right {
    float: right;
    margin: 0 0 20px 20px;
    max-width: 33.33%;
  }

  img[src$="alignleft"],
  .image-left {
    float: left;
    margin: 0 20px 20px 0;
    max-width: 33.33%;
  }

  img[src$="alignrightfull"] {
    float: right;
    margin: 0 0 20px 20px;
  }

  img[src$="alignleft50"] {
    float: left;
    width: 46%;
    margin: 0 2% 2% 0;
  }

  img[src$="alignleft50"]:nth-child(2n) {
    clear: right;
    margin-right: 0;
  }
}

/* Main content max-width */
.sl-markdown-content {
  max-width: 900px;
  margin: 0 auto;
}

/* Clear floats for headings and paragraphs */
.sl-markdown-content h1,
.sl-markdown-content h2,
.sl-markdown-content h3,
.sl-markdown-content p {
  clear: both;
}

/* Image captions */
.sl-markdown-content img + em {
  text-align: center;
  display: block;
}
```

Update `astro.config.mjs` to include custom CSS:

```javascript
starlight({
  // ... existing config
  customCss: ['./src/assets/custom.css'],
})
```

### 3.3 Configure Content Collection

Update `src/content.config.ts`:

```typescript
import { defineCollection } from 'astro:content';
import { docsLoader } from '@astrojs/starlight/loaders';
import { docsSchema } from '@astrojs/starlight/schema';

export const collections = {
  docs: defineCollection({ loader: docsLoader(), schema: docsSchema() }),
};
```

---

## Phase 4: GitHub Actions Workflow

### 4.1 Create Workflow File

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to VPS

on:
  push:
    branches: [main]
  workflow_dispatch: # Allow manual trigger

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Build site
        run: npm run build

      - name: Deploy to VPS via SSH
        uses: appleboy/scp-action@v0.1.7
        with:
          host: ${{ secrets.VPS_HOST }}
          username: ${{ secrets.VPS_USER }}
          key: ${{ secrets.VPS_SSH_KEY }}
          port: ${{ secrets.VPS_PORT || 22 }}
          source: "dist/*"
          target: "/var/www/konte-docs/"
          strip_components: 1
          rm: true # Remove existing files before upload

      - name: Verify deployment
        uses: appleboy/ssh-action@v1.0.3
        with:
          host: ${{ secrets.VPS_HOST }}
          username: ${{ secrets.VPS_USER }}
          key: ${{ secrets.VPS_SSH_KEY }}
          port: ${{ secrets.VPS_PORT || 22 }}
          script: |
            echo "Deployment completed at $(date)"
            ls -la /var/www/konte-docs/
```

### 4.2 GitHub Secrets Setup

In your GitHub repository, go to **Settings → Secrets and variables → Actions** and add:

| Secret | Description | Example |
|--------|-------------|---------|
| `VPS_HOST` | Your VPS IP or domain | `192.168.1.100` or `docs.yourdomain.com` |
| `VPS_USER` | SSH username | `deploy` or `root` |
| `VPS_SSH_KEY` | SSH private key | `-----BEGIN OPENSSH PRIVATE KEY-----...` |
| `VPS_PORT` | SSH port (optional) | `22` (default) |

### 4.3 Generate SSH Key Pair

On your local machine:

```bash
ssh-keygen -t ed25519 -C "github-actions-deploy" -f ~/.ssh/github_actions_deploy
```

This creates:
- `~/.ssh/github_actions_deploy` (private key)
- `~/.ssh/github_actions_deploy.pub` (public key)

Add the **public key** to your VPS:

```bash
# On VPS
mkdir -p ~/.ssh
chmod 700 ~/.ssh
cat >> ~/.ssh/authorized_keys
# Paste the public key content, then Ctrl+D
chmod 600 ~/.ssh/authorized_keys
```

Add the **private key** to GitHub:

```bash
# Copy private key content
cat ~/.ssh/github_actions_deploy
```

Then paste into GitHub repo secrets as `VPS_SSH_KEY`.

---

## Phase 5: VPS Setup (One-time)

### 5.1 Create Deploy Directory

```bash
sudo mkdir -p /var/www/konte-docs
sudo chown -R $USER:$USER /var/www/konte-docs
chmod -R 755 /var/www/konte-docs
```

### 5.2 Install/Configure Nginx

If Nginx is not installed:

```bash
sudo apt update
sudo apt install nginx
```

Create site configuration:

```bash
sudo nano /etc/nginx/sites-available/konte-docs
```

Add configuration:

```nginx
server {
    listen 80;
    server_name docs.yourdomain.com; # Replace with your domain

    root /var/www/konte-docs;
    index index.html;

    # Gzip compression
    gzip on;
    gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;
    gzip_min_length 1000;

    # Cache static assets
    location ~* \.(js|css|png|jpg|jpeg|gif|ico|svg|woff|woff2|ttf|eot)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }

    location / {
        try_files $uri $uri/ =404;
    }

    # Security headers
    add_header X-Frame-Options "SAMEORIGIN" always;
    add_header X-Content-Type-Options "nosniff" always;
    add_header X-XSS-Protection "1; mode=block" always;
}
```

Enable the site:

```bash
sudo ln -s /etc/nginx/sites-available/konte-docs /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx
```

### 5.3 SSL with Let's Encrypt (Optional but Recommended)

```bash
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d docs.yourdomain.com
```

---

## Phase 6: Testing & Verification

### 6.1 Local Development Testing

```bash
npm run dev
```

Checklist:
- [ ] All pages render correctly
- [ ] Sidebar navigation works
- [ ] Search functionality works
- [ ] All images display properly
- [ ] Internal links work
- [ ] Responsive design works on mobile
- [ ] Custom CSS is applied

### 6.2 Build Testing

```bash
npm run build
npm run preview
```

Checklist:
- [ ] Build completes without errors
- [ ] No broken links in build output
- [ ] Preview works correctly

### 6.3 Deployment Testing

1. Commit and push to main:
```bash
git add .
git commit -m "Migrate to Astro Starlight"
git push origin main
```

2. Monitor GitHub Actions:
- Go to **Actions** tab in your repo
- Watch the deployment workflow
- Check for any errors

3. Verify live site:
- Visit `https://docs.yourdomain.com`
- Test all functionality
- Check page source to verify SSR HTML

---

## Migration Checklist

### Pre-Migration
- [ ] Backup current Docsify site
- [ ] Create new branch for migration
- [ ] Set up local development environment

### Phase 1: Project Setup
- [ ] Initialize Starlight project
- [ ] Install dependencies
- [ ] Verify project structure

### Phase 2: Content Migration
- [ ] Move markdown files to `src/content/docs/`
- [ ] Move images to `public/images/`
- [ ] Add frontmatter to all markdown files
- [ ] Update internal links (remove `.md` extensions)
- [ ] Update image paths
- [ ] Remove Docsify-specific files (`_sidebar.md`, `_navbar.md`, `index.html`)

### Phase 3: Configuration
- [ ] Configure `astro.config.mjs` with sidebar
- [ ] Add custom CSS
- [ ] Set site URL
- [ ] Configure content collection

### Phase 4: GitHub Actions
- [ ] Create `.github/workflows/deploy.yml`
- [ ] Generate SSH key pair
- [ ] Add public key to VPS
- [ ] Add private key to GitHub secrets
- [ ] Add VPS host, user, port to GitHub secrets

### Phase 5: VPS Setup
- [ ] Create deploy directory
- [ ] Configure Nginx
- [ ] Enable site in Nginx
- [ ] Set up SSL certificate (optional)
- [ ] Test Nginx configuration

### Phase 6: Testing
- [ ] Test locally with `npm run dev`
- [ ] Test build with `npm run build`
- [ ] Test preview with `npm run preview`
- [ ] Push to main branch
- [ ] Monitor GitHub Actions deployment
- [ ] Verify live site
- [ ] Test all pages and links
- [ ] Test search functionality
- [ ] Test responsive design

---

## Key Differences: Docsify vs Starlight

| Feature | Docsify | Astro Starlight |
|---------|---------|-----------------|
| Rendering | Client-side JavaScript | Server-side HTML (SSR) |
| SEO | Poor (JS-rendered) | Excellent (static HTML) |
| URLs | `#/path/to/page` | Clean `/path/to/page/` |
| Search | Plugin required | Built-in |
| Build Step | None | `npm run build` |
| Deployment | Static files | Static files |
| Navigation | Hash-based | Real page loads |
| Performance | Slower initial load | Fast, pre-rendered |

---

## Troubleshooting

### Build Errors
- Check for missing frontmatter in markdown files
- Verify all links are correct
- Ensure image paths are valid

### Deployment Issues
- Verify SSH key permissions on VPS (`chmod 600 ~/.ssh/authorized_keys`)
- Check GitHub Actions logs for errors
- Ensure VPS directory exists and has correct permissions

### Nginx Issues
- Check logs: `sudo tail -f /var/log/nginx/error.log`
- Test config: `sudo nginx -t`
- Reload: `sudo systemctl reload nginx`

### Missing Pages
- Verify markdown files are in `src/content/docs/`
- Check frontmatter has `title` field
- Ensure sidebar links match file paths

---

## Post-Migration

1. **Update DNS** (if needed) to point to VPS
2. **Set up monitoring** for uptime
3. **Configure backups** for the site
4. **Document the deployment process** for other developers
5. **Remove old Docsify files** after verifying everything works

---

## Quick Reference Commands

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build locally
npm run preview

# Deploy manually (if needed)
rsync -avz --delete dist/ user@your-vps:/var/www/konte-docs/
```

---

## Resources

- [Starlight Documentation](https://starlight.astro.build/)
- [Astro Documentation](https://docs.astro.build/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Nginx Documentation](https://nginx.org/en/docs/)
