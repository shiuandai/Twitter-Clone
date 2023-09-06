<h2 align="center">Twitter-Clone</h2>

<p align="center">
  <em> The twitter clone is my ninth project of Scrimba Front-End course, in this course I build the duplication of twitter from scratch and structure the code to finish the layout design.</em>
</p>

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com) [![Join the chat at https://gitter.im/Front-End-Checklist/Front-End-Design-Checklist](https://badges.gitter.im/Front-End-Checklist/Front-End-Design-Checklist.svg)](https://gitter.im/Front-End-Checklist/Front-End-Design-Checklist) [![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

## Table of Contents
* **[1. Design requirements](#1---design-requirements)**
	* [1.1 Structure Design](#11---grid-system)
	* [1.2 Colors](#12---colors)
	* [1.3 Fonts and texts](#13---fonts-and-texts)
	* [1.4 Publish files](#14---publish-files)
* **[2. Pre-work phases](#2---pre-work-phases)**
	* [2.1 Refine the project using CSS](#21---refine-the-project-using-CSS)
* **[3. Before production](#3---before-production)**

---

> The **Twitter Clone** is my ninth static website, building the small features step by step and make sure the code is easily to read.

I start the Scrimba Module 5 course- Essential JavaScript Concepts and learn how to use advanced JavaScript. At the end of the course, I follow the instruction to finish the Twitter Clone, take a look at the → [Twitter Clone](https://shiuandai.github.io/Twitter-Clone/).

## How I start the project?

* Learn how to set the textarea for user to input their replies, and render the replies. 
* Insert the icons from the "Font Awesome CDN" website.
* Increase & Decrease the number of the "likes" and "tweets" icons.
* Change the color of icons when clicking.
* Render the replies by getting their UUID, and improving the UX.

---

## 1. - Create a new tweet

Designing a twitter clone social media website requires following some rules and taking into consideration about each scrum tutorial. This project can be split into several small parts.

### 1.1 - Add the textarea

* [ ] Take control of the data from **Textarea** when clicking button, then make sure the size of textarea fixed.
	> ℹ️ [TEXTAREA] GET to know more about the element. → [W3School](https://www.w3schools.com/tags/tag_textarea.asp)

* [ ] **resize for textarea element**. 

```css
textarea{
    border: none;
    padding: 10px;
    margin: 0 0 20px 0;
    height: 60px;
    width: 100%;
    font-size: 20px;
    line-height: 30px;
    resize: none;   //keeps textarea the same size
}
```

**[⬆ back to top](#table-of-contents)**

### 1.2 - “For each” method to iterate the array

Look through how to use .forEach() → [.forEach()](https://www.w3schools.com/jsref/jsref_foreach.asp)

```js example
const characters = [
    {
        title: 'Ninja',
        emoji: '🥷',
        powers: ['agility', 'jsstealth', 'aggression'],
    },
    {
        title: 'Sorcerer',
        emoji: '🧙',
        powers: ['magic', 'invisibility', 'necromancy'],
    },
    { 
        title: 'Ogre',
        emoji: '👹',
        powers: ['power', 'stamina', 'shapeshifting'],
    },  
    { 
        title: 'Unicorn',
        emoji: '🦄',
        powers: [ 'flight', 'power', 'purity'],
    }
]

characters.forEach(function(character){   //The purpose of using forEach is to make the code easy to read and simple.
    console.log(character)
//The result shows below.
//{title: "Ninja", emoji: "🥷", powers: ["agility", "stealth", "aggression"]}
//{title: "Sorcerer", emoji: "🧙", powers: ["magic", "invisibility", "necromancy"]}
//{title: "Ogre", emoji: "👹", powers: ["power", "stamina", "shapeshifting"]}
//{title: "Unicorn", emoji: "🦄", powers: ["flight", "power", "purity"]}
```

**[⬆ back to top](#table-of-contents)**

### 1.3 - Fonts and texts

Fonts are an essential part of every design.

It is recommended to organize the font size and style in the design process. There are several websites where the designer can download the font. ([Google font](https://fonts.google.com/)).

* [ ] Using the technique **@font-face** in CSS, the link is embedded in the CSS. 

  __Resources:__
	* 📖 [Using @font-face | CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] The **Web Safe Fonts** is an important concept. Web-safe fonts are fonts that are pre-installed by many operating systems. While not all systems have the same fonts installed, you can use a web-safe font stack to choose several fonts that look similar and are installed on the various systems that you want to support.

**[⬆ back to top](#table-of-contents)**


### 1.4 - Publish files

* [ ] How to host your website, there are several ways. 1. **Netlify** provides next-generation web hosting and automation that's very affordable. Is can be integrated with Github for publishing the web easily. The alternative is using Github Page, my way is to use Github Page. → [Comparison of Github Page and Netlify](https://www.freecodecamp.org/news/publish-your-website-netlify-github/) 

## 2. - Pre-work phases

### 2.1 - Refine the project using CSS

It is recommended to master the **flex-box** concept, it usually combines with different **Property** like **flex-direction: column; align-items: center;** .

Define what condition to use the flex-box, it influences how the content displayed.

⚠️ *When using the flex-box, it is good to use the property of "gap" rather than "margin" to generate the gap.*

## 3. - Before production

Before launching your website, be sure to review all your code and make sure the text layout and comment it's easy to read for another programmer.

**[⬆ back to top](#table-of-contents)**

---

## Author

**[Shiuan Dai](https://www.linkedin.com/in/shiuandai/)**

**[⬆ back to top](#table-of-contents)**


[6]:	https://guideguide.me/
[7]:	https://www.sketchapp.com/docs/canvas/rulers-guides-grids/
[8]:	https://getbootstrap.com/docs/4.0/layout/grid/
[9]:	http://flexboxgrid.com/
[10]: https://css-tricks.com/dont-overthink-it-grids/
[11]:	https://www.lifewire.com/aco-file-2619477
[16]:	http://bradfrost.com/blog/post/atomic-web-design/
[22]:	https://js.libhunt.com/
[23]:	https://bestof.js.org/
[28]:	https://gitter.im/Front-End-Checklist/Front-End-Design-Checklist
