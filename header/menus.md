# Menus

Menus are the default part of any WordPress site. Konte supports custom WordPress menus, with multiple levels of dropdown support for the main menu. If you are new with WordPress, we recommend you take a look at this guide firstly - [WordPress Menu User Guide](https://codex.wordpress.org/WordPress_Menu_User_Guide).


## Menu Locations

In Konte theme, there are 8 menu locations:

![Menu locations](_images/header--menu-locations.png)

- **Primary Menu** - This is the main menu of your website.
- **Secondary Menu** - In case you choose header layout with the logo at center and 2 menus on sides, you need to assign both **Primary Menu** and **Secondary Menu** locations.
- **Topbar Menu** - This menu is displayed on the topbar if your topbar include it.
- **Full Screen Menu** - If your header layout has the humberger menu icon, a fullscreen will appear when you click on this icon. This menu is displayed inside this fullscreen.
- **Socials Menu** - This menu only displays social icons base on URLs you entered. You will see this menu on different pages, such as blog header, portfolio, homepage, etc.
- **Blog Header Menu** - If you enable the blog header and blog header menu, this menu will be used as the blog header menu.
- **Footer Menu** - This menu appear on your site footer.
- **Mobile Menu** - This is will be used when viewing on mobile devices. If this menu is not set, it will use __Primary Menu__. Why you need this? Because of the primary menu support mega menu on large screens, therefore you should create another menu for mobile. Of course, theme will remove all mega menu style if you still using the primary menu for mobile.


## Setup Mega Menu

Konte theme comes with a built-in Mega menu system. It means you don't need to purchase or install extra plugin for this feature. To setup mega menu, please go **Appearance > Menus** and select menu you want to edit. Please note you cannot setup mega menu in the Customizer at this moment.

A mega menu can ben enabled on every first level menu item. This image can show you what is menu item level:

![Menu levels](_images/menu-levels.png)


### Enable Mega Menu

Select a top level (Level 1) menu item that you want to setup mega menu for it. You will see a new **Settings** link added to every menu item. Click to that _Settings_ link, a new popup will show up. Please note with different menu item levels, different popups will appear. In this popup, you will see an option to enable the mega menu.


### Mega Menu Columns

![Menu settings](_images/mega-menu-settings.png)

In the popup, there are options helping you setup this mega menu item.

- Enable mega menu: select enable or disable mega menu for this menu item. By default, it is disabled.
- Container width: select the mega menu container width.

Bellow, you will see mega menu columns. They are menu items level 2 which are direct children of current menu item. You can change the width of each column right there by clicking to the arrow icons.


### Mega Menu Background

Just click to **Design** menu in the left side of popup, new options will appear and allow you to upload background image as well as select background properties.

![Mega menu background](_images/mega-menu-bg.png)


### Hide Column Label

Open the **Settings** popup of menu items level 2, you will see options to set the visiblity of column label.

![Mega menu column settings](_images/mega-menu-column-settings.png)

- **Visibility**: this option allows you to set the visibility of mega menu column label. It is visibile by default.
- **Disable link**: remove link from the mega menu column label.

### Column Background

Open the **Settings** popup of menu items level 2, you can see the tab **Design** on the left side. In this tab, you can upload the background image for a mega menu colum, or simply pick a background color.

![Mega menu column design](_images/mega-menu-column-design.png)

> [!TIP]
- You can use the **Margin** opton to pull a column to top and display over the main menu.
- You can also change the **left and right padding of a column** to make columns closer.

![Mega menu column offset](_images/mega-menu-column-offset.png)
![Mega menu column offset example](_images/mega-menu-column-offset-example.png)


### Custom Content

From menu items level 2 and bellow, you can set a custom HTML content for them. For example, you can hide the column lable then display a HTML/Shortcode of a banner image on the menu.

![Mega menu column offset example](_images/mega-menu-column-content.png)

> [!TIP] To build complex mega menu content, you can build your content inside a page with visual page builder then copy generated content here.