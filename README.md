# Mini Project - Blurry Web Page with loading

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View blurred website at the beginning and slowly sharpening the view
- See loading timer that will dissapear once website is fully sharpened

### Links

- Solution URL: [https://github.com/TomasScerbak/js-blurry-page-load.git]
- Live Site URL: [https://tomasscerbak.github.io/js-blurry-page-load/]

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Vanilla JavaScript

### What I learned

I've learned function how to set internal and clear the interval at specific number. How to change inner text during load and change opacity and blurr effects.


```js
const loadText = document.querySelector('.loading-text');
const bg = document.querySelector('.bg');

let load = 0;

let int = setInterval(blurring, 30);

function blurring() {
    load++

    if (load > 99) {
        clearInterval(int);
    }

    loadText.innerText = `${load}%`;
    loadText.style.opacity = scale(load, 0, 100, 1, 0);
    bg.style.filter = `blur(${scale(load, 0, 100, 30, 0)}px)`;
}

function scale (number, inMin, inMax, outMin, outMax) {
    return (number - inMin) * (outMax - outMin) / (inMax - inMin) + outMin;
}
```

### Continued development

I'll be practicing small vanilla JS projects and continue with practice

## Author

- Website - [Tomas Scerbak](https://tomasscerbak.github.io/tomas-scerbak-portfolio/)
- Frontend Mentor - [@Potato](https://www.frontendmentor.io/profile/TomasScerbak)
