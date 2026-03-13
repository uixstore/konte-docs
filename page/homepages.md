# Homepages


## Setup the homepage

Setting up your home page is the same as setting up any other regular pages, except that you need to specify in the settings which page will be your Main Home Page.

![Setting Reading](_images/settings--reading.png)

- **Step 1** – Navigate to **Settings > Reading** menu.

- **Step 2** – Select A Static Page option.

- **Step 3** – Choose the page you want as your home page from the Front Page dropdown list.

- **Step 4** – This is also the same spot you select the blog page as the Posts page.



## Rebuild a homepage

If you are using a builder that the theme supports like Elementor or WPBakery Page Builder, you can use the predefined template of a homepage to recreate that homepage without importing the demo data again.

You can read more about the predefined templates in these documents:

- [WPBakery Page Builder Templates](wpb-page-builder/templates.md)
- [Elementor Templates](elementor/templates.md)


However, with some special homepages, it requires additional configuarations which will be described in bellow sections.


## Home v1 - Main

This is a special page which list the latest Flex Posts with the ajax pagination. You don't need to use any page builder to build this homepage, just create a page using **Flex Posts** page template. Then you need to create flex posts to show them on the front page. A flex post may be a custom HTML/shortcode or simply link to a post.


## Home v7 - Categories

In this homepage layout, you will see a grid of elements above the list of products and the products filters. You may think it can be built with the page builder like Elementor or WPBakery Page Builder. But unfortunately, WooCommerce only support the product filters on the product catalog pages. So you're not able to build a custom page with a product grid and the search/filter fields along with it. Therefore we have to edit the shop page to add the addtional elements to the top. Then we set the shop page as the front page. So the shop page and the homepage are one now.

> [!ATTENTION] If you're using Elementor and want to edit the shop page, you need to unset the shop page in the WooCommerce Settings first. Elementor doesn't support to edit archive pages like the shop page or blog page. Once you finish editing the shop page, you can reasign it as the shop page again.


## Home v10 - Clean

This homepage is the same as the Home v7. You have to edit the shop page and then set it as the front page. In this page, we just display a slider on top of product listing.

> [!NOTE] With the shop page set as the frontpage, you may want to disable the shop page header. It can be disabled in **Appearance > Customize > Shop > Products Page Header**


## Home v13 - Instagram Shop

The content of this homepage is basisly very simple. The most complex part of this page is the Instagram shop is built by another service called GetSnappt. You can find more information about this service on its' page - [Snappt Visual Shopping](https://www.getsnapppt.com/visual-shopping)

In order to build your own instagram shop feed, you need to have an account on this website, then connect it with your Instagram account. We highly recommend you to check the documentation of this service before creating your own "Visual Shop" with it.

[Snappt Visual Shopping Documentation](https://help.snapppt.com/en/collections/186688-visual-shopping)

It is pretty easy to follow. Once you completed setting your Instagram Shop with this Visual Shopping, you will get a script code. Now you just to paste this code to your page and display the Instagram Shop on your website.

> [!TIP] By default, WordPress doesn't allow inserting JS scripts into the page content directly. You should use the **Raw HTML** element of WPBakery Page Builder or the **HTML** widget of Elementor to insert this script code into your page.