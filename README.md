# Frontend Mentor - Results summary component solution

This is a solution to the [Results summary component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/results-summary-component-CE_K6s0maV). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

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

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

![Desktop screenshot](./desktop_screenshot.png)
![Mobile screenshot](./mobile_screenshot.png)

### Links

- Solution URL: [https://www.frontendmentor.io/solutions/result-summary-component-hO9O6l5wee](https://www.frontendmentor.io/solutions/result-summary-component-hO9O6l5wee)
- Live Site URL: [https://reversalgm.github.io/results-summary-component/](https://reversalgm.github.io/results-summary-component/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learned

I used flexbox to do most of the heavy lifting when it comes to layout and responsive design. I used a media query to at the 600px breakpoint to transition from the mobile design to the desktop design. The component size does not change much across devices, only the layout, So I mostly used the rem unit and the only piece of responsive typography is the user's score in the circle, made responsive using clamp() and viewpoint units. I also tried using the BEM naming system for css classes.

I am quite proud of being able to create the corner borders for each item in the summary section. It was quite a bit of work for such a small detail. I created 4 small, square, divs that are absolutely positioned at each corner. Then I applied a corner border to each of the divs.

```html
<li class="list-item list-item--yellow">
  <img
    class="list-item__icon"
    src="assets/images/icon-memory.svg"
    alt="reaction-icon"
  />
  <div class="list-item__text">Memory</div>
  <div class="list-item__score"><strong>92</strong> / 100</div>
  <!-- Corner borders -->
  <div class="list-item__corner-border list-item__corner-border--topleft"></div>
  <div
    class="list-item__corner-border list-item__corner-border--topright"
  ></div>
  <div class="list-item__corner-border list-item__corner-border--botleft"></div>
  <div
    class="list-item__corner-border list-item__corner-border--botright"
  ></div>
</li>
```

```css
.list-item {
  position: relative;
  display: flex;
  align-items: center;

  padding: 1rem;
  margin: 1rem 0;

  border-radius: 0.75rem;
  font-weight: 700;
}

.list-item__corner-border {
  position: absolute;
  width: 0.75rem;
  height: 0.75rem;
}

.list-item__corner-border--topleft {
  top: 0;
  left: 0;
  border-left: 0.1rem solid var(--pale-blue);
  border-top: 0.1rem solid var(--pale-blue);
  border-top-left-radius: 0.75rem;
  border-color: inherit;
}

.list-item__corner-border--topright {
  top: 0;
  right: 0;
  border-right: 0.1rem solid var(--pale-blue);
  border-top: 0.1rem solid var(--pale-blue);
  border-top-right-radius: 0.75rem;
  border-color: inherit;
}

.list-item__corner-border--botleft {
  bottom: 0;
  left: 0;
  border-left: 0.1rem solid var(--pale-blue);
  border-bottom: 0.1rem solid var(--pale-blue);
  border-bottom-left-radius: 0.75rem;
  border-color: inherit;
}

.list-item__corner-border--botright {
  bottom: 0;
  right: 0;
  border-right: 0.1rem solid var(--pale-blue);
  border-bottom: 0.1rem solid var(--pale-blue);
  border-bottom-right-radius: 0.75rem;
  border-color: inherit;
}

.list-item__icon {
  margin-right: 0.5rem;
}

.list-item__text {
  flex-grow: 1;
}

.list-item__score {
  color: var(--dark-gray-blue-transparent);
}
.list-item__score > strong {
  color: var(--dark-gray-blue);
}

.list-item--red {
  color: var(--light-red);
  background-color: var(--light-red-transparent);
  border-color: var(--light-red-transparent);
}
```

### Continued development

The final product sufficiently resembles the original design and looks well on most devices. However, I would like to continue improving my responsive design skills and focus on responsive typography especially.
