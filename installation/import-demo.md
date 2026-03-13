# Import Demo

The easiest way to import our demo content is to use our [Soo Demo Importer plugin](http://uix.store/plugins/soo-demo-importer.zip). Our importer will give you all pages and posts, several sample sliders, widgets, menus, theme options, assigned pages, and more. This is recommended to do on fresh installs. It will not replace content like posts, pages, portfolio, etc. And it will not delete current menus or sliders. It will, however, configure and use our demo menus, add sliders and replace theme options, reading settings and widgets.

## Before Importing

Before you import any of our available demos, please make sure to check the items listed below. All of these are important and will ensure that your demo import goes smoothly. In case something does go wrong with your demo import, please see the Troubleshooting section below.

- **Required Plugins**: Installed Konte's required plugins. Also make sure you’ve installed the recommended plugins.
- **Konte Addons**: Make sure you're using the latest version of this plugin.
- **System Status**: Navigate to **WooCommerce > System Status** and ensure your server meets all requirements.
- **Use Modern Browsers**: To ensure the importing process runs smoothly, you should use Chrome or Firefox. They are modern browsers and support new API of Javascript. Internet Exploer is an old browser, you shouldn't use it for importing demo content.


## Import Demo Data

Once you’ve checked all requirements and ensure everything is ok, it's time to begin:

**Step 1** - Downnload and install the plugin [Soo Demo Importer](http://uix.store/plugins/soo-demo-importer.zip). It is a required plugin if you want to enable the "One Click Import Demo" feature.

**Step 2** - Navigate to **Appearance > Import Demo Data**, select what demo you want to import and click **Import button**.

**Step 3** - It can take a few minutes to import everything. Please be patient and wait for it to complete. During the import process, you will see the message logs to know what is going on.


## Troubleshooting

1. **I don't see Import Demo Data menu**

	This feature requires you to install an additional plugin [Soo Demo Importer](http://uix.store/plugins/soo-demo-importer.zip). Please make sure you finised the **Step 1** above.

1. **I stuck at the importing screen**

	Mostly, this issue comes from the hosting configuration. Please place a ticket on our [support system](http://uix.ticksy.com/). Our developer will help you check it.

1. **Where are other sliders**

	When you select to import a demo, it will import the slider of the selected demo only. If you want to have other slider, you can found all exported slider in the theme package. It locates in folder `Konte Package/Demo Data/Sliders`. You can import them all to your site manually.

1. **Demo content duplicated**

	When you import our demo content, it can take several minutes depending on the speed of your server. Each time the button is clicked it will import the content, so if it is clicked twice it will import everything two times. There are two ways to get rid of duplicate content.

	**Method 1**: WP Reset Plugin – This plugin is the fastest way to get rid of content. However, it will remove all content from your database and leave the default theme activated. It does not remove plugins, but will deactivate them and remove all pages, posts, menus, sliders, widget data, theme options, etc. Basically it removes all the content that you imported from our theme. Only do this if you are able to start over. [Click Here To Download](https://wordpress.org/plugins/wordpress-reset/).

	**Method 2**: Manual Removal – This method will take longer and simply involves manually removing duplicate items. For example, go to the **Appearance > Menu** and delete and duplicate items one by one. Same thing for pages, post, sliders, etc.