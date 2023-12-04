# Frontend Mentor - Results summary component solution
## Table of contents
- [Overview](#overview)
  - [Links](#links)
  - [Built with](#built-with)
- [What I learned (Reflection)](#what-i-learned)
    - [Variables & Naming Things](#the-colors)
    - [Themes & Maps](#the-colors)
    - [The Colors](#the-colors)
- [What next?](#what-next)

## Overview
This is my attempt at the [Results summary component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/results-summary-component-CE_K6s0maV) - a place with a ton of web development & design challenges. In fact, this is my first challenge.

### Links
- [View Page Here](https://geoffsg.github.io/results-summary-component/)

### Built with
- HTML5
- CSS; SASS/SCSS
- Flexbox

## What I learned (Reflection)
### Variables & Naming Things
For this challenge, I really tried getting the hang of using variables. One particular variable `$base-padding` turned out to be a universal variable for sizing elements. This highlights a lesson I'm learning; naming stuff.

I am aware of naming a variable based on its purpose, which can be tricky when one variable have many purposes. Perhaps, to reflect, this `$base-padding` variable could be called `$base-size` or something similar. I may go back and change this, or keep it here as a mark of reflection and outlining faults to improve n remind myself later - or its a point of learning for you?

### Themes & Maps
Another point of practice was using maps (or 2D arrays in SCSS) for creating the color schemes (or themes, as I called them) of the separate data-bars. 

```scss
$summary-themes: (
    'reaction': (
        'bg': hsla(0, 100%, 67%, .125),
        'fg': hsl(0, 100%, 67%)
    ),
    'memory': (
        'bg': hsla(39, 100%, 56%, .125),
        'fg': hsl(39, 100%, 56%)
    ),
    'verbal': (
        'bg': hsla(166, 100%, 37%, .125),
        'fg': hsl(166, 100%, 37%)
    ),
    'visual': (
        'bg': hsla(234, 85%, 45%, .125),
        'fg': hsl(234, 85%, 45%)
    )
);
```

This was so I could do something like this...

```scss
@each $summary, $color in $summary-themes {
    &.summary-#{$summary} {
        background-color: map-get($color, 'bg');
        color:  map-get($color, 'fg');
    }
}
```

A for-each loop that goes through each theme and apply their properties. In this case, the `background-color` and `color`.


## What next?
My goal for these challenges is to develop 