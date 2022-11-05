# Use webfonts responsibly

Use web fonts responsibly and lean towards using only natively supported fonts if possible. Whilst modern browsers support many built in system fonts, using web fonts allows you to download and use specific fonts from directly within your application's CSS. This feature been [supported across all major browsers](https://caniuse.com/fontface) for a very long time (as far back as Internet Explorer 6) and there are a few reasons you might want to use it for your application.

- A particular font might be very important to your brand identity or a major stylistic choice for your application.
- It might be very important that the site looks exactly the same across all browsers and operating systems (some native fonts are only available on certain operating systems, for example the [Tahoma](<https://en.wikipedia.org/wiki/Tahoma_(typeface)>) font is Microsoft-developed and therefore [not available in some Linux distros](https://wiki.debian.org/tahoma)).

Including web fonts does require your users to _download an additional and not-insignificant amount of extra data_, increasing your site's energy footprint.

## Using web web fonts

Web fonts are downloaded using the [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face) css rule. This supports several types of file formats including `woff2`, `TrueType` and `svg`.

```
@font-face {
  font-family: "myAwesomeFont";
  src: url("myAwesomeFont.woff2");
}
```

Content Delivery Networks (CDNs) such as [google fonts](https://fonts.google.com/) will often provide all of the supporting CSS for you, making it very simple to include the font in your application.

## It's perfecty fine to use Webfonts

This prompt is **not** reccomending that you avoid web fonts, only that you use them responsibly and with your eyes open to the data cost. Don't simply choose to use webfonts on a whim - make it a _conscious and confident choice_ and factor the extra download cost into your page weight budget.

If you do decide that you are going to use web fonts, there are a number of things you can do in order to reduce the data cost;

- **Use a CDN** - Serving web fonts from a a CDN such as [google fonts](https://fonts.google.com/) carries a number of benefits - chief among these being smart caching. Users may have already downloaded the font from elsewhere on the internet and have it stored locally, and any fresh downloads will likely have been cached closer to the user's location.
- **Only download what you need** - Some web fonts come with multiple variants (e.g. multiple font weights). You should only download what you are actually using.
- **Consider images** - If you are only using webfonts in one place (e.g. the header/logo) then consider using an image with `alt` text instead - the data cost of downloading an image might end up being smaller than the cost of downloading a web font.
- **Consider using webfonts only for titles and headings** - The difference in appearance may be negligable at smaller sizes and reserving web fonts to only titles would mean you could download less variants.

## Relevant Links

- [MDN page about web fonts](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Web_fonts)
- [MDN page about the `@font-face` css rule](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
- [Caniuse page about web fonts](https://caniuse.com/fontface)
