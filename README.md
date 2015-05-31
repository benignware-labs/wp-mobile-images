wp-mobile-images
----------------

> Deliver smaller images on mobile

This Wordpress Plugin lets you optimize images for mobile devices without much further effort.


It works totally server-sided by determining a mobile request, filtering `the_content` and `post_thumbnail_html` for local thumbnail images, getting its ratio by its src and searching for an appropriate smaller thumbnail-file matching the proportions at nearly `768px`.
Only mobile phones are supported.

## Usage

All you have to do, is to create an additional thumbnail-size for every thumbnail you want to be handled, having the same ratio than its original thumbnail.
For example, if you have an image-size defined called `large` with resolution `1200x600` and ratio `2`, you need to create another one, giving it `750x375` pixels.

```php
# functions.php
add_image_size( 'large', 1200, 600, true );
add_image_size( 'large_xs', 750, 375, true );
```

> Please note that after adding a new thumbnail size, you need to regenerate existing thumbnails. Best way to do this, is making use of good old [Regenerate Thumbnails Plugin](https://wordpress.org/plugins/regenerate-thumbnails/). You may also need to delete unwanted thumbnail files after changing your image-sizes.
