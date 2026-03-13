# Install Konte Theme

After you download the package from ThemeForest, please unzip it. You'll see a file called `konte.zip`, which is the main file needed to upload and install.

You can either choose to upload and installl the theme using **WordPress theme install** or use **FTP** function.

> [!TIP] If you plan to customize the theme, you should install both the theme and child theme, then activate the child theme. Using a child theme allows you to custimze some parts of the parent theme without touching into the theme files.


## Install via WordPress Dashboard

![Install Konte via WordPress Dashboard](/_images/install-theme.png)

**Step 1** – Navigate to **Appearance > Themes**.

**Step 2** – Click the **Add New** button on top of the page, then the **Upload Theme** button.

**Step 3** – Click **Choose File** and find the theme files you've just downloaded. If you’ve downloaded the installable WordPress file, then you do not need to unzip the file. If you’ve downloaded the Full Theme Package, you have to unzip the master `konte.zip` file, therein you will see a secondary `konte.zip` file, this is the one you select to install.

**Step 4** - Click the **Install Now** button.

**Step 5** – When upload and installation progresses are completed, click **Activate**, or go to `Appearance > Themes` and activate the **Konte** theme.


<iframe width="560" height="315" src="https://www.youtube.com/embed/iBK5wjMua0o" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>



## Install via FTP

If you get any fail when install theme by Wordpress install function, we recommend to use FTP.

**Step 1** - If you have downloaded the Full Theme Package from ThemeForest, please unzip the package file to get the theme file `konte.zip`. Unzip the `konte.zip` file, you'll get a folder `Konte`.

**Step 2** - Use a FTP client like [FileZilla](http://filezilla-project.org/) and upload the extracted folder to `wp-content/themes` folder on your host

**Step 3** - Log in to your WordPress Dashboard and navigate to **Appearance > Themes** and clicking the **Activate** button of the Konte theme.


## Troubleshooting

1. **"Are you sure you want to do this?"** error

	If you get the “Are You Sure You Want To Do This” message when installing Konte.zip file via WordPress, it means you have an upload file size limit that is set by your host. If this happens, please install the theme via FTP or contact your hosting company and ask them to increase the limit.

1. **Theme is missing the style.css stylesheet** error

	A common issue that can occur when installing a WordPress themes is **“The package could not be installed. The theme is missing the style.css stylesheet.”** error message being displayed when uploading or activating the theme. One of the reasons you may receive this error is if you have uploaded the incorrect file. You have 2 options for downloading your theme

	- Installable WordPress file only
	- All files and documentation (full zip folder). You will need to extract and locate the installable WordPress file.