# Frontend Mentor - Single price grid component solution

This is a solution to the [Single price grid component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/single-price-grid-component-5ce41129d0ff452fec5abbbc). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See a hover state on desktop for the Sign Up call-to-action

### Screenshot

![](./screenshot.jpg)

### Links

- Solution URL: [https://github.com/pawelgp/single-price-grid-component](https://github.com/pawelgp/single-price-grid-component)
- Live Site URL: [https://pawelgp.github.io/single-price-grid-component/](https://pawelgp.github.io/single-price-grid-component/)

## My process

### Built with

- Semantic HTML5 markup,
- CSS custom properties,
- rem units,
- CSS Flexbox & Grid,
- BEM,
- SCSS (Dart Sass),
- DRY.

### What I have learnt

I have used HTML5 tags just for text allocation. CSS CP for coloursset in root element. REM units gives ability to manage sizes adequatly to base value set in html tag in pixels. BEM is there for styling with classes not by tag names. However tags as html, body or footer have been used w/o classes. I don't see a reason, in this particular example, to add class to the unique and only tags in the document. There is neither header, nor main tags, as I gathered all in one component, but with two blocks, their elements and modifiers. Sass is a logical choice when using BEM. Sass mixins helps in addition to prevent code repetition.

H4 can be easily replaced with ex. H2 with no CSS changes as long as class stays in place.

```html
<h4>Every card title</h4>
```
I've started using sass mixins with default variables, along with sass modules.

```css
@use "sass:color";
...
@mixin box-highlight($amount: 0%) {
  background-color: color.scale(hsl(71, 73%, 54%), $lightness: $amount);
  font-weight: 700;
}
```
When noticed there is a block size shifting on font swap, to avoid it I set some fixed values ex.:
```css
.deck {
  min-height: 465px;
  max-width: 642px;
  ...
}
```
There are a few more colours on the given design than presented on style guid, but still decided to keep them simple. Instead of adding more colours I achieved their shades by transparency.
```css
@mixin text-transparent($transparency: 0.5) {
  color: hsla(0, 0%, 100%, $transparency);
}
...
&__text {
    &--transparent {
      @include text-transparent();
    }
    &--transparent-70 {
      @include text-transparent(0.7);
    }
  ...
}
```

### Continued development

The areas I want to continue focusing on in future projects are as pointed in Built with section. The techniques I found useful and want to refine and perfect are SASS modules and functions.
I also want to learn to prevent shifting of any type of elements that making bad user experience with interface.

### Useful resources

- [sass:color](https://sass-lang.com/documentation/modules/color) - SASS built-in modules.

## Author

- Website - [over40.pl](https://over40.pl)
- Twitter - [@pgpasich](https://www.twitter.com/pgpasich)
