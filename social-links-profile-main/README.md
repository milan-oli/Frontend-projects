# Frontend Mentor - Social links profile solution

This is a solution to the [Social links profile challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/social-links-profile-UG32l9m6dQ). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- See hover and focus states for all interactive elements on the page

### Screenshot

![Social links profile solution screenshot](./preview.jpg)

### Links

- Repository URL: [github.com/milan-oli/Frontend-projects/tree/main/social-links-profile-main](https://github.com/milan-oli/Frontend-projects/tree/main/social-links-profile-main)
- Live Site URL: [milan-oli.github.io/Frontend-projects/social-links-profile-main/](https://milan-oli.github.io/Frontend-projects/social-links-profile-main/)

## My process

### Built with

- Semantic HTML5 markup (`ul`/`li`/`a` for real navigation links)
- CSS custom properties
- Flexbox, including a reusable `.flex` utility class
- `clamp()` for fluid, responsive sizing
- Mobile-first workflow
- Google Fonts (Inter)

### What I learned

This project reinforced a mistake I'd made before: setting an explicit `color` directly on a child element can silently override a parent's hover/focus color change, because of CSS specificity. My links had their own `color` set, so when I tried to change the text color on `li:hover`, nothing visibly happened. The fix was to target the link directly instead of relying on inheritance:

```css
li:hover a,
li:focus-within a {
  color: var(--primary-Grey700);
}
```

I also practiced pulling repeated Flexbox declarations (`display: flex; flex-direction: column; justify-content: center; align-items: center;`) into a single reusable `.flex` class instead of repeating them across `body`, `.container`, `main`, `.detail`, and `ul`. It's a small refactor, but it made the CSS noticeably easier to scan.

Lastly, I made sure every interactive element — not just the five social links, but also the footer's attribution links — had visible hover and focus states, since the brief specifically called that out as a requirement for "all interactive elements on the page," not just the main content.

### Continued development

- Keep watching for the specificity trap where a child's explicit style silently blocks a parent's hover/focus rule
- Get more practice with CSS Grid, since Flexbox is still my main layout tool so far
- Continue testing every project down to a 320px viewport width, per the style guide's accessibility note

### AI Collaboration

I used Claude (Anthropic) throughout this project.

- **How I used it**: I wrote all the HTML and CSS myself, then shared it with Claude for review against the design and style guide.
- **What it helped with**: catching the color-inheritance bug on hover, spotting that the footer links were missing hover/focus states even though the main links had them, and confirming my font sizes/weights matched the style guide exactly.
- **What worked well**: reviewing code after I wrote it, rather than having it generated for me, meant I still had to understand and apply each fix myself.

## Author

- GitHub - [@milan-oli](https://github.com/milan-oli)
- Frontend Mentor - [@milan-oli](https://www.frontendmentor.io/profile/milan-oli)
