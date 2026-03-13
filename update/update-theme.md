# Update Konte Theme

There are 3 ways to update your theme: use Envato Market Plugin for automatic theme updates or manual update the theme via FTP or WordPress.

!> After updating the theme, all your content such as pages, options, images and posts will not be lost or erased by doing this. However, any customizations to the theme’s core files, such as PHP files, language files will be lost. So you need to the child theme to customize the theme and backup the lang file if you translated the theme.


## Method 1: Automatic Updates

The [Envato Market plugin](http://envato.github.io/wp-envato-market/) can install WordPress themes and plugins purchased from ThemeForest & CodeCanyon by connecting with the Envato Market API using a secure OAuth personal token. Once your themes & plugins are installed WordPress will periodically check for updates, so keeping your items up to date is as simple as a few clicks.

- **Step 1** – [Download WP Envato Market](http://envato.github.io/wp-envato-market/) plugin.

- **Step 2** – Install and Active the plugin. To install the plugin navigate to **Plugins > Add New** and click on the **Upload Plugin** button at the top of the page. Next browse for the _envato-market.zip_ file that you downloaded from Github. Then click the button to **Install Now** and when prompted click the **Activate Plugin** link.

- **Step 3** – If you translated the theme and the language files are in **themes/Konte/languages/**, you need to upload them to **wp-content/languages/themes/**. If not, after updating the theme, any customizations to the theme’s core files, such as PHP files, language files will be lost.

- **Step 4** – Click the **Envato Market** menu in WordPress and connect to the API.

- **Step 5** – Don’t forget to update the required plugins


?> If this instruction is not clear enough, we found a very detail tutorial to using this plugin [here](http://www.wpexplorer.com/envato-market-plugin-guide/).



## Method 2: Manual Update Via WordPress

- **Step 1** – Download the **Installable theme** from ThemeForest in the Download menu on ThemeForest. Then extract it to your computer.

- **Step 2** –  Go to **Appearance > Themes** and deactivate Konte theme. To deactivate, simply switch to a different theme. For example, the default WordPress Twenty Seventeen theme.

- **Step 3** – If you translated the theme and the language files are in **themes/Konte/languages/**, you need to upload them to **wp-content/languages/themes/**. If not, after updating the theme, any customizations to the theme’s core files, such as PHP files, language files will be lost.

- **Step 4** – After deactivating you can go ahead and delete it. To do this, hover over the theme thumbnail then click **Theme Details**. In the bottom right corner of the window, click the **Delete** button. All your content such as pages, options, images and posts will not be lost or erased by doing this. However, any customizations to the theme’s core files, such as PHP files will be lost. So you need to the child theme to customize the theme.

- **Step 5** – Upload, Install and Active the theme.

- **Step 6** – Don’t forget to update the required plugins



## Method 3: Manual Update Via FTP

- **Step 1** – Download the **Installable theme** from ThemeForest in the Download menu on ThemeForest. Then extract it to your computer.

- **Step 2** - Access your server via FTP or SFTP ([Filezilla](https://filezilla-project.org/) is a free recommended program)

- **Step 3** – If you translated the theme and the language files are in **themes/Konte/languages/**, you need to backup then upload them to **wp-content/languages/themes/**. If not, after updating the theme, any customizations to the theme’s core files, such as PHP files, language files will be lost.

- **Step 4** - Browse to _wp-content/themes/_

- **Step 5** - Delete the current theme folder (folder "Konte") then upload the new one downloaded in step 1.