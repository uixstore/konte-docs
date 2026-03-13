# Storing Translation Files

Storing translation files in the right directory is very important to make sure the translations you’ve downloaded, created or edited remain functional and intact. The best way to do this is store them inside the **languages** folder located inside the **wp-content** folder.


## Store Theme Translation Files

Place your theme translation files inside **wp-content/languages/themes** folder. If you don't have the languages and themes folder, simply create the languages folder, and the themes folder inside it.

Updating the theme will not overwrite the wp-content folder. Storing your translation files here will ensure they stay intact during updates.

When storing your language files, remember that the file structure is different and must include the theme name, as well. For example, if the language files are in the Deutsch language, the file names would be **Konte-de_DE.mo** and **Konte-de_DE.po**.


## Store Plugin Translation Files

Place your plugin translation files inside **wp-content/languages/plugins/** folder. If you don't have the languages and plugins folder, simply create the languages folder, and the plugins folder inside it.

Updating the plugin will not overwrite the wp-content folder. Storing your translation files here will ensure they stay intact during updates.

When storing your language files, remember that the file structure is different and must include the plugin name, as well. For example, if the language files are in the Deutsch language, the file names would be **konte-de_DE.mo** and **konte-de_DE.po**.