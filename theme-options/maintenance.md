# Maintance

![Customize maintenance mode](_images/customize-maintenance.png#alignright)

This section containt options turn your site into the maintenance mode. Its allows you to display a user-friendly notice to yor users instead of a broken site during website maintenance. When you are logged as an administrator, you can visit your website normally.

- **Enable Maintenance Mode** - turn on/off the maintenance mode on your site.
- **Mode** - select the suitable mode for your site. There are 2 options for you chose from, _Maintenance_ or _Coming Soon_.
	- **Maintenance** - select this mode if you need to work on building/fixing your site for a long perior of time. It return the HTTP 503 to browsers and bots.
	- **Coming soon** - select this mode if you just need to close your website to vistor in a short perior of time. It return the HTTP 200 to browsers and bots.

	This option help your site always be friendly to search bots and don't affect to your site SEO ranking. You can learn more about these status codes in [this link](https://yoast.com/http-503-site-maintenance-seo/).

- **Mainenance Page** - select the page you designed to display as your maintenance page.
- **Maintenance Page Layout** - select the layout for the maintenance page. This option only works if the maintenance page use the default tempalte.