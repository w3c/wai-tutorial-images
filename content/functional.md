---
title: "Functional Images"
permalink: /tutorials/images/functional/
layout: default
description: 
image: /content-images/wai-tutorial-images/social.png
github:
  repository: w3c/wai-tutorial-images
  path: 'functional.md'
footer: > # Text in footer in HTML
  
inline_css: |
  .ex, .ap {
    b, &:before {
      color: #005A6A;
      font-weight: inherit;
    }
  }
  .risky {
    &:after {
      background-color: #005A6A;
      color: #fff;
      font-weight: normal;
      border-radius: 100%;
      width: 1.2em;
      height: 1.2em;
      margin-left: .6em;
      line-height: 1.2;
      text-align: center;
      display: inline-block;
      content: "!";
    }
  }
  .ex {
    counter-increment: examples;
    counter-reset: approaches;
  }
    .ex:before {
      content: 'Example ' counter(examples) ': ';
    }
    .ex.inap {
      counter-reset: none;
    }


  .newap {
    counter-reset: approaches;
  }

  .newex {
    counter-reset: examples;
  }


  h2.first, h3.first, .newexap {
    counter-reset: examples approaches;
  }

  .ap {
    counter-increment: approaches;
  }
    .ap:before {
      content: 'Approach ' counter(approaches) ': ';
    }
wcag_techniques:
- H37
- H36
---

{::nomarkdown}
{% include_cached toc.html type="start" title="Page Content" class="full" %}
{:/}

-   TOC is created automatically.
{:toc}

{::nomarkdown}
{% include_cached toc.html type="end" %}
{:/}

Functional images are used to initiate actions rather than to convey information. They are used in buttons, links, and other interactive elements. The text alternative for the image should convey the action that will be initiated (the purpose of the image), rather than a description of the image. For instance, as shown in examples below, the text alternative should be “print this page” rather than “(image of a) printer”, “search” rather than “magnifying lens” or “Example.com homepage” rather than “Example.com logo”.

Missing or empty `alt` values create significant problems for screen reader users because functional images are essential to the functionality of the content. Screen readers will typically announce the image file name, the image URL, or the URL for the link destination, which is unlikely to help users understand the action that will be initiated by the image.

## Image used alone as a linked logo
{:.ex}

The following image is the only content of a link that leads to the W3C home page. It has the text alternative “W3C home” to indicate where the link will take the user. The next example, [“Logo image within link text” example](#logo-image-within-link-text), discusses what to do when there is more text in the link to identify the destination:

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

[![W3C home]({{ "/content-images/wai-tutorial-images/w3c.png" | relative_url }})](https://www.w3.org/)

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<a href="https://www.w3.org/">
  <img src="w3c.png" alt="W3C home">
</a>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Note" class="simple notes" %}
{:/}

1. In this situation, the logo is also an image of the text “W3C”, but in this case, its primary function is to link to the homepage, so the word “home” was added to the text alternative.

2. Images used as logos are exempt from some of the accessibility requirements that apply to other images of text, for instance, there are no minimum color contrast and text size requirements.

{::nomarkdown}
{% include box.html type="end" %}
{:/}

## Logo image within link text
{:.ex}

In this example, the W3C logo is used to supplement text within a link that leads to the W3C home page. The image does not represent different functionality or convey other information than that already provided in the link text, so a null (empty) value is applied, (`alt=""`), to avoid redundancy and repetition. In effect the image is a decorative adjunct or visual cue to the link text:

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

[![]({{ "/content-images/wai-tutorial-images/w3c.png" | relative_url }}){:style="vertical-align: middle; margin-right: 1em;"}W3C Home](https://www.w3.org/){:style="display:inline-block;"}

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<a href="https://www.w3.org/">
  <img src="w3c.png" alt=""> W3C Home
</a>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

## Icon image conveying information within link text
{:.ex}

In this example, the image follows text within a link to inform users that the link will open in a new window. It has the text alternative “new window” to convey the meaning of the icon:

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

[W3C Home page ![new window]({{ "/content-images/wai-tutorial-images/new-window.png" | relative_url }})](https://www.w3.org/)

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<a href="https://www.w3.org/" target="_blank">
  W3C Homepage <img src="new-window.png" alt="new window">
</a>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Note" class="simple notes" %}
{:/}

This technique is often used with icons to indicate different file formats such as AVI, ODF, MP3, PDF, Word, and many more. In this case, the text alternative should equally convey the format represented by each icon, see [Informative Images]({{"/tutorials/images/informative/" | relative_url}}#images-conveying-file-format).

{::nomarkdown}
{% include box.html type="end" %}
{:/}

## Stand-alone icon image that has a function
{:.ex}

The following image is an icon representing a printer to denote print functionality. It has the text alternative “Print this page” because its purpose is to activate the print dialog when it is selected:

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

[![Print this page]({{ "/content-images/wai-tutorial-images/print.png" | relative_url }})](javascript:print())

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<a href="javascript:print()">
  <img src="print.png" alt="Print this page">
</a>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

## Image used in a button
{:.ex}

The following image is used to give the button a distinct style. In this case, it is the button to initiate a search request and is an icon representing a magnifying lens. The text alternative for the image is “search” to convey the purpose of the button:

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

<form action="#" method="post">
  <p>
    <label for="search" style="vertical-align: middle; display:inline-block;">Search:</label>
    <input name="search" id="search" type="text" style="vertical-align: middle; display:inline-block;">
    <input name="submit" src="{{ "/content-images/wai-tutorial-images/searchbutton.png" | relative_url }}" alt="Search" type="image" style="vertical-align: middle; display:inline-block; border: none;">
  </p>
</form>

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<input type="image" src="searchbutton.png" alt="Search">
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}
