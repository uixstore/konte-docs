# Elementor Knowledge Base


Elementor is a modern website builder that delivers high-end page designs and advanced capabilites. It is very flexible and is highly recommended by most of WordPress users. It is the yourest page builder on the market but quickly become the top popular website builder plugin of WordPress. The Konte theme start supporting it from version 2.0 and we strongly recommend people to use it if you are using this version or a newer version.

Before getting started with the Elementor, we strongly recommend you to get accustomed with its documentation.

- [Elementor Documentation](https://elementor.com/help/)
- [Support Forum](https://wordpress.org/support/plugin/elementor/)


## Basic Settings

By default, Elementor will load the Roboto as the font of all elmements. It may causes your website looks differently to the demo. You should deactivate the default font and default color scheme in **Elementor > Settings**.

![Elementor basic settings](_images/elementor--settings.png)


## Convert WPBakery site to Elementor?

With the flexible and useful features of Elementor, it is deserve to switch a WPBakery based site to Elementor. Even with the free version, Elementor has plenty of useful features and functionalities, while the WPBakery is a premium plugin. Besides, with the growing community of Elementor users, you will easy find the solution for your design/issues, while the author of WPBakery Page Builder seems is being spend less care for their plugin (Actually, they have develop a new builder plugin called "Visual Composer").

Now if you desided to convert your WPBakery based site to Elementor, you should know **there is no one-click solutions that can convert your website from WPBakery to Elementor**. You have to convert/rebuild your pages manually. But luckily, with the friendly user experience and rich options of Elementor, it is very easy.

1. Download and install Elementor plugin to your website.

1. Edit all pages whichs are built by WPBakery Page Builder and switch to Elementor editor. The Konte theme provide all widgets that the WPabkery Page Builder has, so you can easily rebuild your pages with Elementor widgets. You can also use predefined templates to rebuild pages to save your times if your page has a similar design with our demo pages.

1. Deactivate the WPBakery Page Builder and recheck all the page to ensure they are display properly without the old page builder. Actually, you can keep both plugins activated. But if you don't have plan to use the WPBakery Page Builder any more, you should deactivate it. Keep it activated may cause your website loads additional resources and it will impact to the site performance and speed.


## Enable Elemetor for Products


The Elementor builder is enabled for Posts and Pages by default. In order to enable it for WooCommerce products, you need to update the **Post Types** option in **Elementor > Settings**. You can see this option in the above screenshot.


## Editting the Shop page

While trying to edit the archive pages with Elementor, you may encounter an error message that indicates that the content area has not been found on the page. This error message usually appears in the following scenarios:

- When Trying to edit an archive page without creating an archive template / not editing through the archive template.

- When the website URL and home page URL are not the same


For example, you will receive an error message **"The content area has not been found on your page"** while trying to edit the shop page. The error occurs because when a page is set as the Shop page, WooCommerce plugin takes over and assigns the WooCommerce template to that page. This means that the page is no longer editable in Elementor, as the WooCommerce template takes priority over any other templates or page builders.

The reason for this is that the WooCommerce plugin has its own template hierarchy that determines how the WooCommerce shop page is displayed. The WooCommerce template takes priority over any other templates or page builders, including Elementor.

In summary, WooCommerce shop pages cannot currently be directly edited by Elementor. With Elementor Pro, however, you can create a new shop archive page to use in place of the default shop page. If you have the Elementor Pro on your website, you can refer to the documentation of [How to create a WooCommerce archive template](https://elementor.com/help/creating-a-woocommerce-archive-template/).

You can also refer to the documentation of [How to fix the error: “The content area has not been found on your page”?](https://elementor.com/help/the-content-area-was-not-found-error/) to learn more about the error and how to fix it.
