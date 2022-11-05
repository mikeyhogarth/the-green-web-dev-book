# Use appropriate image formats

Always try to use an appropriate format for the type of image you are working with. Photographs work well in lossy formats such as JPEG, but if you want to draw a logo or similar in different sizes and colours, SVG may be more appropriate.

Here's a short list of other recommendations. Note that WebP and AFIV are both versatile enough to fulfil multiple roles, and normally offer 20-30% better compression than alternatives. Where feasible, you should use vector graphics.

| Image Type   | Preferred Format | Fallback Format |
| ------------ | ---------------- | --------------- |
| Photography  | WebP, AVIF       | JPEG            |
| Flow Diagram | SVG              | WebP, AVIF,PNG  |
| Animation    | WebP, AVIF       | GIF             |
| Transparency | WebP, AVIF       | PNG, GIF        |
| Logo         | SVG              | WebP, AVIF, PNG |
| Icon         | SVG              | WebP, AVIF, PNG |

Choosing an inappropriate format can result in image files _much larger_ than they need to be (sometimes hundreds of times larger).

**Be cautious using the AVIF format**; whilst it is intended as a successor to WebP, current tooling and [browsers](https://caniuse.com/avif) are not yet mature enough to fully support it, so you need to provide fallback images within your pages using the [HTML5 `picture`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture) element.

## Relevant Links

- [MDN article on image types](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
- ["Can I use"... entry for WebP](https://caniuse.com/webp)
- ["Can I use"... entry for AVIF](https://caniuse.com/avif)
