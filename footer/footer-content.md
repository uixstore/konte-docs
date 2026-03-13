# Footer Extra Content

Footer content area is the section where you see add custom content to the footer. We use this option to display the subscribe form on our demo.

## Remove Footer Content

You can remove the footer content area by un-selecting the option **Enable Extra** in **Customize > Footer > Footer Layout**.


## Add Subscribe Form

![Footer subscribe form](_images/footer--extra-content.png)

The option **Footer Extra** is the main option of this area. You can enter _HTML_ and _Shortcodes_ here. For example, we used a subscribe form which is provided by plugin [MailChimp for WordPress](https://wordpress.org/plugins/mailchimp-for-wp/) plugin. This is the code we used:

```
[vc_row][vc_column offset="vc_col-lg-offset-3 vc_col-lg-6 vc_col-md-offset-2 vc_col-md-8"][vc_column_text]
<h2 style="font-weight: 400; text-align: center;">Join Our List</h2>
<p style="font-size: 16px; text-align: center;">Signup to be the first to hear about exclusive deals, special offers and upcoming collections</p>
[mc4wp_form id="77"][/vc_column_text][/vc_column][/vc_row]
```

Please note that the form ID here (77) is on our site only. It could be different on your site. If you want to get the right shortcode for this, please go to **MailChimp for WP > Forms** and press the **Get Shortcode** button. Besides, the default form will look a little bit different with the form on our demo. Please replace all code of that form by following code:

```
<input type="email" name="EMAIL" placeholder="Your email address" required="">
<input type="submit" value="Subscribe">
```


## Add Extra Content To Bottom

If you want to add custom content at the bottom of site, you can use this option. Just order this section at the bottom, in **Customize > Footer > Footer Layout**

You can use this option to display somethings like custom menu, payment logos...

> [!TIP] you can desgin your content in a page then copy generated shortcodes to this option.