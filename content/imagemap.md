---
title: "Image Maps"
permalink: /tutorials/images/imagemap/
layout: default
description: 
image: /content-images/wai-tutorial-images/social.png
github:
  repository: w3c/wai-tutorial-images
  path: 'imagemap.md'
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
- G196
- H67
- ARIA13
---

{::nomarkdown}
{% include_cached toc.html type="start" title="Page Content" class="full" %}
{:/}

-   TOC is created automatically.
{:toc}

{::nomarkdown}
{% include_cached toc.html type="end" %}
{:/}


A client-side image map is an image divided into selectable regions defined by `<area>` elements (“hotspots”) that allow user interaction. Usually, the selectable regions are links to other pages. For image maps, text alternatives are needed on both the `<img>` element itself (to convey the informative context) and on each of the `<area>` elements (to convey the link destination or the action that will be initiated if the link is followed).

## An organizational chart with links to individual pages
{:.ex}

The following organizational chart is used to provide links to each director's home page. The text alternative for the image is “Board of Directors and related staff:”. Each linked `<area>` has a text alternative to identify the individual -- for example, “Davy Jones: Chairman”. The text alternative for individuals also states their relation in the graph.

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

![Board of directors and related staff: ]({{ "/content-images/wai-tutorial-images/orgchart.png" | relative_url }}){:usemap="#Map"}

<map name="Map" id="Map">
  <area shape="rect" coords="176,14,323,58" href="../res/beyond" alt="Davy Jones: Chairman">
  <area shape="rect" coords="81,75,226,114" href="../res/beyond" alt="Carole Brewster: Company Secretary">
  <area shape="rect" coords="6,138,155,182" href="../res/beyond" alt="Harry H Brown: Marketing Director (reports to chairman)">
  <area shape="rect" coords="175,138,323,182" href="../res/beyond" alt="Paula Holbein: Sales Director (reports to chairman)">
  <area shape="rect" coords="345,136,496,186" href="../res/beyond" alt="Hugh Howard: Finance Director (reports to chairman)">
</map>

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<img src="orgchart.png"
     alt="Board of directors and related staff: "
     usemap="#Map">
<map id="Map" name="Map">
  <area shape="rect"
        coords="176,14,323,58"
        href="[…]"
        alt="Davy Jones: Chairman">
  […]
  <area shape="rect"
        coords="6,138,155,182"
        href="[…]"
        alt="Harry H Brown: Marketing Director (reports to chairman)">
  […]
</map>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

[Full code for Image map example](/tutorials/images/examples/imagemap/)

Browser implementation for image maps varies at the time of writing; see [this HTML bug](https://lists.w3.org/Archives/Public/public-html-bugzilla/2015Jan/0020.html). To accommodate for the different implementations, keep in mind to:

* use every image map only once. That means if multiple images with the same map are to be used, the map should be duplicated and have a different `id`s;
* place the `<map>` element as a direct sibling to the image.

{::nomarkdown}
{% include box.html type="start" title="Note" class="simple notes" %}
{:/}

Image maps may not function correctly on some mobile devices if the coordinates for the areas are not scaled using the same proportions as the image. To compensate for this, provide redundant text links on the same page.

{::nomarkdown}
{% include box.html type="end" %}
{:/}
