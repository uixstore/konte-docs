# Popup

Popup is a powerful and flexible way help you get more newsletter subscribers, promote new products, deliver special offers to your customers. You can view the description of popup's options in the [Theme Options > General > Popup](theme-options/general.md?id=popup) section.


## Enable popup

To enable the newsletter popup, just navigate to **Appearance > Customize > General > Popup**. There is an option on the top of this section to enable the popup.


## Edit popup content

The option **Popup Content** in section **General > Popup** is used to handle the popup's content. In our demo site, we use this content for the newsletter popup:

```
<h3>Newsletter</h3>
<p>Stay Updated on all that's new
add noteworthy</p>
[mc4wp_form id="306"]
```

Please note the **id** of the newsletter shortcode can be different on your website. You can get the correct shortcode in **MailChimp for WP > Forms**.


## Customize the popup

Like many other parts of Konte, we prepared template files for the popup in **template-parts/popup** folder. Just copy the correct file to the same folder into your child theme to customize it.

## Close popup with a custom element

Sometimes, you want to add a link or a button inside your popup and want to close the popup when people click on it. From version 2.1.0, you can use this CSS class for popup content to do it:

`.close-popup-trigger`.

For example, you want to close the popup if a visitor click on to a link inside the popup, you can use this HTML:

```
<a class="close-popup-trigger">Close Popup</a>
```