PHP Offline  Fonts
==================

### **This is under development and will soon be a composer package**

**Why can't I download the fonts from Google myself?**
Well, you'll be stuck with either the hinted/unhinted format, which will cause some machines to butcher your font. Also, Google corretly updates and assigns the correct files automatically for you. *This library is special because it downloads the fonts from Google to your server based on User Agent, ensuring perfect compatibility.*

How To
------
This will soon be a composer package or include. It also only supports Google Fonts. 
 1.  Copy the `fonts` folder where you would keep similar folders like `css`, `js`, etc. in your project.
 2.  Configure the `GoogleFontsCSS` file (its PHP) so that it knows what directory it's in with `$fonts_cache_folder`.
 3.  Set the folder to save the CSS files (based on User Agent) with `$cache_folder`.
 4.  Set `fonts_client_cache_folder` to how the client will perceive the font folder. PHP and the client will probably see this differently. Just see how I have it configured previously. The `$fonts_cache_folder` tells PHP that `DOCUMENT_ROOT` is the starting point, but a browser knows that `/` will bring it to the root. If you are hosting the actual fonts cross-domain, but not the CSS, this is the option you need to change to reflect that.
 5.  The `file_extention` setting is optional. Try it and see.
 6.  The `google_url` is what the script will look for when replacing Google's path to the font with your own.
 7.  You may now use it like you would use Google Fonts:

This:
```html
<link href='//fonts.googleapis.com/css?family=Lato:400,400italic,700' rel='stylesheet' type='text/css'>
```
Becomes:
```html
<link href='/fonts/GoogleFontsCSS?family=Lato:400,400italic,700' rel='stylesheet' type='text/css'>
```

**If Anything has left you in the dark, feel free to open an issue about it!**

TODO
----
 - More font providers
 - Composer Package
 - Auto delete/expring fonts (your cache will be huge otherwise)
 - Nginx Example