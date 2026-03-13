# Setup Language

WordPress makes it super-easy to change the language on your website. Simply go to **Settings > General** in your WordPress dashboard, and scroll down to the bottom of the page. There you will see the option to select **Site language**.

![Translate setup language](_images/translate--setup.png)

If you do not see your language in the list, this does not mean that it is not available or that you can not use it.
We will show you how to manually install language packs in WordPress.


### Manually Installing WordPress Translation Files For Other Languages

WordPress uses a gettext system for translations (localization and internationalization). Volunteer users from around the world use a main .pot template file to translate WordPress in their languages. This results into two files for each language. Portable Object format file with .po extension, and Machine Object file with .mo extension. You will need a .mo file for your language.

Go to the WordPress [translation teams](https://make.wordpress.org/polyglots/teams/) page to see if there is a WordPress translation available for your language.

![Translate download language](_images/translate--download.png)

Next, click on the percentage value to see the status of the translation progress in your language and then click on current WordPress version.

You will now reach GlotPress, which is a web based app used by WordPress team to manage and translate WordPress projects.

Once there, you need to scroll down to the bottom until you see the export section. In the dropdown, select Machine Object Message Catalog (.mo) and then click on Export link.

![Translate download exported](_images/translate--export.png)

Repeat the process above and select Portable Object Message Catalog (.po) and then click on the Export link.

After downloading and unzipping the language pack on your computer, you will need to connect to your website using an FTP client. Once connected, upload the language files to /wp-content/languages folder.

After you’re done uploading the file, return to the WordPress admin area. Go to Settings » General page and scroll down to site language option. You can now select the language you just uploaded because it will appear under installed languages.
