# Topbar

You can control the site topbar in **Customize > Header > Topbar**. All options for it are described in the section [Theme Options > Header > Topbar](/theme-options/header.md?id=topbar)


## Enable Topbar

In order to enable the topbar on your website, please navigate to **Customize > Header > Topbar** and turn on the option **Topbar**.


## Change Background

At this moment, topbar only support to select from 2 background colors: dark or light. It is the option **Header > Topbar > Background**.

## Change Topbar Height

![Change topbar height](_images/header--topbar-height.png#alignright)

There is an option called **Height** in **Header > Topbar**. You can drag the slider to left or right to decrease/increase the topbar height. You can also use the left & right arrow on your keyboard to adjust the value of this option.


## Add Items to Topbar

![Add new topbar items](_images/header--topbar-add-new.png#alignright)

There are two sections of the topbar: **Left Items** section and **Right Items** section. You can see these two options for them in **Header > Topbar** panel. To add a new item to a section, you need:

1. Click the **Add New Item** button to add a new item.
1. Select the item type in from the dropdown.


## Arrange Topbar Items

It's very easy to change the order of topbar items. You just need to drag and drop items to the position you want.


## Remove an Item from Topbar.

In each topbar item, you will a **Remove** link. Just click this link to remove the item from topbar.


## Edit Topbar Menu

![Topbar menu](_images/header--topbar-menu.png#alignright)

- To have the topbar menu, please ensure you added the  **Topbar Menu** element into the topbar.
- Then navigate to **Customize > Menus > Mene Locations** and asign a menu for **Topbar Menu** location.


## Currency and Language

To have the currency and lanuage switchers on the topbar, you need to add an element to the topbar then select the element's type as **Currency Switcher** or **Language Switcher**. And please remember to have the required plugin for these switchers.

- The plugin [WPML](https://wpml.org) for the language switcher.
- The plugin [WooCommerce Currency Switcher](https://wordpress.org/plugins/woocommerce-currency-switcher/) for the currency switcher.


## Add Custom Content to Topbar

![Topbar menu](_images/header--topbar-custom-content.png#alignright)

Beside normal elements, Konte allows adding custom content (text, HTML, shortcodes) on the topbar. You just need to add an element to the topbar and select element's type as **Custom Text**. Then at the bottom of the Topbar options panel, you will see a textarea field **Custome Text** to enter custom content for the topbar. You can add a simple text for an important notification, or add HTML code for a more complex element (with a link for example), or add shortcodes.


## Add a Countdown to Topbar

You can use **Custom Text** element to display custom sale countdown notification to the topbar. This a sample code for it.

`The sale will ended in [konte_countdown type="inline" date="2019/03/28"]`