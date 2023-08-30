# Responsive Order Summary Card Component

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- See hover states for interactive elements

### Screenshot

![](./design/desktop-preview.jpg)

### Links

- Live Site URL: [https://btk5301.github.io/order-summary-component-main/](https://btk5301.github.io/order-summary-component-main/)

## My process

### Built with

- Media Queries
- CSS custom properties
- SASS/Gulp workflow
- Flexbox
- Mobile-first workflow

### What I learned

1. Media Queries

   In order to make the content responsive, I set screen size breakpoints for both desktop and mobile devices. You can also utilize SASS functions and maps to pass variables like "large" or "medium" so you don't have to pass the pixel size everytime.

   ```scss
   $breakpoints-up: (
     "large": "1440px",
     "medium": "870px",
     "small": "375px",
   );

   @mixin breakpoint($size) {
     @media (min-width: map-get($map: $breakpoints-up, $key: $size)) {
       @content;
     }
   }
   ```

   Then utilize the function like so:

   ```scss
   .card {
     max-width: rem(330);
     width: 100%;
     border-radius: 16px;
     background-color: white;
     display: flex;
     flex-direction: column;
     filter: drop-shadow(0 0 8px rgba(0, 0, 0, 0.2));

     @include breakpoint(large) {
       max-width: rem(400);
     }
   }
   ```

2. Pseudo classes

   There are many pseudo classes that can be utilized in CSS like active, visited, or hover and are implemented using `:` . In this case the challenge was about hover effects so that was the main focus.

   ```scss
   .card {
     max-width: rem(330);
     width: 100%;
     border-radius: 16px;
     background-color: white;
     display: flex;
     flex-direction: column;
     filter: drop-shadow(0 0 8px rgba(0, 0, 0, 0.2));

     @include breakpoint(large) {
       max-width: rem(400);
     }
   }
   ```

3. & in SCSS

   In SCSS, nesting a class selector with & will append the nested class name to the outer class name. This saves on typing and works really well with the BEM methodology of class names.

   ```scss
   .card {
     max-width: rem(330);
     width: 100%;
     border-radius: 16px;
     background-color: white;
     display: flex;
     flex-direction: column;
     filter: drop-shadow(0 0 8px rgba(0, 0, 0, 0.2));

     &__header {
       font-weight: 900;
       text-align: center;
       margin-bottom: rem(16);
     }
   }
   ```

   This will append \_\_header to .card parent to select for .card\_\_header

4. divs as Images

   While images can be added through `<img>` tags in html, they can also be added to divs through the `background-image` CSS like so:

   ```scss
   &__hero {
     margin-bottom: rem(24);
     height: rem(160);
     background-size: contain;
     border-radius: 16px 16px 0 0;
     width: 100%;
     background-image: url("../images/illustration-hero.svg");
   }
   .background {
     background-image: url("../images/pattern-background-mobile.svg");
     height: 50%;
     width: 100%;
     background-size: contain;
     background-repeat: repeat-x;
     position: absolute;

     @include breakpoint(medium) {
       background-image: url("../images/pattern-background-desktop.svg");
     }
   }
   ```

5. File reference location

   With the project Gulp setup, the compiled CSS files end up in a dist folder. Therefore, the path to images or assets should be relative to the final CSS files and not the SCSS files (Thanks VScode for the false autocomplete paths 😒)

6. Putting `<a>` tag inside `<p>` tag

   When adding linked text, be careful of only using an `<a>` tag. The linked text will take up the whole width of the parent which causes the users to acidenntaly click on the text even if they didn't directly click on the text.
   Practice safe anchoring and wrap it in a `<p>` tag

   ```html
   <p class="card__cancel-container">
     <a class="card__cancel">Cancel Order</a>
   </p>
   ```

### Continued development

Manipulating images with CSS was very new to me in this project and to be honest, is still a black-box for me. I will continue to hone my skills on different CSS properties for images.

## Author

- Website - Brian K
