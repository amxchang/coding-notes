# Responsive Images

These notes are from the free Udacity course titled Responsive Images.

Quick review: To be honest, I don't think the course was extremely good. It helped give me some insight to responsive images, but I just don't think that the videos and quizzes were very good. Many of the quizzes require the Udacity Browser Extension, which is no longer available. I could do the quizzes, but I couldn't submit an answer (since the extension gives you a code once you do the quiz correctly). The explanations could be confusing at times, but that may be because I haven't really used Chrome Dev Tools before. Many of the videos were very short (less than 5 minutes). I felt like I was learning while watching the videos, but now that I'm reflecting, I feel like I could have quickly googled the content and spent much less time. However, some people might learn better with videos. Since the course is free, I encourage you to look over it to see if you might be interested.

## Lesson 1: Getting Up and Ready

### Why Responsive Images?

- Images consume a lot of bandwidth.
- Images don't always work well on different devices.
  - For example: On a mobile device, a large image may get "cropped." The user must scroll around to see the full picture.

> "Create a product, don't re-imagine one for small screens. Great mobile products are created, never ported."
> - Brian Fling

- Chrome Dev Tools can be used to look at the code, see the website on different devices, and check out the image size.

## Lesson 2: Units, Formats, Environments

### All about Bits and Pixels

- Total bits = pixels x bits per pixels
- To improve performance, keep images as small as possible and compression as high as possible.
- Less pixels x better compression = Less bytes

### Requests and Revenue

- The average webpage makes 56 requests for images.
- Image requests have costs.
  - A study by Google shows that a 0.4 to 0.9 second increase decreases traffic and ad revenue by 20%.
  - A study by Amazon shows that every 100 millisecond increase in page load causes a loss of sales by 1%.

### Relative Sizing

- Images with fixed sizes get "cropped" if the image is bigger than the viewport.
- Relative sizes make images match the viewport.
- Sometimes, if the viewport is too large, the image becomes blurry and pixelated.
  - `max-width: 100%` can fix this, since it doesn't allow the image to become wider than the natural width. 
- Window size may change, so don't assume the window size will always be the same.
- To fit two images side by side, no matter the size of the viewport, use relative sizing.
  - For example: Use `width: 50%;`
- `calc()` can perform calculations.
  - For example: to put a margin between photos, use `calc ((100% - 10px)/2);` to find the size of the photos.
  
```
/* This example makes the right margin equal to zero for the last image. */
img: last-of-type {
  margin-right: 0;
}
```

### Landscape and Portrait

- Devices can be landscape or portrait oriented. 
  - Taller, square images can work well in portrait mode but wider image can be a problem.

### Less Well Known CSS Units

- To make an image cover the entire height of the viewport, you can set the height to 100%.
  - However, that only works if the height of the html and body elements are also set to 100%.
- A better way is to use the vh (viewport height) unit. 
  - 1 vh = 1% of the viewport height
  - vw (viewport width) also works
- The vmin (viewport minimum) unit corresponds to 1% of the viewport height or width (whichever is smaller).
- If you want the image to cover the whole viewport but don't want it to stretch or squash, you can use vmax (viewport maximum).
  - It corresponds to 1 of the viewport height or width (whichever one is greater).
  - If you set `width: 100vmax;` and `height: 100vmax;`, the image resizes to cover the viewport.

### Raster and Vector

- Raster images are photographs or other images that are represented as a grid of individual dots of color.
  - They can come from a camera, scanner, or created with the HTML canvas.
- Vector images are images like logos or line art.
  - They are sets of curves, lines, shapes, fill colors, and gradients.
  - They can be created by programs like Adobe Illustrator or from using vector formats like SVG.
  - Vectors can be rendered at any size.
  
### File Formats
 
- Don't use a JPEG to combine a SVG and an image. 
  - The file size will be too big.
  - Also, the SVG will no longer have crisp and clear edges.
- Use JPEG or WebP (when supported) for photographic raster images.
- Use SVG for vector images.
  - If you can't, use PNG.
  
## Lesson 3: Images with Markup

### Performance

- Try to reduce the quantity of file requests, not just the size of the image files.
- Latency = the delay between request and response
- Ilya Grigorik says that latency is the new bottleneck.

### Text Problems

- Text as graphics can cause issues.
  - Can't be read by screen readers
  - Can't be found by search engines
- Use fonts and real text instead of a PNG or JPEG
- Don't use pictures if it's not needed.

### CSS Techniques

- CSS can be used for shadows, rounded corners, gradients, and animations.
- There is a processing and rendering cost for these techniques, especially for mobile.

### CSS Background Images

- CSS supports background images, which can be used to create responsive effects.
- You can make many cool effects with pure CSS.
- CSS `image-set()` can be used to choose a background image based on screen resolution.
- `background-size: cover;` makes the image as small as possible while it still completely fills the container.
- `background-size: contain;` makes the image as large as possible while it's still completely visible inside the container.

### Symbol Characters

- If you need to use a graphical symbol, check if it's available as part of a font. 
  - That way, it will be responsive.
  - It can also be used with CSS effects.
- Note: to use Unicode characters, you need to set the character set to UTF-8 inside the meta tag.

### Icon Fonts

- Icon fonts provide an option for little pictures in websites, without needing to use an image.
  - For example: Zocial is an icon font.
- Icons before the text are added with `[class*="zocial-"]:before`. This applies the CSS rules to all classes that start with zocial.
- use @import to import the fonts
- Icon fonts can be scaled and an entire set can be downloaded in one font. This makes them good for responsive design.

### Inlining Images

- You can use SVGs or data URIs to reduce file requests by inlining images.
- Inline SVG has good support on mobile and desktop browsers.
- Optimization tools can reduce SVG sizes.
- Data URIs provide a way to include a file, like an image, inline as a base 64 number.
  - `<img src = "data:image/svg+xml;base64,[data]">`
  - The full version is about 5,000 characters though.
  - Data URIs are well supported on different browsers.
  
## Lesson 4: Full Responsiveness

### Responding to Screen Capability & View

- Serving one single file for every single context isn't a good idea.
- A big photo for a high definition TV doesn't work for a tiny watch.
- Media queries only refer to the viewport dimensions, not the actual display size of the image.

### srcset

- Instead of using a small photo that will pixelate, you can use a big photo.
  - However, not everyone will need such a big picture.
- The normal img src only gives one URL to use.
- srcset allows you to provide multiple image options
  - the browser will choose the best one
```
<img src="wallaby_1x.jpg" srcset="wallaby_1x.jpg 1x, wallaby_2x.jpg 2x" alt="Wallaby">
/* 1x and 2x are pixel density descriptors */
```
- Some browsers don't support srcset, so they use the src attribute and ignore srcset.
- srcset can also be used with width (w) units. 
```
<img src="small.jpg" srcset="small.jpg 500w, medium.jpg 1000w, large.jpg 1500w" alt="Wallaby">
```

### Sizes Attribute

- The w unit tells the browser the dimensions of an image file so it can make a decision about which file to retrieve.
- The sizes attribute tells the browser the sizes at which an image will be displayed, since the HTML is parsed before the CSS.
```
<img src="small.jpg" srcset="small.jpg 500w, medium.jpg 1000w, large.jpg 1500w" sizes="50vw" alt="Wallaby">
```
- If there is a media query, you have to add the additional sizes to the sizes attribute.

### The Picture Element

```
<picture>
  <source srcset="kittens.webp" type="image/webp">
  <source srcset="kittens.jpeg" type="image/jpeg">
  <img src="kitten.jpg" alt="Two grey tabby kittens">
</picture>
```

- Source tags provide additional possible images.
  - If the browser can't use the first one, it continues to the next one and so on.
- The picture element provides alternative sources for image files.
- The above example contains a WebP file for browsers that support it, as well as a JPEG for files that don't. If a browser doesn't support the picture element, there's still the img src.

### The Full Monty

```
/* Provides a minimum width for the image */
<source media="(min-width: 650px)" srcset="kitten-large.png">
```

- Full Monty combines media queries, srcset, and different images.

### Accessibility

- Not all people on the web can see everything so they must use screen readers (ex: ChromeVox).
- Use alt attributes.
  - Leave alt attributes empty for images that are just decorations.
