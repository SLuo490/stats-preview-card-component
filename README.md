# Frontend Mentor - Stats preview card component solution

This is a solution to the [Stats preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/stats-preview-card-component-8JqbgoU62). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Frontend Mentor - Stats preview card component solution](#frontend-mentor---stats-preview-card-component-solution)
  - [Table of contents](#table-of-contents)
  - [Overview](#overview)
    - [The challenge](#the-challenge)
    - [Links](#links)
  - [Documentation](#documentation)
    - [HTML](#html)
    - [Styling](#styling)
      - [Utilities](#utilities)
      - [Mobile](#mobile)
      - [Website](#website)
    - [Built with](#built-with)
  - [Author](#author)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size

### Links

- Solution URL: [Solution URL](https://www.frontendmentor.io/solutions/stats-preview-card-component-GhBrS8qwFy)
- Live Site URL: [Live](https://brilliant-granita-0d2ca7.netlify.app/)

## Documentation

### HTML

```html
<body>
  <main>
    <section class="image">
      <img src="./images/image-header-mobile.jpg" alt="" />
    </section>
    <section class="contents">
      <h1 class="title fw-700-Inter">
        Get <span class="text-color">insights</span> that help your business
        grow.
      </h1>
      <h2 class="info fw-400-Inter">
        Discover the benefits of data analytics and make better decisions
        regarding revenue, customer experience, and overall efficiency.
      </h2>

      <div class="data">
        <div class="companies">
          <h3>10k+</h3>
          <p>COMPANIES</p>
        </div>
        <div class="templates">
          <h3>314</h3>
          <p>TEMPLATES</p>
        </div>
        <div class="queries">
          <h3>12m+</h3>
          <p>QUERIES</p>
        </div>
      </div>
    </section>
  </main>
</body>
```

I sectioned my code into two sections contained in a `<main>` container. The sections include a `image` section and a `content` section. The `image` section contains the image whereas the `content` section contains the information. For the `data` I contained it in a `div` so that I can use `flex-box` to align the data easier.

### Styling

#### Utilities

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Root Variable */
:root {
  --p-very-dark-blue: hsl(233, 47%, 7%);
  --p-dark-desaturated-blue: hsl(244, 38%, 16%);
  --p-soft-violet: hsl(277, 64%, 61%);

  --n-white: hsl(0, 0%, 100%);
  --n-slightly-transparent-white: hsla(0, 0%, 100%, 0.75);
  --n-slightly-transparent-white-2: hsla(0, 0%, 100%, 0.6);
}

/* Utilities */
.fw-400-Inter {
  font-weight: 400;
  font-family: 'Inter', sans-serif;
}

.fw-700-Inter {
  font-weight: 700;
  font-family: 'Inter', sans-serif;
}

.fw-400-Lexend {
  font-weight: 400;
  font-family: 'Lexend Deca', sans-serif;
}
```

Using the given styles in figma, I used `root variables` and created utility classes for the font weights. I added the primary, and secondary colors to the root variables, and the `font-weight` and `font-family` as utility classes.

#### Mobile

I started of with a mobile first approach where I designed the website for mobile screens first.

```css
body {
  background-color: var(--p-very-dark-blue);

  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;

  font-size: 15px;
  font-family: Inter, sans-serif;
}

/* Main */
main {
  background-color: var(--p-dark-desaturated-blue);
  margin: 5.5rem 1.5rem;

  border-radius: 0.5rem;
}
```

I started off by centering the container, using `flex-box`, in the middle and adding the background color. I've also added font-size and font-family to the body. I have also changed the background color of the main container and added rounded corners to the container.

```css
img {
  width: 100%;
  height: 100%;

  border-radius: 8px 8px 0px 0px;
}

.image {
  position: relative;
}

.image:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  opacity: 0.7511;
  background-color: #ab5cdb;
  mix-blend-mode: multiply;
}
```

Next, I styled the image by making sure the image is 100% in both `width` and `height`. Then I made the image's position `relative` to change color by adding `mix-blend-mode`.

```css
/* Contents */
.title {
  margin: 2rem 2rem 1rem 2rem;

  color: var(--n-white);
  font-size: 1.75rem;
  text-align: center;
  line-height: 2rem;
}

.text-color {
  color: var(--p-soft-violet);
}

.info {
  margin: 0 2rem 2.5rem 2rem;

  color: var(--n-slightly-transparent-white);
  text-align: center;
  font-size: 0.94rem;
  line-height: 1.56rem;
}

/* Data */

.data {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.data > div > h3 {
  color: #fff;
  text-align: center;
  font-size: 1.5rem;
  font-weight: 700;
}

.data > div > p {
  color: #fff;
  text-align: center;
  font-family: Lexend Deca, sans-serif;
  font-size: 0.75rem;
  font-weight: 400;
  line-height: 1.56rem;
  letter-spacing: 0.0625rem;
  opacity: 0.6;
  margin-bottom: 1.5rem;
}

.queries {
  margin-bottom: 2rem;
}
```

Next, I added styling to the content by targeting the heading, paragraph and the data. Following the figma, I added the `rem` to the `font-size`, `margins`, and more.

#### Website

```css
@media screen and (min-width: 1100px) {
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: row;

    width: 69.38rem;
    height: 27.88rem;
  }
}
```

I then used `media query` to design the website for desktop sizes. By changing the `flex-direction` to row, and changing the width and heights.

I've then updated the styling for the contents, header, paragraph, and data following the figma design.

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

## Author

- Frontend Mentor - [@SLuo490](https://www.frontendmentor.io/profile/SLuo490)
- LinkedIn - [@SLuo490](https://www.linkedin.com/in/sluo490/)
- Github - [@SLuo490](https://github.com/SLuo490)
