# Dominant Colors Lazy Loading
Contributors: manuelwieser
Donate link: https://manu.ninja/
Tags: images, dominant colors, lazy loading, pinterest, javascript, optimization, performance, bandwidth
Requires at least: 4.4
Tested up to: 4.4.2
Stable tag: 0.5.2
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

This plugin allows you to lazy load your images while showing the dominant color of each image as a placeholder – like Pinterest or Google Images.

## Description

This plugin allows you to lazy load your images while showing the dominant color of each image as a placeholder – like Pinterest or Google Images. If you want to know how it works read the article [Dominant Colors for Lazy-Loading Images](https://manu.ninja/dominant-colors-for-lazy-loading-images), where I explain the general concept.

I plan on adding multiple features in the near future, as outlined in the backlog. To ensure the quality of the plugin please let me know if you encounter any issues. I will reply swiftly and fix them as soon as possible!

The plugin is compatible with [RICG Responsive Images
](https://co.wordpress.org/plugins/ricg-responsive-images/), which has been added to WordPress 4.4 as default functionality.

### Backlog

* Ability to change the dominant color to a custom color in the attachment details.
* Ability to choose a dominant color from a reduced color palette.
* Option to enable tiny thumbnails as described on [manu.ninja](https://manu.ninja/dominant-colors-for-lazy-loading-images).
* Function for retrieving the dominant color in various formats (hexadecimal, RGB, HSL…).
* Fallback for visitors without JavaScript.

## Installation

1. Upload `dominant-colors-lazy-loading` folder to the `/wp-content/plugins/` directory.
2. Activate the plugin through the 'Plugins' menu in WordPress.

## Frequently Asked Questions

### Why are no dominant colors calculated?

Please make sure that you have installed and activated the `imagick` PHP extension.

### How do I use the custom filter in my themes?

`$image = get_the_post_thumbnail( $post_id );
$image = apply_filters( 'dominant_colors', $image, get_post_thumbnail_id ( $post_id ) );
echo $image;`

## Changelog

### 0.5.2
* Portuguese translation added by Pedro Mendonça.
* Simple test suite for admin functions added.
* Changed all `[]` array literals to the classic `array()` for compatibility.

### 0.5.1
* Admin interface now shows an error if no ImageMagick PHP extension was found.
* Admin interface is now ready for translation. There is a `.pot` file, go crazy ;)
* German translations for the admin interface added.

### 0.5.0
* Added a bulk operation in the settings for calculating missing dominant color meta values for existing images. Until recently colors were only calculated upon initial upload of an image.

### 0.4.0
* Filter for lazy-loading images in custom templates and themes added.
* Added an option to specify a fallback color if no dominant color was found.

### 0.3.0
* Added an option to use SVG placeholders as described by [Shaw](http://codepen.io/shshaw/post/responsive-placeholder-image). SVG placeholders have the same pixel size and aspect ratio as the original images, instead of being a single square pixel. This way responsive images do not need a wrapper for preserving the original aspect ratio. This crosses "Automatically wrapping flexible images (`max-width: 100%; height: auto;`) so that the placeholder has the right aspect ratio." off the road map ;)
* Images with no dominant color stored in the database are now automatically skipped.

### 0.2.2
* Fixed a bug where responsive images weren't revealed properly.

### 0.2
* Galleries added via the default `[gallery]` shortcode are now also lazy loaded while showing the dominant color of each image as a placeholder.

### 0.1
* Initial release -- plugin seems to work ;)
