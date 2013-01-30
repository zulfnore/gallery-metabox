gallery-metabox
===============

Proper gallery metabox for WordPress. Uses the new WP 3.5 media uploader. Instead of selecting the images one at a time, you can also select multiple images. Images can be sorted by dragging the thumbnails.

Usage
-----

Include the `gallery.php` in your `functions.php`:

```php
require_once 'gallery-metabox/gallery.php';
```

Specify where you want the gallery metabox to show on line 21 in `gallery.php`. You can pass an array to have it show up on multiple post types, custom post types are also allowed:

```php
array('post', 'page', 'custom-post-type')
```