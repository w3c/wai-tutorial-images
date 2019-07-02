---
title: "Tips and Tricks"
permalink: /tutorials/images/tips/
layout: default
description: 
image: /content-images/wai-tutorial-images/social.png
github:
  repository: w3c/wai-tutorial-images
  path: 'tips.md'
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
---

## Tips

- **Choosing appropriate text alternatives:** <br>
  Imagine that you’re reading the web page aloud over the phone to someone who needs to understand the page. This should help you decide what (if any) information or function the images have. If they appear to have no informative value and aren’t links or buttons, it’s probably safe to treat them as [decorative]({{"/tutorials/images/decorative/" | relative_url}}).

- **Prioritize information in text alternative:** <br>
  Aim to put the most important information at the beginning.

- **Length of the text alternative:** <br>
  The `alt` text should be the most concise description possible of the image’s purpose. If anything more than a short phrase or sentence is needed, it would be better to use one of the long description methods discussed in [complex images]({{"/tutorials/images/complex/" | relative_url}}).

- **Punctuation within `alt` attributes:**

  * As for any text, using punctuation in the text alternative makes the information easier to understand. In particular, remember to add space characters in the `alt` text when there’s no space character between the image and adjacent text, to avoid having words running together when they are read by a screen reader.

  * If you use a null (empty) text alternative (`alt=""`) to hide decorative images, make sure that there is no space character in between the quotes. If a space character is present, the image may not be effectively hidden from assistive technologies. For instance, some screen readers will still announce the presence of an image if a space character is put between the quotes.

- **Superfluous information in the text alternative:** <br>
  Usually, there’s no need to include words like “image”, “icon”, or “picture” in the alt text. People who can see will know this already, and screen readers announce the presence of an image. In some situations, it may be important to distinguish between paintings, photographs, or illustrations, etc., but it’s best to avoid the more generic use of the terms.

- **SVG graphics:**

  * SVG graphics can be referenced in the `src` attribute of an `<img>` element like other image formats (PNG, JPEG, GIF). In this case, the examples of this tutorial can be used with SVG as well.

  * As SVG images consist of tags like HTML, their code can also be used in HTML5 directly. In this case you can provide a text alternative in a `<title>` element within the SVG image. To improve accessibility support, that title should be referenced from an `aria-labelledby` attribute of the `<svg>` element, for example:

  `<svg aria-labelledby="svgtitle1"> <title id="svgtitle1">Settings</title> [other svg code] </svg>`

- **Logos:** <br>
  Logo images with text are exempt from some of the accessibility requirements. For instance, there is no minimum contrast requirement.

## Other W3C Resources

- Background information on [providing text alternatives for non-text content](https://www.w3.org/WAI/intro/people-use-web/principles#alternatives) in How People with Disabilities Use the Web.
- Test the accessibility of images on your site: [Quick Checks Image text alternatives](https://www.w3.org/WAI/EO/Drafts/eval/checks#images).
- Examples of good and bad practice in selecting text alternatives can be found in the [Before and After Demonstration](https://www.w3.org/WAI/demos/bad/) (BAD).
