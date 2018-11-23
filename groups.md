---
title: "Groups of Images"
permalink: /tutorials/images/groups/
layout: default
description: 
image: /content-images/wai-tutorial-images/social.png
github:
  repository: w3c/wai-tutorial-images
  path: 'groups.md'
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

Sometimes groups of images are used together to represent one piece of information. For example, a collection of star icons that together represent a rating. In this case, only one of the images needs a text alternative to describe the entire collection, while the other images have a null (empty) `alt` attribute so that they are ignored by assistive technology.

In other cases, a group of images may represent a collection of related images. For example, showing a collection of art impressions that are thematically related. In this case, each image needs its text alternative that describes it individually, as well as its relationship within the group.

## Multiple images conveying a single piece of information
{:.ex}

This group of five images combined shows a product rating. There are five images (three filled stars, one half-filled star and one empty star) indicating the overall rating. The text alternative for the first image is “Rating: 3.5 out of 5 stars”. All other images have a null (empty) `alt` attribute (`alt=""`).

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

Rating: ![3.5 out of 5 stars]({{ "/content-images/wai-tutorial-images/star-full.png" | relative_url }})![]({{ "/content-images/wai-tutorial-images/star-full.png" | relative_url }})![]({{ "/content-images/wai-tutorial-images/star-full.png" | relative_url }})![]({{ "/content-images/wai-tutorial-images/star-half.png" | relative_url }})![]({{ "/content-images/wai-tutorial-images/star-empty.png" | relative_url }})

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
Rating:
<img src="star-full.jpg"  alt="3.5 out of 5 stars">
<img src="star-full.jpg"  alt="">
<img src="star-full.jpg"  alt="">
<img src="star-half.jpg"  alt="">
<img src="star-empty.jpg" alt="">
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

## A collection of images
{:.ex}

In the example below, the HTML5 `<figure>` and `<figcaption>` elements are used to provide a caption for each image in a collection. The `<figure>` element can be nested, which is used in the example to provide a caption for the entire collection of images. The WAI-ARIA attribute `role` with the value of `group` is used to indicate this grouping to assistive technologies, `aria-labelledby` makes sure that the `figcaption` elements are used as labels for the individual groups.

Note: The web browser and assistive technology support vary for this particular WAI-ARIA attribute and value.

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}

<figure role="group" aria-labelledby="fig1">
<figcaption id="fig1">The castle through the ages: 1423, 1756, and 1936 respectively.</figcaption>


<figure role="group" aria-labelledby="fig11">
<img src="{{ "/content-images/wai-tutorial-images/castle-etching.jpg" | relative_url }}" alt="The castle has one tower, and a tall wall around it.">
<figcaption id="fig11">Charcoal on  wood. Anonymous, circa 1423.</figcaption>
</figure>
<figure role="group" aria-labelledby="fig12">
<img src="{{ "/content-images/wai-tutorial-images/castle-painting.jpg" | relative_url }}" alt="The castle now has two towers and two walls.">
<figcaption id="fig12">Oil-based paint on canvas. Eloisa Faulkner, 1756.</figcaption>
</figure>
<figure role="group" aria-labelledby="fig13">
<img src="{{ "/content-images/wai-tutorial-images/castle-fluro.jpg" | relative_url }}"
alt="The castle lies in ruins, the original tower all that remains in one piece.">
<figcaption id="fig13">Film photograph. <span lang="fr">Séraphin Médéric Mieusement</span>, 1936.</figcaption>
</figure>

</figure>

{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<figure role="group" aria-labelledby="fig1">
  <figcaption id="fig1">
    The castle through the ages: 1423, 1756, and 1966 respectively.
  </figcaption>


  <figure role="group" aria-labelledby="fig11">
    <img src="castle-etching.jpg"
      alt="The castle has one tower, and a tall wall around it.">
    <figcaption id="fig11">Charcoal on  wood. Anonymous, circa 1423.</figcaption>
  </figure>

  <figure role="group" aria-labelledby="fig12">
    <img src="castle-painting.jpg"
      alt="The castle now has two towers and two walls.">
    <figcaption id="fig12">Oil-based paint on canvas. Eloisa Faulkner, 1756.</figcaption>
  </figure>

  <figure role="group" aria-labelledby="fig13">
    <img src="castle-fluro.jpg"
      alt="The castle lies in ruins, the original tower all that remains in one piece.">
    <figcaption id="fig13">Film photograph. <span lang="fr">Séraphin Médéric Mieusement</span>, 1936.</figcaption>
  </figure>

</figure>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

