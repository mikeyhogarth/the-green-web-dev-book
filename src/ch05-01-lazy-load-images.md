# Lazy load images

Defer the loading of images until they are within the active viewport. This avoids paying the data cost for images the user never sees.

Lazy image loading used to be fiddly to implement, requiring an understanding of JavaScript. However, it is now **natively supported** across [all major browsers](https://caniuse.com/loading-lazy-attr) and requires no programming knowledge. Simply assign the `"lazy"` property to the `loading` attribute of the `img` tag, e.g.

```
<img loading="lazy" src="/foobar.jpg" alt="bar baz" />
```

This change ensures the request for `foobar.jpg` is only sent if the image becomes visible to the user (either through the user scrolling to the image's location or if the image becomes un-hidden, perhaps by a CSS rule). This technique is supported by screen readers, and also works for `iframe` tags.

Since this technique will degrade gracefully into older browsers, there is little reason to not use it. The behavior of this feature can vary between browsers, so you should make sure to test your assumptions and make sure your application is not erroneously sending off requests - you can do this using the [network section of your browser's developer tools](https://developer.chrome.com/docs/devtools/network/).

## Relevant Links

- ["Can I use..." entry for lazy attributes](https://caniuse.com/loading-lazy-attr)
- [MDN article on Lazy Loading](https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading)
