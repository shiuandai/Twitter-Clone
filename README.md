<h2 align="center">Twitter-Clone</h2>

<p align="center">
  <em> The twitter clone is my ninth project of Scrimba Front-End course, in this course I build the duplication of twitter from scratch and structure the code to finish the layout design.</em>
</p>

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com) [![Join the chat at https://gitter.im/Front-End-Checklist/Front-End-Design-Checklist](https://badges.gitter.im/Front-End-Checklist/Front-End-Design-Checklist.svg)](https://gitter.im/Front-End-Checklist/Front-End-Design-Checklist) [![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

## Table of Contents
* **[1. Create a new tweet](#1---Create-a-new-tweet)**
	* [1.1 Add the textarea](#11---Add-the-textarea)
	* [1.2 For each method to iterate the array](#12---For-each-method-to-iterate-the-array)
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

### 1.2 - For each method to iterate the array

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

characters.forEach(function(character){   //The purpose of using forEach is to make the code easy to read.
    console.log(character)
//The result shows below.
//{title: "Ninja", emoji: "🥷", powers: ["agility", "stealth", "aggression"]}
//{title: "Sorcerer", emoji: "🧙", powers: ["magic", "invisibility", "necromancy"]}
//{title: "Ogre", emoji: "👹", powers: ["power", "stamina", "shapeshifting"]}
//{title: "Unicorn", emoji: "🦄", powers: ["flight", "power", "purity"]}
```

**[⬆ back to top](#table-of-contents)**


## 2. - Control the icons

### 2.1 - CDN

Explaination why should we use CDN. → [AWS](https://aws.amazon.com/tw/what-is/cdn/)
The icon examples which we can get from here. → [FONT-AWESOME-CDN](https://cdnjs.com/libraries/font-awesome)

⚠️ *The first step to use the CDN, copy code and paste the link into <link> then paste “class” details into the section*

```js
<section class="icons-bar">
     <i class="fa-solid fa-house"></i>
     <i class="fa-solid fa-location-dot"></i>  //Get icon resource class name //Have to understand the concept of the data attribute.
     <i class="fa-regular fa-envelope"></i>
     <i class="fa-regular fa-calendar-days"></i>   //This is the example of how to use the data-attribute in the class.
</section>
```

⚠️ *The defination of the **Data Attribute**: deta-unique-name="your data"*

### 2.2 - Get value of data-attribute 

```js
document.addEventListener('click', function(e) {
		if (e.target.dataset.share){
    			console.log(e.target.dataset.share)   //output is image-1, review the code above，after clicking: output shows "image"
		}     //if return T then the data-share inside data element   //The output is DOMStringMap {share: "image-1"}
})
```

### 2.3 - Find the tweet obj & increase the "like" number 

```js
import { tweetsData } from './data.js'
const tweetInput = document.getElementById('tweet-input')
const tweetBtn = document.getElementById('tweet-btn')

tweetBtn.addEventListener('click', function(){
    console.log(tweetInput.value)
})

document.addEventListener('click', function(e){
    if(e.target.dataset.like){
       handleLikeClick(e.target.dataset.like) 
    }
})

function handleLikeClick(tweetId){
    const targetTweetObj = tweetsData.filter(function(tweet){
        return tweet.uuid === tweetId  //if the tweet id is the same of the loop id，then return true
    })[0]  //The output is object, not array
    targetTweetObj.likes++  //increase the like number when click
    console.log(tweetsData)
}
```

### 2.4 - Flip the boolean to control the like & dislike

```js
//Make sure to listen to the button
document.addEventListener('click', function(e){
    if(e.target.dataset.like){
       handleLikeClick(e.target.dataset.like) 
    }

function handleLikeClick(tweetId){ 
    const targetTweetObj = tweetsData.filter(function(tweet){
        return tweet.uuid === tweetId
    })[0]

    if (targetTweetObj.isLiked){
        targetTweetObj.likes--
    }
    else{
        targetTweetObj.likes++ 
    }
    targetTweetObj.isLiked = !targetTweetObj.isLiked   //The goal is to flip the boolean.
    render()
}
```

### 2.5 - Conditionally Render CSS 

```js/ Make heart icon turns to red
const galleryContainer = document.getElementById('gallery-container')

let isLiked = false
let isShared = false


document.addEventListener('click', function(e){
    if(e.target.dataset.heart){
        isLiked = !isLiked  //flip the boolean short-hand
        render()
    }
    else if(e.target.dataset.share){
        isShared = !isShared  //flip the boolean short-hand
        render()
    }
})

function render(){ 
    
    let heartClass = ''  //剛開始是empty class所以沒有class在裡面
    let shareClass = ''
    
    if(isLiked){
        heartClass = 'liked'  //if "isLiked" is true then set up the Class to "liked"
    }
    
    if(isShared){
        shareClass = 'shared'   
    }
       
    let imageHtml = `
    		<div id="image-1" class="img-container">
			<img src="dino2.jpeg" alt="Man in front of dinosaur">
			<div class="social-icons-container">
				<i class="fa-solid fa-heart ${heartClass}" data-heart="image-1"></i>
				<i class="fa-solid fa-share ${shareClass}" data-share="image-1"></i>
			</div>
    `
    galleryContainer.innerHTML = imageHtml
}

render()
```

``` html
<section class="gallery-container" id="gallery-container">
</section>
```

```css
.liked{
    color: #f80000; /* red */
}

.shared{
    color: limegreen; 
}
```

## 3. - Replies setup

### 3.1 - Get the UUID of replies

```js
function getFeedHtml(){
    let feedHtml = ``
    
    tweetsData.forEach(function(tweet){  //loop through the object
        
        let likeIconClass = ''
        
        if (tweet.isLiked){
            likeIconClass = 'liked'
        }
        
        let retweetIconClass = ''
        
        if (tweet.isRetweeted){
            retweetIconClass = 'retweeted'
        }
        
        if(tweet.replies.length > 0){
            console.log(tweet.uuid)   //check the length of the tweet if there is any replies then output its UUID
        }
}
```

### 3.2 - Provide each reply unique UUID

```js
import { v4 as uuidv4 } from 'https://jspm.dev/uuid'; //import the UUID JS 
  
const cars = [
    {
    brand: 'Nissan',
    model: 'Leaf',
    price: 3000,
    uuid: '4fb2b6b7-c7ee-4c80-8de1-390e89f43d7f'
    }, 
    {
    brand: 'Toyota',
    model: 'Prius',
    price: 6000,
    uuid: '82a13f62-d239-46a2-a94f-020189338e1a'
    }, 
] 

cars.push({
    brand: 'Tesla',
    model: 'Model S',
    price: '🤦‍♂️',
    uuid: uuidv4()  //Input function
})

console.log(cars)
```

```html
<html>
    <head>
        <link rel="stylesheet" href="index.css">
    </head>
    <body>
        <script src="index.js" type="module"></script>  //setting to module
    </body>
</html>
```

### 3.3 - Push the new tweet to the dataset

```js
function handleTweetBtnClick(){
    tweetsData.unshift({   //tweet the post in the beginning of the object
        handle: `@Scrimba`,
        profilePic: `images/scrimbalogo.png`,
        likes: 0,
        retweets: 0,
        tweetText: tweetInput.value,
        replies: [],
        isLiked: false,
        isRetweeted: false,
        uuid: uuidv4()
    })
    render()    
}
```
### 3.4 - Improve the UX

```
function handleTweetBtnClick(){
    const tweetInput = document.getElementById('tweet-input')
    if(tweetInput.value){       //If the value in the textarea exists then push the data into the array.
        tweetsData.unshift({
            handle: `@Scrimba`,
            profilePic: `images/scrimbalogo.png`,
            likes: 0,
            retweets: 0,
            tweetText: tweetInput.value,
            replies: [],
            isLiked: false,
            isRetweeted: false,
            uuid: uuidv4()
        })
    render()
    tweetInput.value = ''
    }
}
```

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
