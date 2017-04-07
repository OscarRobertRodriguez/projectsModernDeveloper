---
layout: post
title:  "Intro to Responsive Design"
---

<br>

<h1 style="color:#3CCAE6">Project Assignment 1: Creating a Responsive Accordion Menu</h1>

## Media Queries code

```css 
/* media */

@media screen and (max-width:360px) and (orientation: portrait) {

    label {
        margin-top: 2px;
        border:1px solid black;
        padding:10px;
        font-size:20px;
        color:#641C19;
        letter-spacing: 1px;
        font-weight: 500;
        font-family: sans-serif;
        background-color:lightblue;
        text-transform:uppercase;
        transition: background-color .5s ease-out ;
        display: block;
        position: relative;
        cursor:pointer;
    }

    [type="radio"]:checked ~ label {
        color: #fff;
        background-color:darkblue;
        font-weight:600;
    }

    .accordion label:hover  {
        color: #fff;
        background-color:darkblue;
        font-weight:600;
    }
}


@media screen and (min-width:361px) and (max-width:600px) and (orientation:portrait) {
    label {
        margin-top: 2px;
        border:1px solid black;
        padding:10px;
        font-size:20px;
        color:#641C19;
        letter-spacing: 1px;
        font-weight: 500;
        font-family: sans-serif;
        background-color:lightgreen;
        text-transform:uppercase;
        transition: background-color .5s ease-out ;
        display: block;
        position: relative;
        cursor:pointer;
    }

    [type="radio"]:checked ~ label {
        color: #fff;
        background-color:darkgreen;
        font-weight:600;
    }

    .accordion label:hover  {
        color: #fff;
        background-color:darkgreen;
        font-weight:600;
    }
}

@media screen and (min-width:601px) and (max-width:1024px)  {
    label {
        margin-top: 2px;
        border:1px solid black;
        padding:10px;
        font-size:20px;
        color:#fff;
        letter-spacing: 1px;
        font-weight: 500;
        font-family: sans-serif;
        background-color:black;
        text-transform:uppercase;
        transition: background-color .5s ease-out ;
        display: block;
        position: relative;
        cursor:pointer;
    }

    [type="radio"]:checked ~ label {
        color: black;
        background-color:#fff;
        font-weight:600;
    }

    .accordion label:hover  {
        color: black;
        background-color:#fff;
        font-weight:600;
    }
}
```

<br>

## Result<br>
For the purpose of this project I left out the portrait orientation so that it will work on desktop resizing. 
<p data-height="542" data-theme-id="0" data-slug-hash="oBXpXW" data-default-tab="result" data-user="nopity" data-embed-version="2" data-pen-title="accordian tab" class="codepen">See the Pen <a href="http://codepen.io/nopity/pen/oBXpXW/">accordian tab</a> by oscar (<a href="http://codepen.io/nopity">@nopity</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>
<br>

<h1 style="color:#3CCAE6">Project Assignment 2: Making Previous Projects Responsive</h1>


1.[front-page of personal website ](https://oscarrobertrodriguez.github.io/)
2.