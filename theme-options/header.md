# Header

This panel contains sections which have options that helping you control your site header, like top bar, logo, header icons, header layout... In the [Header Section](header/layout.md), you will see more detailed guide to control your site header. At this writing, we only introduce to you the general purposes of sections in this panel.


## Topbar

![Customize Header Topbar](_images/customize-header--topbar.png#alignright)

This section contains options for controling the topbar, like turn it on/off, select topbar layout, set the content for it.

- **Topbar** - enable or disable the topbar.
- **Height** - set the topbar's height.
- **Background** - select the background color of topbar. There are 2 options to choose - Dark or Light.
- **Left Items** - add/remove items to/from the left section of the topbar. You can also reorder them.
- **Right Items** - add/remove items to/from the right section of the topbar. You can also reorder them.
- **Custom Content** - enter the custom content for the Text element.

> [!NOTE] It requires to install [WooCommerce Currency Switcher](https://wordpress.org/plugins/woocommerce-currency-switcher/) and [WPML](https://wpml.org/) plugins if you would like to have the currency & language swithcers.


## Header Layout

![Customize Header Layout](_images/customize-header--layout.png#alignright)

This section contains options to control the site header layout. You can chose to use one of pre-build header layout or select to build your own layout. That we say the site header of Konte is unlimited.

- **Present** - select either pre-build header or build your own.
- **Pre-build Header** - select a header layout which is built by Konte.
- **Sticky Header** - select the sticky header type or disable sticky header.


## Header Background

![Customize Header Layout](_images/customize-header--background.png#alignright)

This section contains options to control header background. You can select select from Dark, Light or Custom background color. With the custom background color, you will be able to select the header text color.

You can also select a diferent background color for blog and shop page.

> [!NOTE] On each individual page, you can override some setting about background color and text color with the help of [Display Settings](page/display-settings.md) meta box.



## Header Main & Bottom

![Customize Header Header](_images/customize-header--main.png#alignright)

Konte splits header into 2 sections: Header main and Header bottom. This section contains options for controling how these header sections display. You can add elements, remove elements or order them.

If you select to use a pre-build header layout, you will see the option of section height only.

- **Left Items** - manage header left elements.
- **Center Items** - manage header center elements.
- **Right Items** - manage header right elements.
- **Height** - change the height of each header section.

Konte supports follow elements on the site header: Logo, Primary menu, Secondary menu, Hamburger icon, Search icon, Cart icon, Wishlist icon and Account icon. Each of them has it own options which are placed in differtent sections.



## Logo

![Customize Header Logo](_images/customize-header--logo.png#alignright)

This section contains options for controling how your site logo. You can select either logo image or logo text and config them.

- **Logo Type** - select logo type either _Image_, _Text_ or _SVG_ code.
- **Logo Dimension** - this option is used to adjust the logo image/svg dimension.

If you select Logo Type as **Image**, you will see these options:

- **Logo** - upload your main logo image.
- **Logo Light** - upload your logo which is in light color. When you need this? If you select header background as transparent, you should prepare the main logo in dark color and upload this light version to make sure your logo display well in all situations.
- **Logo Dimension** - specify the width and height of your logo image. By default, you don't need to enter values for them. The logo will be display in nature dimension. But if you want the logo displays well on retina screens, you should prepare it in double dimension then enter these values as regular dimension. For example, your logo is 140x70, you should design it in 280x140. Then enter the value of width is 140px and height is 70px.

If you select Logo Type as **Text**, you will see these options:

- **Logo Text** - enter your branding here. It is usually your site name.
- **Logo Font** - select font's properties for you logo, like Font family, font size, font weight, text transform, letter spacing, etc.

If you select Logo Type as **SVG**, you will see these options:

- **Logo SVG** - paste SVG code of your logo here.
- **Logo Dimension** - you can use this option to adjust the SVG logo.




## Search


![Customize Header Search](_images/customize-header--search.png#alignright)

This section contains options of the search icon on header. You can select icon style, what the search form looking for, and manage quick links.

- **Style** - you can select the style of the search icon from icon + field, icon only (click to toggler search field) or icon only (click to open search modal).
- **Search for** - you can select what type of content you want to search for when using this modal. By default, it will search for products. You can select searching for products or post or everything.
- **Quick links** - turn on/off quick links section on the search form.
- **Links** - you will see this option if you enable **Quick Links** option. You can manage links (text and custom URL) with this option.



## Cart

![Customize Header Search](_images/customize-header--cart.png#alignright)

This section contains options to control the cart icon on site header.

- **Cart Icon Behaviour** - select to open the cart panel on side or redirect to the cart page when clicking on the cart icon.


## Account


![Customize Header Search](_images/customize-header--account.png#alignright)

This section contains options to control the account icon on site header.

- **Account Icon Behaviour** - select to open the account login panel on side or redirect to the My Account page when clicking on the "Sign In" text on header.



## Full-Screen Menu

![Customize Header Search](_images/customize-header--fullscreen_menu.png#alignright)

This section contains options to control the full screen menu. This screen will be open when you click on the hamburger menu icon.

- **Background** - upload background image of this full screen menu. This image will be displayed in half of this screen.
- **Show Logo** - select to show the logo on top of this screen.
- **Show Social Menu** - select to show the social icons in this screen. Konte manages these icons as a menu in **Appearance > Menus**. You can learn more about it in [Footer/Menu](footer/footer-socials.md).
- **Show Currency Switcher** - select to show the currency switcher. It requires you to install plugin [WooCommerce Currency Switcher](https://wordpress.org/plugins/woocommerce-currency-switcher/).
- **Show Language Switcher** - select to show the language switcher. It requires you to install plugin [WPML](https://wpml.org/).
- **Content Type** - select to the content type. By default, it show the "Ful Screen Menu" as the content of this screen, but you can chose to display the Off-Screen sidebar.
- **Open Sub-menu Behaviour** - select how to open sub-menus.
- **Toggle Animation** - select the animation when opening the this fullscreen menu.

