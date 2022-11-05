# Never use GIFs

Instead of animated GIFs, use the HTML5 `video` element to stream MP4 videos. The file size of a GIF can be quite large even for very short videos, and a near-identical effect can be achieved with a much smaller MP4 file. The following HTML will look exactly like a GIF to users, but is actually a muted MP4 set to play automatically and loop indefinitely.

```
<video autoplay loop muted playsinline>
  <source src="/media/video/my-video.mp4" type="video/mp4" />
</video>
```

The only way most users would realise this was a video is if they right-clicked it, at which point they might be thankful for the additional versatility of the format, including options to pause and rewind, view full-screen, or even "cast" the video to other devices.

The video above was originally a GIF almost 2MB in size. After an [online tool](https://cloudconvert.com/gif-to-mp4) was used to convert it into an MP4, the file's size dropped to less than 100k. Since video data will be _streamed_ to the user and not downloaded in full like a GIF, the user only pays the data cost for what they actually view.

Be aware that **MP4 Videos do not support transparency** like GIFs do; if transparency is required, consider a modern format with better compression such as WebP or AVIF, both of which support animation and transparency.

Other things to consider:

- If you leave the video's controls enabled, users can decide whether to play it at all, helping them avoid unwanted data costs.
- Multiple [other video formats](https://en.wikipedia.org/wiki/HTML5_video#Supported_video_and_audio_formats) are supported.

## Relevant Links

- ["Can I use..." entry for video](https://caniuse.com/video)
- ["Can I use..." entry for mp4](https://caniuse.com/mpeg4)
- [MDN article on the video tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
- [Smashing Magazine: GIF to Video](https://www.smashingmagazine.com/2018/11/gif-to-video/)
