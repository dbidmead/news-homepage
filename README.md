# Frontend Mentor - News homepage solution

This is a solution to the [News homepage challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/news-homepage-H6SWTa1MFl). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [The challenge](#the-challenge)
- [Links](#links)
- [Built with](#built-with)
- [What I learned](#what-i-learned)
- [Author](#author)

## The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

## Links

- Solution URL: [https://dbidmead.github.io/news-homepage](https://dbidmead.github.io/news-homepage)

## Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- JS (toggle mobile menu)

## What I learned

### Cool hamburger icon animation to reuse for the future

```html
<div class="hamburger">
  <div class="bar" id="a"></div>
  <div class="bar" id="b"></div>
  <div class="bar" id="c"></div>
</div>
```

```css
.hamburger {
        display: flex;
        flex-direction: column;
        width: 4rem;
        height: 4rem;
        position: relative;
        z-index: 100;
    }

    .bar {
        position: absolute;
        left: 25%;
        top: 50%;
        width: 3rem;
        height: 3px;
        background-color: black;
        transition: all 400ms cubic-bezier(.84,.06,.52,1.8);
    }

    #a {
        transform: translateY(-0.5rem);
    } 

    #c {
        transform: translateY(0.5rem);
    }

    .active>#a {
        transform: rotate(45deg);
    }

    .active>#b {
        opacity: 0;
    }

    .active>#c {
        transform: rotate(-45deg);
    }
```

```js
const hamburger = document.querySelector('.hamburger');

hamburger.addEventListener('click', () => {
    hamburger.classList.toggle('active');
})
```

### CSS grid is awesome and easy to use

For a simple 3x3 grid with equal-sized columns and row sizes of 300px, 200px, 100px and 25px gap between all grid cells
```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 300px 200px 100px;
  gap: 25px;
}
```

To make a div span 2 columns within its row, specify the grid LINE it starts at and grid LINE it ends at
```css
.cell {
  grid-column: 1 / 3;
}
```
Note that grid-row works the same way. The divs can still all be styled using display flex.

## Author

- GitHub - [@dbidmead](https://github.com/dbidmead)
- Frontend Mentor - [@dbidmead](https://www.frontendmentor.io/profile/dbidmead)
