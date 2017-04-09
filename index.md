# Project 4: Website Performance Optimization

Keeping within 60 frames per second.

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

By default, CSS is treated as a render blocking resource, which means that the browser won't render any processed content until the CSSOM is constructed. Make sure to keep your CSS lean, deliver it as quickly as possible, and use media types and queries to unblock rendering. [link](http://bit.ly/1ydoYhV)

- By default, CSS is treated as a render blocking resource.
- **Media types and media queries allow us to mark some CSS resources as non-render blocking.**
- The browser downloads all CSS resources, regardless of blocking or non-blocking behavior.

### Layout

Pages optimized for a variety of devices must include a meta viewport tag in the head of the document. A meta viewport tag gives the browser instructions on how to control the page's dimensions and scaling.

- Use the meta viewport tag to control the width and scaling of the browser's viewport.
- Include 'width=device-width' to match the screen's width in device-independent pixels.
- Include 'initial-scale=1' to establish a 1:1 relationship between CSS pixels and device-independent pixels.
- Ensure your page is accessible by not disabling user scaling.

'<meta name="viewport" content="width=device-width, initial-scale=1">'
[link](http://bit.ly/2gztfq1)

### Inline CSS


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/LauraHesse/p4-notes/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
