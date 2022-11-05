# Resize images appropriately

Don't serve images that are bigger than they need to be. Larger images mean larger files, resulting in more data traffic. If possible, you should **pre-resize the image** on the server so the user's browser downloads it in an appropriate size.

It is common in web development to have the browser render images in dimensions much smaller than those of the original file. This can be done using CSS or the `width` and `height` attributes of an image tag. At best, this means scaling by a few hundred pixels to help an image fit a given layout, but at worst it can mean images thousands of pixels in size being rendered as thumbnails.

Such extreme rescaling forces users to pay the data cost of downloading an image they may never see at full size and, depending on the image's format, that cost can be steep. This is especially problematic for mobile devices, where smaller screens require smaller images, and users' data allowances might be limited and expensive.

## Resizing images

Resizing images need not be a tedious manual task; if you can identify images on your server that are larger than required, you can automate the resizing process. There are many tools available to help you do this, including [ImageMagick](https://imagemagick.org/index.php), which makes resizing images as easy as:

```
convert person.jpg -resize 64x64 person_thumb.jpg
```

ImageMagick also includes the `mogrify` command, which is similar to the `convert` command above but works on batches of images.

## Handling different sizes for different viewports

If you know your user's screen is only 500 pixels wide, you probably don't need to serve them huge image files. Historically there was no decent solution to this issue, but that is no longer the case. The HTML5 `picture` element can be used with media queries to ensure only appropriately sized images are requested, e.g.

```
<picture>
    <source srcset="/foo_500.jpg" media="(min-width: 500px)">
    <img src="/foo.jpg" alt="Bar" />
</picture>
```

The picture element is [supported across all major browsers](https://caniuse.com/picture). You can set your own thresholds depending on the target viewport width; screen widths can vary significantly between devices, but mobile phones typically don't have a screen width greater than 450 pixels at time of writing. Most modern browser developer tools let you [simulate mobile devices](https://developer.chrome.com/docs/devtools/device-mode/), letting you test the functionality without needing the physical device itself.

## Relevant Links

- ["Can I use..." entry for the picture tag](https://caniuse.com/picture)
- [ImageMagick Home page](https://imagemagick.org/index.php) - a tool for resizing images
