---
title: "Complete Image Maps Example"
permalink: /tutorials/images/examples/imagemap/
backlink: /tutorials/images/imagemap/an-organizational-chart-with-links-to-individual-pages
layout: default
description: 
image: /content-images/wai-tutorial-images/social.png
github:
  repository: w3c/wai-tutorial-images
  path: 'examples/imagemap.md'
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
---


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

<map name="Map" id="Map">
  <area
    shape="rect"
    coords="176,14,323,58"
    href="…"
    alt="Davy Jones: Chairman"
  >
  
  <area 
    shape="rect" 
    coords="81,75,226,114" 
    href="…"
    alt="Carole Brewster: Company Secretary"
  >
  <area 
    shape="rect" 
    coords="6,138,155,182" 
    href="…"
    alt="Harry H Brown: Marketing Director (reports to chairman)"
  >
  <area 
    shape="rect"
    coords="175,138,323,182"
    href="…"
    alt="Paula Holbein: Sales Director (reports to chairman)"
  >
  <area
    shape="rect" 
    coords="345,136,496,186" 
    href="…"
    alt="Hugh Howard: Finance Director (reports to chairman)"
  >
</map>

~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

