# Create print-specific styles

Have you thought about whether your users will ever print your content onto physical paper? Use _print specific styles_ to apply certain styles only when a page is printed. This allows you to tailor the look of the content to the printed medium whilst also disabling certain sections or elements where it makes no sense for them to be printed at all. Doing so conserves electricity, paper and ink.

## Use cases for a print stylesheet

Printing out large areas of solid color can use a _lot_ of printer ink, so most modern browsers will automatically disable the printing of background images and background colors. In some cases this can lead to the printed page losing some of its brand identity, or some elements looking strange becoming unreadable - adding a print stylesheet allows you to correct some of this.

What you use print styles for is very case-specific and it might be that you decide that users are very unlikely to ever print out your application and that none of this is therefore a concern for you. Here are a few ideas to give you a flavour for the kind of thing that they are commonly used to fix or adjust;

- **Making text visible** - If you had a block of pure white text on a dark background, the browser may remove the background, making the text unreadable.
- **Maintaining brand identity** - your brand might have specific guidelines for how things like logos are displayed when they are black and white.
- **Disabling superflous elements** - This might include elements which are not relevant to the content such as headers, navigation, sidebars and footers, but also interactable elements such as buttons and forms - none of which provide any value once printed. Take the example of a recipe website - if someone is printing that page, they probably don't need to print all the links to other recipes you might have placed around the recipe itself.
- **Fixing layouts** - most modern websites are built mobile-first and responsive, meaning that a layout should be able to adapt to whatever viewport size it is applied to (paper or otherwise) - however if that is _not_ the case with your application then it might be that your layout prevents the content from being printed in portrait mode.

## How to create a print stylesheet

It might be that your application/site works just fine when printed without you having to do anything - you can verify what your page will look like when printed simply by using the _print preview_ functionality within your browser. If it does turn out that you need to apply some print styles, there are a number of ways to do this;

### Method 1: Create a seperate print-media stylesheet

Add a stylesheet using the `"media"="print"` attribute when the sheet is included;

```
<link rel="stylesheet" media="print" href="styles/print.css"/>
```

Styles specified by that stylesheet will now only be applied to pages when they are printed.

### Method 2: Using media queries

You can put print-specific styles directly into your existing stylesheets using media queries. You can differentiate print and screen styles using the following syntax;

```
@media screen {
// screen styles go here
}

@media print {
// print styles go here
}
```

You can also apply logical operators `not` or `only` to your media queries if it makes sense to specify things that way;

```
@media not print {
  // styles not to be applied to print go here
}
```

Note that if you do this, ensure that you are not including a `media` attribute when you actually include the stylesheet on the page or this will override these settings.

### Method 3: Leverage the capabilities of a CSS library or framework

If you are using a CSS library or framework, it is possible that the authors have already made some print-related considerations and created functionality or documentation to help you work with these styles;

- [TailwindCSS](https://tailwindcss.com) documents how you can use the media query functionality [within its config files](https://tailwindcss.com/docs/breakpoints#styling-for-print) to style for print.
- [BootStrap](https://getbootstrap.com/) provides special [utility classes](https://getbootstrap.com/docs/4.0/utilities/display/#display-in-print) specifically for print styling.

Always consult the documentation for your library or framework before trying to figure out novel solutions on your own.

## Paged media properties

It might be that your particular use case falls into the category of being "very likely" to be printed. If this is the case, there are a number of [paged media-specific CSS styles](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media) that can be applied to elements in order to achieve the exact printed look that you want for your content. These include;

- The [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page) media query for per-printed-page styles (normally for things like margins) - also includes support for pseudo selectors such as `:first` (to target only the first page) and `:left`/`:right` to target pages that would only appear on the left/right (depending on the major writing direction for the document).
- [Page Breaks](https://developer.mozilla.org/en-US/docs/Web/CSS/break-before) to allow content to be spread across multiple pages more logically.
- There is also support for more technical typographical concpets such as [orphans](https://developer.mozilla.org/en-US/docs/Web/CSS/orphans) and [widows](https://developer.mozilla.org/en-US/docs/Web/CSS/widows).

## Relevant Links

- [MDN page on media css @ rule](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
- [MDN page on the media attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-media)
- [Smashing Magazine article on print stylesheets](https://www.smashingmagazine.com/2018/05/print-stylesheets-in-2018/)
