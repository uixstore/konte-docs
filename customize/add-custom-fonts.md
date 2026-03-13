# Add Custom Fonts


If you want to add custom fonts to your theme, you can follow this tutorial.


### 1. Add font files to the child theme

If your font is not ready for web use, you can use a webfont generator like [Font Squirrel](https://www.fontsquirrel.com/tools/webfont-generator). 
You should convert your file to recommended formats like `woff2`, `woff`.

> [!WARNING]
> The fonts you’re creating must be legally eligible for web embedding!


**Step 1** - Create a folder “fonts” in the child theme and upload your font files (.woff, .woff2, etc.) to the folder “fonts” via FTP.

**Step 2** - Load your fonts from style.css file of your child theme file, using the `@font-face` method.

```
@font-face {
	font-family: 'your_font_name';
	src: url('fonts/font-file.woff2') format('woff2');
	font-weight: normal;
	font-style: normal;
}
```


### 2. Add selections to the typography options

This theme uses the **Kirki Framework Toolkit** plugin to add options to the native Customizer of WordPress. Luckily, the Kirki Customizer Framework has a very handy typography control built into it. You can add add your font to the typography options of the theme with the filter hook `konte_custom_fonts_options`. But firstly, you need to have Kirki installed on your website.

Add this code the file `funcitons.php` of your child theme.

```
add_filter( 'konte_custom_fonts_options', function( $fonts ) {
	$fonts['families'][] = array( 'id' => 'your_font_name', 'text' => 'Custom Font Name' );
	$fonts['variants']['your_font_name'] = array( '400', '700', '900' );

	return $fonts;
} );
```

!> The **id** parameter must match with the name of the font you set in the `@font-face` above.


### 3. Change fonts of other elements

Because the theme just provides options of typography for main elements only, you may need to use custom CSS to change the font of other elements. It requires you to have experience with CSS customizing. The code to change the font of a specific element would be like this:

```
.element-selector {
	font-family: "your_font_name" !important;
}
```

Don't forget to change the `.element-selector` to match your element class (or ID).
