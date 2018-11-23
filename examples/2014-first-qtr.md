---
title: "Long Description Example"
permalink: /tutorials/images/examples/2014-first-qtr/
backlink: /tutorials/images/complex/#image-containing-substantial-information
layout: default
description: 
image: /content-images/wai-tutorial-images/social.png
github:
  repository: w3c/wai-tutorial-images
  path: 'examples/2014-first-qtr.md'
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
- C22
- G94
---

{::nomarkdown}
{% include_cached toc.html type="start" title="Page Content" class="full" %}
{:/}

-   TOC is created automatically.
{:toc}

{::nomarkdown}
{% include_cached toc.html type="end" %}
{:/}


## Site visitors for example.com

### Overview

The chart shows the website hits for the first quarter of 2014. It shows that Site 1 has more visitors than either of the other sites, but the number of visitors is decreasing. Site 2 has a fairly constant number of visitors, while for Site 3 page hits are increasing month on month.

### Values

Numerical values presented on the image:

<table>
  <caption>
      2014 First Quarter visitors per site (in thousands)
    </caption>
    <tr>
      <th scope="col">Period</th>
      <th scope="col">Site 1</th>
      <th scope="col">Site 2</th>
      <th scope="col">Site 3</th>
    </tr>
    <tr>
      <th scope="row">Jan</th>
      <td>135</td>
      <td>112</td>
      <td>92</td>
    </tr>
    <tr>
      <th scope="row">Feb</th>
      <td>117</td>
      <td>114</td>
      <td>99</td>
    </tr>
    <tr>
      <th scope="row">March</th>
      <td>96</td>
      <td>111</td>
      <td>126</td>
    </tr>
    <tr>
      <th scope="row">Qtr total</th>
      <td>348</td>
      <td>337</td>
      <td>308</td>
    </tr>
</table>

### Presentation

The bar chart represents both the number of visitors per month for each website, and the total number of visitors per website for the entire quarter. Website visitors for each month are represented using columns lined up horizontally, with heights indicating the number of visitors. A fourth column is provided for each website with the accumulated site visitors for the quarter.