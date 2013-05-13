gallery-metabox
===============

Proper gallery metabox for WordPress. Uses the new WP 3.5 media uploader. Instead of selecting the images one at a time, you can also select multiple images. Images can be sorted by dragging the thumbnails.

![gallery-metabox](http://www.daanvosdewael.com/files/gallery-metabox-preview.jpg)

Usage
-----

>This is not a plugin! You need to include this in your theme folder and further customize it to your needs. If you are not comfortable doing this, don't use it...

Include the `gallery.php` in your `functions.php`:

```php
require_once 'gallery-metabox/gallery.php';
```

Specify where you want the gallery metabox to show on line 17 in `gallery.php`. You can pass an array to have it show up on multiple post types, custom post types are also allowed:

```php
$types = array('post', 'page', 'custom-post-type');
```

In your template inside a loop, grab the IDs of all the images with the following:

```php
$images = get_post_meta($post->ID, 'vdw_gallery_id', true);
```

Then you can loop through the IDs and call `wp_get_attachment_link` or `wp_get_attachment_image` to display the images with or without a link respectively:

```php
foreach ($images as $image) {
  echo wp_get_attachment_link($image, 'large');
  // echo wp_get_attachment_image($image, 'large');
}
```