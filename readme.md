# Introducing Device Theme Switcher

Device Theme Switcher is a WordPress plugin that uses the [MobileESP PHP library created by Anthony Hand](http://code.google.com/p/mobileesp/)

## How do I use it?

Install the plugin from either the [WordPress Plugin Repository](http://wordpress.org/extend/plugins/device-theme-switcher/) or grab the latest bundled-zip here on github. Then set your handheld and tablet themes under Appearance > Device Themes. Computer users will be given the theme you specify in Appearance > Themes, as usual. However, now handheld users will see the handheld theme and tablet users will be given the tablet theme. Using WordPress child themes is supported.

The following can be used in your themes..

##### View Full Website

    <?php if (class_exists('Device_Theme_Switcher')) : Device_Theme_Switcher::generate_link_to_full_website(); endif; ?>


##### Return to Mobile Website

    <?php if (class_exists('Device_Theme_Switcher')) : Device_Theme_Switcher::generate_link_back_to_mobile(); endif; ?>

The anchor tags that output both have a CSS class: 'dts-link'. The 'View Full Website' anchor tag also has a class of 'to-full-website' and the 'Return to the Mobile Website' link has an additional class of 'back-to-mobile'.

##### Link Styling Example

    .dts-link {
        font-size: 1.5em ;
    }
        .dts-link.to-full-website {
            color: red ;
        }
        .dts-link.back-to-mobile {
    	    color: blue ;
        }

##### Constants
    
*Version 1.9+*. You can use these anywhere in themes. This could be helpful if for instance, you want one theme to power all devices.

    <?php if (HANDHELD_DEVICE) echo "HANDHELD" ?>
    <?php if (TABLET_DEVICE) echo "TABLET" ?>
    <?php if (HANDHELD_LOW_SUPPORT_DEVICE) echo "HANDHELD_LOW_SUPPORT" ?>



### Changelog 

* _Version 1.9_
    * NEW - Constants to check in the theme, HANDHELD_DEVICE, TABLET_DEVICE, and HANDHELD_LOW_SUPPORT_DEVICE
    * Included a pull request from Tim Broder (https://github.com/broderboy) which adds support for Varnish Device Detect (https://github.com/varnish/varnish-devicedetect). Thanks Tim!!
    * Made the Admin UI more presentable and WordPressy

* _Version 1.8_
    * Updated the Kindle detection for a wider range of support

* _Version 1.7_
    * Updated the plugin to provide backwards compatible support for WordPress < v3.4 (Pre the new Themes API)
    * Added a 3rd theme selection option for older/non-compliant devices, so theme authors can also supply a text-only version to those devices if they like. 
    * Revised some language in the plugin readme file

* _Version 1.6_
    * Updated the plugin to use the new Theme API within WordPress 3.4
    * Updated MobileESP Library to the latest verion (April 23, 2012) which adds support for BlackBerry Curve Touch, e-Ink Kindle, and Kindle Fire in Silk mode. And fixed many other bugs. 
    * Updated the Device Theme Switcher widgets so they only display to the devices they should, e.g. The 'View Full Website' widget will only display in the handheld theme. 
    * Revised readme language and added a WordPress Plugin Repository banner graphic. 

* _Version 1.5_
    * Modified the way themes are deliveried so the process is more stable for users with odd WordPress setups, by detecting where their theme folders are located instead of assuming wp-content/themes

* _Version 1.4_
    * Updated to the latest version of the MobileESP library which now detects some newer phones like the BlackBerry Bold Touch (9900 and 9930)

* _Version 1.3_
    * Changed the admin page to submit to admin_url() for those who have changed /wp-admin/ 
    * Added a warning suppresor to session_start() in case another plugin has already called it
    * Updated language in the WordPress readme file

* _Version 1.2_
	* Added the handheld and tablet theme choices to the WordPress Dashboard Right Now panel
	* Update both GitHub and WordPress readme files to be better styled and versed
	* Added two wigets for users to put in their themes
	* Coding and efficiency improvements
* _Version 1.1_
	* Bug fixes
    * Efficiency improvements
* _Version 1.0_
	* First Public Stable Release

## Credits

This plugin is based on the [concepts provided by Jonas Vorwerk's Mobile theme switcher plugin](http://www.jonasvorwerk.com/), and [Jeremy Arntz's Mobile Theme Switcher plugin](http://www.jeremyarntz.com/).