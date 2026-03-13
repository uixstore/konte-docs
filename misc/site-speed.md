# Site Speed

There are many things can slow down your website or speed it up. As a side note, these are not ordered by importance or any criteria, We've just gathered everything we've learned around how to speed up WordPress page loads and listed them all here.

This is what we done on our demo site to improve the loading time. You could try to follow it to improve your website's speed.

1. **Choose a good host.**

	When starting out, a shared host might seem like a bargain if you don't have too many visitor. We are using a hosting of [Stablehost](https://billing.stablehost.com/aff.php?aff=6792) for our demo site. But if you have more than 1000 visitors per day, you should use a VPS, or at least a higher plan of a sharing hosting.

1. **Use an effective caching plugin.**

	WordPress plugins are obviously quite useful, but some of the best fall under the caching category, as they drastically improve page loads time, and best of all, all of them on WordPress.org are free and easy to use.

	We are using [WP Super Cache](https://wordpress.org/plugins/wp-super-cache/) for our demo site. Beside this plugin, [W3 Total Cache](https://wordpress.org/extend/plugins/w3-total-cache/) is also another good choice.

1. **Combining CSS, JS and HTML.**

	Using [Autoptimize](https://wordpress.org/plugins/autoptimize/) for combining CSS, JS and HTML. Even the cache plugin supports combining those files, but sometime it break JS scripts. Therefore we usually using this plugin for better combining and minifying files.

1. **Use a content delivery network (CDN).**

	Essentially, a CDN, or content delivery network, takes all your static files you’ve got on your site (CSS, Javascript and images etc) and lets visitors download them as fast as possible by serving the files on servers as close to them as possible.

1. **Optimize images (automatically)**

	Yahoo! has an image optimizer called Smush.it that will drastically reduce the file size of an image, while not reducing quality. However, if you are like me, doing this to every image would be beyond a pain, and incredibly time consuming. Fortunately, there is an amazing, free plugin called [WP-SmushIt](https://wordpress.org/extend/plugins/wp-smushit/) which will do this process to all of your images automatically, as you are uploading them. No reason not to install this one.

1. **Add Expires headers to your files.**

	If you test your webstie speed on some tools, like GTmetrix, you will get a notice about adding expires headers. You can follow [this tutorial](https://gtmetrix.com/add-expires-headers.html) to add it to your website.


### Other resouses

You could easily found many tutorials on internet that telling about how to optimize your website's speed. There are some we found:

1. https://www.sparringmind.com/speed-up-wordpress/
1. http://www.wpbeginner.com/wordpress-performance-speed/
1. https://premium.wpmudev.org/blog/speeding-up-wordpress/
1. https://websitesetup.org/how-to-speed-up-wordpress/
1. https://www.keycdn.com/blog/speed-up-wordpress/
