=== WP-Addpub ===
Contributors: cyberscorp
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=6286924
Tags: plugin, banner, ads, html, flash, manage, video, photo
Requires at least: 2.3
Tested up to: 3.8
Stable tag: 1.2.8

Banners Management (images, flash and html code) - can be used to customize banners by language or by category using zone and filter fields

== Description ==

WP-addpub is a very simple plugin that let's you upload your banners or your html and javascript code to your blog. Can be used, also, for any kind of script (google adsense, paypal donate, youtube video...)

The advantages of this plugin:

* Enabling and disabling the banner
* Display banners in different areas.
* Ability to display a banner depending on any special field (category, tag, etc).
* Ability to display a banner depending on the language using the field filter.
* Ability to add/edit a script banner.
* Ability to display a random banner.
* Display banner in content of pages or posts using shortcode.

== Installation ==

1. Unzip the file and place the folder wp-addpub in the directory plugins wordpress \ wp-content \ plugins
2. Activate the plug wp-addpub
3. Go on the management of banners in the Options> WP-Addpub

These variables can be used separately or together (example: "zone=sidebar&filter=EN")

== Frequently Asked Questions ==

= Can I manage a banner per category ? =

Yes, you can use filter to specify the category's ID.

e.g.
$catid = get_the_category(); // get the ID of the category
wp_addpub("filter=".$catid[0]->term_id); // show banner that has filter equal to the cat id

= Can I add a banner to the content of my post ? =

Yes, the shortcode [wp-addpub] allows you to add a banner into pages or posts. For attributes, follow the section "How-to use".

e.g.
[wp-addpub bannerid="12"]

== Screenshots ==

1. Add a banner
2. Edit a banner (How-to insert a HTML Code)
3. Display an embedded object

== Changelog ==

= 1.2.8 =
* (Fixed) Shortcode attribute names are always converted to lowercase before they are passed into the handler function.
* (Fixed) MYSQL error when inserting a new banner.

= 1.2.7 =
* Add a banner into pages and posts using the shortcode [wp-addpub]
* A second argument is added to the php function wp_addpub as boolean ($echo). set to true to echo the result or set to false for return the result as string.

= 1.2.6 =
* add an 'alt' on image
* russian translation by Vladimir Vasilenko (aka jeltoesolnce)

= 1.2.5 =
* add CDATA to javascript code to ignore by the validator (reported by Jorge)
* add the full url to swfobject (reported by Jorge)
* add width to the banner type input 
* bug fixed : when updating a banner without uploading a new file, it changes to html code.

= 1.2.4 =
* code optimization
* bug : user level access set to 8 (reported by Lars)
* bug : error when adding a html banner (reported by inklude)

= 1.2.3 =
* bug div id when displaying many swf in the same page.
* show error if cannot upload the file

= 1.2.2 =
* bug ie7 resolved.

= 1.2.1 =
* Display a random banner using random argument. e.g. : wp_addpub ("zone=sidebar&random=true");

= 1.2 =
* Accept a script as a banner
* Check if there is a new version of the plugin
* Correct bug : Edit banner

= 1.1 =
* add new file "swfload.swf" => enable to click an swf banner
* BUG Display flash
* Change varchar(255) to TEXT

== A brief Markdown Example ==

How-to use:

Add the following line in your theme:

<?php wp_addpub ( "bannerID=1" ) ; ?>

The parameter of the function is a string that contains variables:

* bannerID : Id of the banner
* zone: a text field that can be used to identify an area of your page (eg sidebar, footer)
* filter: a text field that can be used as a criterion for display (ie value: French, English or Category1, Category2)
* random : display a random banner (random=true)

or

Add a shortcode into content of pages or posts : [wp-addpub]

Add attributes to the shortcode to get the banner :
* bannerID : Id of the banner. bannerID attribute goes alone. the others could be mixed together.
* zone: a text field that can be used to identify an area of your page (eg sidebar, footer)
* filter: a text field that can be used as a criterion for display (ie value: French, English or Category1, Category2)
* random : display a random banner (random=true)