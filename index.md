# Project 4: Website Performance Optimization

Keeping within 60 frames per second.

**Minify, Compress, Cache!**

Google's [PageSpeed](https://developers.google.com/speed/pagespeed/insights) Insights analyzes and generates suggestions on how to make that page faster.

Udacity recommends to use Chrome Canary for debugging websites.

## Critical Rendering Path

More about the [Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/) with Google's [Web Fundamentals](https://developers.google.com/web/fundamentals/).

### What is the Document Object Model?

Before the browser can render the page, it needs to construct the DOM and CSSOM trees. As a result, we need to ensure that we deliver both the HTML and CSS to the browser as quickly as possible. [link](http://bit.ly/1NYSyvT)

![DOM](http://bit.ly/2of6NaT)

[The HTML5 Specification](https://www.w3.org/TR/html5/)

### Flushing the Document Early

Flushing is when the server sends the initial part of the HTML document to the client before the entire response is ready. When done correctly, flushing results in a page that loads and feels faster. The flush should occur before the expensive parts of the back end work, such as database queries and web service calls. But the flush should occur after the initial response has enough content to keep the browser busy. [link](http://bit.ly/2oTAalF)

If needed check "[Chunk Scatter](http://bit.ly/2nv88gF)", an HTTP chunked encoding analysis tool.

How to Use Chrome [Timeline Tool](http://bit.ly/2oPOYT5)

### Render Blocking CSS

By default, CSS is treated as a render blocking resource, which means that the browser won't render any processed content until the CSSOM is constructed. Make sure to keep your CSS lean, deliver it as quickly as possible, and use media types and queries to unblock rendering.

- By default, CSS is treated as a render blocking resource.
- **Media types and media queries allow us to mark some CSS resources as non-render blocking.**
- The browser downloads all CSS resources, regardless of blocking or non-blocking behavior.
[link](http://bit.ly/1ydoYhV)

### Layout

Pages optimized for a variety of devices must include a meta viewport tag in the head of the document. A meta viewport tag gives the browser instructions on how to control the page's dimensions and scaling.

- Use the meta viewport tag to control the width and scaling of the browser's viewport.
- Include **width=device-width** to match the screen's width in device-independent pixels.
- Include **initial-scale=1** to establish a 1:1 relationship between CSS pixels and device-independent pixels.
- Ensure your page is accessible by not disabling user scaling.

```markdown
<meta name="viewport" content="width=device-width, initial-scale=1">
[link](http://bit.ly/2gztfq1)
```

### Inline your CSS

Inlined CSS reduces the amount of files the browser has to download prior to displaying your web page. If you are using an external CSS file, the browser must first load your HTML file, then download your CSS file.

[link](https://varvy.com/pagespeed/inline-small-css.html)

### Optimizing the DOM

**Text compression with GZip
- Apply content-specific optimizations first: CSS, JS, and HTML minifiers.
- Apply GZIP to compress the minified output.** [link](http://bit.ly/1ux5lPs)

GZIP is not enough(20 years old) - DELTA & GZIP Compression! Check **LZMA, LPAQ, BZIP2**
[link](http://bit.ly/2nVVNgO)

### HTTP caching

read here more
[link](http://bit.ly/1OiFrKQ)

### External JavaScript Dependencies

JavaScript allows us to modify just about every aspect of the page: content, styling, and its response to user interaction. However, JavaScript can also block DOM construction and delay when the page is rendered. To deliver optimal performance, make your JavaScript **async** and eliminate any unnecessary JavaScript from the critical rendering path.

**JavaScript blocks DOM construction unless explicitly declared as async.**
[link](http://bit.ly/1rDQkxE)

### Mobile Analysis in PageSpeed Insights

It is not easy to meet the one second time budget. Luckily for us, the whole page doesn’t have to render within this budget, instead, we must deliver and render the above the fold (ATF) content in under one second, which allows the user to begin interacting with the page as soon as possible. Then, while the user is interpreting the first page of content, the rest of the page can be delivered progressively in the background.
[link](http://bit.ly/2oSmojA)

### The Preload Scanner

How the Browser Pre-loader Makes Pages Load Faster
[link](http://bit.ly/2oS9Clj)

## Project

[Cameron's portfolio](http://cameronwp.github.io/udportfolio/), [Customed Cameron's portfolio](https://laurahesse.github.io/udacity-frontend-nanodegree-mobile-portfolio)
