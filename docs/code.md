---
title: Code Samples
layout: single-col
date: 2019-04-23
---

# Code Samples

*This page provides all the kinds of code snippets you might need. The gray boxes should show you exactly what code you need to use; copy and paste it into your own site pages and adjust the attributes as you need to.*

**• In all of the below examples, make sure you take extreme care with your quotation marks and other coding symbols!**

**• DO NOT use double quotation marks `"` in your titles or captions. Single quotation marks `'` are fine.**

**• Remember to use the [Markdown Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for Markdown syntax issues. And you can always double experiment with [Dillinger](http://dillinger.io).**

---

## Essay Metadata
All essays must have the following metadata at the top of the page, with the values customized to your own page. **Be sure you have the 3 hyphens `---` before and after your metadata on their own lines**. The top of your essay page should look like:

``` markdown
---
title: Mesa Vista Hall
author: Fred Gibbs
layout: single-col
date: 2019-03-25
---
```

---

## Images
There is one basic way we will embed images in our essay files. Note that it is totally different from how you learned to do them in Markdown itself. This is because if we want to maintain consistency between images, like how the captions appear, we have to make sure we display all images exactly the same way.


### Standard Usage

{% include figure.html class="img-right" width="33%" caption="Mesa Vista Hall" src="essays/images/default.jpg" %}

Fusce vulputate eleifend sapien. Vestibulum purus quam, scelerisque ut, mollis sed, nonummy id, metus. Nullam accumsan lorem in dui. Cras ultricies mi eu turpis hendrerit fringilla. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; In ac dui quis mi consectetuer lacinia. Nam pretium turpis et arcu. Duis arcu tortor, suscipit eget, imperdiet nec, imperdiet iaculis, ipsum.


To embed the image above, we use:
```
{%raw%}{% include figure.html
  class="img-right"
  width="33%"
  caption="Mesa Vista Hall"
  src="images/default.jpg"
%}{%endraw%}
```

---

### Use whatever width you want
You can alter the width of the image **as a percentage of our standard page width**. You can have them appear on the left, right, or center of the page.

### Half-width
{% include figure.html class="img-left" width="50%" src="essays/images/centennial-hotel.jpg" caption="Obviously we need a 50% image somewhere with text wrapping around it."%}

Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; In ac dui quis mi consectetuer lacinia. Nam pretium turpis et arcu. Duis arcu tortor, suscipit eget, imperdiet nec, imperdiet iaculis, ipsum.

---

To achieve the above half-width image, use:
```
{%raw%}{% include figure.html
class="img-left"
width="50%"
caption="Obviously we need a 50% image somewhere."
src="images/centennial-hotel.jpg"
%}{%endraw%}
```
---

### Side by side
{% include figure.html class="img-left" width="48%" src="essays/images/centennial-hotel.jpg" caption="Here's an image on the left."%}

{% include figure.html class="img-left" width="48%" src="essays/images/centennial-hotel.jpg" caption="Here's an image on the right."%}


To achieve two images side by side use (note the 48% width for each):
```
{%raw%}
{% include figure.html
class="img-left"
width="48%"
caption="Here's an image on the left."
src="images/centennial-hotel.jpg"
%}

{% include figure.html
class="img-left"
width="48%"
caption="Here's an image on the right."
src="images/centennial-hotel.jpg"
%}

{%endraw%}
```

---

### Full-width

{% include figure.html class="img-center" width="100%" caption="Make sure your image is large enough to be 100% width or it will look grainy. See above."  src="essays/images/centennial-hotel.jpg" %}


To achieve the above full-width (but not jumbotron) image, use:
{%raw%}
```
{% include figure.html
  class="img-center"
  width="100%"
  caption="Make sure your image is large enough to be 100% width or it will look grainy. See above."
  src="essays/images/centennial-hotel.jpg" %}
```
{%endraw%}

---

### Juxtapose
It's easy to set up a slider to compare historic and contemporary photos. If you find a historic image from a vantage point that you can replicate, please take a modern photo so we can better illustrate the changes in the surrounding space.

{% include juxtapose.html
image1="{{site.baseurl}}/essays/images/kimo-1928.jpg"
image2="{{site.baseurl}}essays/images/kimo-1938.jpg"
caption="These sliders are way more effective the more closely you line up the before and after images."
%}

<script src="https://cdn.knightlab.com/libs/juxtapose/latest/js/juxtapose.min.js"></script>
<link rel="stylesheet" href="https://cdn.knightlab.com/libs/juxtapose/latest/css/juxtapose.css">

Include the change-over-time-slider, we use

```
{%raw%}{% include juxtapose.html
image1="images/kimo-1928.jpg"
image2="images/kimo-1938.jpg"
caption="These sliders are way more effective the more closely you line up the before and after images."
%}{%endraw%}
```

---
## Footnotes
All good historical essays (as you're writing) show what their sources are, which helps readers know what actual research underlies the essay.

To get a footnote to show up, there are two steps:

1) put `[^SOMETEXT]` in your essay where you want the superscript number to appear, and change SOMETEXT to some unique signifier related to the content of the note. In your markdown file, your text will look like:

```
Here's a sample sentence with a footnote at the end.[^source] Here is yet another sentence.[^another-source]
```

2) put  `[^SOMETEXT]: Your footnote text` at the bottom of your essay.


```
[^source]: Your footnote text
[^another-source]: Text for another footnote.
```

Viewed as a webpage, the code above will render as:

Here's a sample sentence with a footnote at the end.[^source] Here is yet another sentence.[^another-source]  Note that the numbering happens automagically, so you don't need to think about that.

[^source]: Your footnote text
[^another-source]: Text for another footnote.

We don't need to footnote every statement, and because you paragraphs should be on the same topic, you can simply use a footnote reference for each paragraph if everything in it comes from the same source. But if you have a certain point you want to make from another source, please cite it directly. Cite as precisely as you can. For books, you need a page number or range, and archival sources should be indicated with collection title, box, folder, etc, as appropriate. Make sure someone else can find what you have cited!


### Footnotes on captions
A good place for image credits is in our "footnotes". To put your image credit in the citation popup, just use the footnote code at the end of your blockquote.

> Here is my quote from a historical source that people would find interesting.[^mysource]

[^mysource]: Some trustworthy reference


Add the code, for that is:
```
> Here is my quote from a historical source that people would find interesting.[^mysource]

[^mysource]: Some trustworthy reference
```

---

## Pull Quotes

As part of our effort to highlight our most important ideas---even in the context of relatively short essays---we want to use pull quotes.

### Standard usage
{% include aside.html class="pullquote" text="
Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce id purus. Ut varius tincidunt libero. Phasellus dolor. Maecenas vestibulum mollis diam. Pellentesque ut neque." %}

Aenean vulputate eleifend tellus. Aenean leo ligula, porttitor eu, consequat vitae, eleifend ac, enim. Aliquam lorem ante, dapibus in, viverra quis, feugiat a, tellus. Phasellus viverra nulla ut metus varius laoreet. Quisque rutrum. Aenean imperdiet. Etiam ultricies nisi vel augue. Curabitur ullamcorper ultricies nisi. Nam eget dui. Etiam rhoncus.


To place a pull quote as above, we use:


```
{%raw%}{% include aside.html
  class="pullquote"
  text="Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce id purus. Ut varius tincidunt libero. Phasellus dolor. Maecenas vestibulum mollis diam. Pellentesque ut neque."
  %}{%endraw%}
```

---

### Full-width quotes
If you are quoting from a historical source, you might want to say more than can fit in a normal pull quote format. For those cases, you can use a markdown blockquote to highlight a particularly juicy quotation.

> Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce id purus. Ut varius tincidunt libero. Phasellus dolor. Maecenas vestibulum mollis diam. Pellentesque ut neque.

To achieve the above full width pull quote, just start your quote with a greater-than sign as shown below:
```
> Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce id purus. Ut varius tincidunt libero. Phasellus dolor. Maecenas vestibulum mollis diam. Pellentesque ut neque.
```
