# Order summary card Component

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
- [Acknowledgments](#acknowledgments)

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

3. & in SCSS

4.

```js
const proudOfThisFunc = () => {
  console.log("🎉");
};
```

If you want more help with writing markdown, we'd recommend checking out [The Markdown Guide](https://www.markdownguide.org/) to learn more.

**Note: Delete this note and the content within this section and replace with your own learnings.**

### Continued development

Use this section to outline areas that you want to continue focusing on in future projects. These could be concepts you're still not completely comfortable with or techniques you found useful that you want to refine and perfect.

**Note: Delete this note and the content within this section and replace with your own plans for continued development.**

### Useful resources

- [Example resource 1](https://www.example.com) - This helped me for XYZ reason. I really liked this pattern and will use it going forward.
- [Example resource 2](https://www.example.com) - This is an amazing article which helped me finally understand XYZ. I'd recommend it to anyone still learning this concept.

**Note: Delete this note and replace the list above with resources that helped you during the challenge. These could come in handy for anyone viewing your solution or for yourself when you look back on this project in the future.**

## Author

- Website - [Add your name here](https://www.your-site.com)
- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@yourusername](https://www.twitter.com/yourusername)

**Note: Delete this note and add/remove/edit lines above based on what links you'd like to share.**

## Acknowledgments

This is where you can give a hat tip to anyone who helped you out on this project. Perhaps you worked in a team or got some inspiration from someone else's solution. This is the perfect place to give them some credit.

**Note: Delete this note and edit this section's content as necessary. If you completed this challenge by yourself, feel free to delete this section entirely.**
