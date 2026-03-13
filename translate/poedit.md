# Using Poedit

There are a few different options for translating WordPress, as outlined in the WordPress Codex. For this tutorial, we’re going to use Poedit, an easy to use open source program available for Mac OS X, Windows and UNIX/Linux.

1. Install [Poedit](http://www.poedit.net/download.php).

1. Open Poedit and go to **File > New catalog from POT file** and select the POT in the **languages** folder of theme/plugin. For example, to translate Konte theme, please select the file **Konte/languages/Konte.pot**.

1. A catalog properties box will pop up asking for information about what you are translating. Enter the language you want to translate here. For example, enter "Spanish".

	![Poedit catalog](_images/translate--poedit-cataglog.png)

1. After you hit **OK** button, you'll be asked what you want to name your translation file. The name is important and there’s a particular format you will need to follow. Check out the [GNU `gettext’ utilities](http://www.gnu.org/software/gettext/manual/gettext.html#Language-Codes) to find your language and country codes.

	For example, if you're translating Konte theme into Spanish for Spain, the file should be name **Konte-es_ES.po**.

1. Save your file in the [Global languages folder](translate/store-translation.md) to ensure it stay intact during updates.

1. Now you can start translating your theme. Poedit has a simple and straight forward interface that doesn’t involve a steep learning curve. The space at the top will display all the text ready to translate, and any completed translations will display to the right. The boxes underneath show the source text you’ve selected to translate, your translation and any notes for translators.

	![Poedit translate](_images/translate--poedit-translate.png)