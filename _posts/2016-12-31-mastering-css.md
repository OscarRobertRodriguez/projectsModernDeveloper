---
layout: post
title:  "Mastering CSS"
---

<style>
table {
    border-radius: 2px;
    margin: 20px 0px;
    width: 100%;
    border-collapse: collapse;
    border-spacing: 0;
}


th, td {
    border:1px solid #dedfe9;
    text-align:center;
    padding:10px;
}



.card {
    height: 300px;
    width: 600px;
    position: relative;
    -webkit-perspective: 300px;
            perspective: 300px;
    -webkit-transition: -webkit-transform 1s;
    
   
    margin: 50px auto;
}

.front, .back {
    position: absolute;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    background-color: orange;
    -webkit-backface-visibility: hidden;
            backface-visibility: hidden;
    -webkit-transition: 1s;
    transition: 1s;
}

.back {
    -webkit-transform: rotateX(180deg);
            transform: rotateX(180deg);
    background: url("../images/backPhoto.jpg") no-repeat;
    background-size: cover;
}

/*Front of Card*/

.front {
    background: url("../images/bg1.png") no-repeat;
    background-size: cover;
}

.card:hover .front {
    -webkit-transform: rotateX(10deg);
            transform: rotateX(10deg);
    box-shadow: 0 15px 15px lightgrey;
}

.card:hover .back {
    box-shadow: 20px 15px 15px lightgrey;
}

/* animation code */

[type="radio"] {
    display: none;
}

[type="radio"]:checked ~ .front {
    -webkit-transform: rotateX(-180deg);
            transform: rotateX(-180deg);
}

[type="radio"]:checked ~ .back {
    -webkit-transform:rotateX(0deg);
            transform:rotateX(0deg);
}

/*end animation */

.frontIntro {
    position: relative;
}

.frontIntro h1 {
    padding: 10px;
    margin-left: 10px;
    color: #fff;
    font-size: 45px;
    letter-spacing: 1px;
    font-family: Arial, serif;
}

.aboutMe, .bookmarkFront p {
    font-family: sans-serif;
    font-size: 14px;
    font-weight: 100;
    color: #fff;
    padding: 0;
    margin-left: 22px;
    top: 70px;
    left: 25px;
}

p.aboutMe {
  margin-right: 80px;
}

.frontIntro > p:nth-child(2) {
    position: absolute;
    font-size: 16px;
    font-family: sans-serif;
    font-weight: 100;
    color: lightgray;
    padding: 0;
    margin: 0;
    top: 70px;
    left: 25px;
}

.frontIntro img {
    position: absolute;
    top: 0;
    right: 40px;
    cursor: pointer;
}

.frontIntro img:hover {
    background-color: #fff;
    border-radius: 5px;
    -webkit-transform: rotateY(180deg);
            transform: rotateY(180deg);
}

.front ul {
    margin: 30px 0 0;
    padding: 0;
    list-style: none;

}

.front li {
    display: inline-block;
    margin: 0 10px 0 24px;
}

.front a {
    font-variant: small-caps;
    font-size: 15px;
    text-decoration: none;
    color: #C464E5;
}

.front a:hover {
    color: #d47ec3;
}

.bookmarkFront {
    position: absolute;
    bottom: 4px;
    left: 20px;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    margin-left: 4px;
    width: 180px;
    -webkit-box-pack: justify;
        -ms-flex-pack: justify;
            justify-content: space-between;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
}

.bookmarkFront img {
    height: 50px;
    width: 50px;
}

.socialMediaIcons {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    width: 250px;
    height:45px;
    -ms-flex-pack: distribute;
        justify-content: space-around;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    position: absolute;
    bottom: 15px;
    right: 30px;
}


.socialMediaIcons img:hover {
    border-radius:50%;
    border:3px solid #fff;
}

/* flip code*/







/*Back Of Card*/


.back img {
    position: absolute;
    top: 30px;
    right: 40px;
    cursor: pointer;
}

.back img:hover {
    background-color: #fff;
    border-radius: 5px;
    -webkit-transform: rotateY(180deg);
            transform: rotateY(180deg);
}

#flipToFront[type="radio"]:checked ~ .front {
    -webkit-transform: rotateX(0deg);
            transform: rotateX(0deg);
}

#flipToFront[type="radio"]:checked ~ .back {
    -webkit-transform: rotateX(180deg);
            transform: rotateX(180deg);
}


.bottomName {
    position: absolute;
    bottom:10px;
    left:20px;
    background-color: #EFEDE0;
    opacity:0.8;
    border-radius:5px;
}

.bottomName p {
    color:#7C30D2;
    padding:5px;
    margin: 0;
}




</style>

<h1 style="color:#3CCAE6">Project Assignment 1: Create a Tabs Component</h1>


## <input type="checkbox" checked> Task 1: Creating the HTML Markup

```html 

<div class="tabComponent">
  <!-- Insert code to create tabbed components here -->

  <div class="tab">
    <input type="radio" id="tab-1" name="tab" />
    <label for="tab-1">home decor</label>

    <div class="content"><a href="#">Browse through our list of Home Decor Items</a></div>
  </div>

  <div class="tab">
    <input type="radio" id="tab-2" name="tab" />
    <label for="tab-2">furniture</label>

    <div class="content"><a href="#">Flash Sale on Living Room and Bedroom Furniture</a></div>
  </div>

  <div class="tab">
    <input type="radio" id="tab-3" name="tab" />
    <label for="tab-3">kitchen</label>

    <div class="content"><a href="#">Bring the best out of the masterchef in you!!</a></div>
  </div>

  <div class="tab">
    <input type="radio" id="clearance" name="tab" />
    <label for="clearance">Clearance</label>

    <div class="content"><a href="#">Red hot deals at affordable prices.<br>Check out our clearance section for more details.</a></div>
  </div>

</div>
```


## <input type="checkbox" checked> Task 2: Identifying and Adding CSS Selectors

```html 
body {
  box-sizing: border-box;
}

.tabComponent {
  position: relative;
  min-height: 200px;
  margin: 50px auto;
  width: 600px;
}

.tab {
  float: left;
}

div.tabComponent input {
  display: none;
}

div.tabComponent label {
  position:relative;
  left:50px;
  padding: 10px 15px 5px 15px;
  background-color:#C97D7B;
  font-size: 20px;
  width: auto;
  height:auto;
  text-transform: capitalize;
  border: 1px solid #ccc;
  letter-spacing:1px;
  font-family: sans-serif;
  border-top-left-radius: 80px;
  border-top-right-radius: 80px;
  margin-left: 1px;
}

.content {
  position: absolute;
  width: 800px;
  top: 27px;
  left: -80px;
  right: 0;
  bottom: 0;
  padding: 20px;
  overflow: hidden;
  height: 200px;
  background:url(https://s29.postimg.org/lxj1l04o7/couch.png) no-repeat;
  background-size: 800px;
}

.content > a {
  position:absolute;
  font-size:20px;
  left:180px;
  text-decoration:none;
  color:#fff;
  line-height:30px;
  text-align:center;
  font-variant:small-caps;
  letter-spacing:1px;
}


[type="radio"]:checked ~ label {
  background: #A22522;
  color: white;
  border-bottom: 1px solid #ccc;
  font-size:17px;
  z-index: 5;
}

[type="radio"]:checked ~ label ~ .content {
  z-index: 1;
}
```



<table>
<thead>
<tr>
    <th>Selector#</th>
    <th>CSS Selector</th>
    <th>Explanation</th>
    <th>Purpose</th>
    <th>HTML element(s) selected</th>
</tr>
</thead>
<tbody>

<tr>
<td>    
1
</td>
<td>
div.tabComponent input
</td>
<td>The type selector div is combined with the class selector .tabComponent to select the outermost div with class="tabComponent". This composite selector is then combined with another type selector input to select all the input type elements. </td>
<td>To apply style rules to the radio button input type elements</td>
<td>Elements selected by this rule are the radio buttons with id="homeDecor", id="furniture" and id="kitchen".</td>
</tr>


<tr>
    <td>2</td>
    <td>body</td>
    <td>the type selector body selects all the tags within the body of the page</td>
    <td>To apply styles to all the elements with one selector</td>
    <td>The elements selected are are the elements that are children to the body</td>
</tr>

<tr>
    <td>3</td>
    <td>.tabComponent</td>
    <td>use the class selector with the name .tabComponent to select the wrapper around all the elements</td>
    <td>To center all the elements to middle</td>
    <td>Elements are all elements within .tabComponent div</td>
</tr>


<tr>
    <td>4</td>
    <td>.tab</td>
    <td>uses class selector to select all div with class of .tab</td>
    <td>Used to select all tabs and float them to the left</td>
    <td>Selects all divs with class .tab and all their children</td>
</tr>

<tr>
    <td>5</td>
    <td>div.tabComponent label</td>
    <td>use type selector of div and combine it with class selector .tabComponent then combined with another type selector of label</td>
    <td>Used to select all labels within the div with .tabComponent</td>
    <td>Elements selected are all label tags within the div with class .tabComponent</td>
</tr>

<tr>
    <td>6</td>
    <td>.content</td>
    <td>uses class selector of .content to target div</td>
    <td>Selects div and a tag in use to position and add background image of couch </td>
    <td>selects div and a tag within</td>
</tr>

<tr>
    <td>7</td>
    <td>.content > a</td>
    <td>use of class selector combined with the >(child selector) to target the a tag</td>
    <td>move the div with .content class with absolute positioning</td>
    <td>selects the a tag that is a child of the .content div</td>
</tr>

<tr>
    <td>8</td>
    <td>[type="radio"]:checked ~ label</td>
    <td>use the type selector of radio to target radio buttons then is combined with the pseudo-class selector of :checked to toggle on and off styles when radio button is selected this in turn is combined with the ~ symbol to select all labels that are sibling to the radio buttons. </td>
    <td>adds style to label when it is clicked on</td>
    <td>selects the label tags that are siblings to the radio inputs and at the same time targets the selected radio button</td>
</tr>

<tr>
    <td>9</td>
    <td>[type="radio"]:checked ~ label ~ .content</td>
    <td>An attribute selector is used to target all inputs of type radio then a pseudo-class selector is used to watch for a checked radio button. This is then combined with a sibling selector to target all .content divs that are siblings of the radio buttons.</td>
    <td>when the sibling radio button is clicked it will change to the .content div that is a sibling of that radio button and then uses the z-index to bring that above the background img and above the other .content divs</td>
    <td>selects the .content div when its sibling radio button is checked</td>
</tr>


</tbody>
</table>

## <input type="checkbox" checked> Task 3: Inserting CSS Style Rules

```css 
body {
  box-sizing: border-box;
}

.tabComponent {
  position: relative;
  min-height: 200px;
  margin: 50px auto;
  width: 600px;
}

.tab {
  float: left;
}

div.tabComponent input {
  display: none;
}

div.tabComponent label {
  position:relative;
  left:50px;
  padding: 10px 15px 5px 15px;
  background-color:#C97D7B;
  font-size: 20px;
  width: auto;
  height:auto;
  text-transform: capitalize;
  border: 1px solid #ccc;
  letter-spacing:1px;
  font-family: sans-serif;
  border-top-left-radius: 80px;
  border-top-right-radius: 80px;
  margin-left: 1px;
}

.content {
  position: absolute;
  width: 800px;
  top: 27px;
  left: -80px;
  right: 0;
  bottom: 0;
  padding: 20px;
  overflow: hidden;
  height: 200px;
  background:url(https://s29.postimg.org/lxj1l04o7/couch.png) no-repeat;
  background-size: 800px;
}

.content > a {
  position:absolute;
  font-size:20px;
  left:180px;
  text-decoration:none;
  color:#fff;
  line-height:30px;
  text-align:center;
  font-variant:small-caps;
  letter-spacing:1px;
}


[type="radio"]:checked ~ label {
  background: #A22522;
  color: white;
  border-bottom: 1px solid #ccc;
  font-size:17px;
  z-index: 2;
}

[type="radio"]:checked  ~ .content {
  z-index: 1;
}
```

## <input type="checkbox" checked> Task 5: Making the Tab Component Attractive

<p data-height="470" data-theme-id="0" data-slug-hash="EZYmzV" data-default-tab="result" data-user="nopity" data-embed-version="2" data-pen-title="Tab Component" class="codepen">See the Pen <a href="http://codepen.io/nopity/pen/EZYmzV/">Tab Component</a> by oscar (<a href="http://codepen.io/nopity">@nopity</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>


<br><br>
<h1 style="color:#3CCAE6">Project Assignment 2: Create an Accordion Component</h1>


## <input type="checkbox" checked> Task 1: Creating the HTML Markup

```html 
<div class="accordion">
  <ul>

    <!-- Item 1 -->
    <li>
      <input id="appetizers" type="radio" name="menu"/>
      <label for="appetizers">appetizers</label>
      <div class="content">
        <h3>Check our tasty apps!</h3>
        <h4>Happy hour menu - half off!!</h4>
        <p>Chicken Wings(6) - 5.99$</p>
        <p>Calamari - 7.99$</p>
        <p>Garlic breaded pickles - 4.59$</p>
      </div>
    </li>

    <!-- Item 2 -->
    <li>
      <input id="entrees" type="radio" name="menu"/>
      <label for="entrees">entrees</label>
      <div class="content">
        <h3>Check our tasty apps!</h3>
        <h4>Happy hour menu - half off!!</h4>
        <p>Chicken Wings(6) - 5.99$</p>
        <p>Calamari - 7.99$</p>
        <p>Garlic breaded pickles - 4.59$</p>
      </div>
    </li>

    <!-- Item 3 -->
    <li>
      <input id="desserts" type="radio" name="menu"/>
      <label for="desserts">desserts</label>
      <div class="content">
        <h3>Check our tasty apps!</h3>
        <h4>Happy hour menu - half off!!</h4>
        <p>Chicken Wings(6) - 5.99$</p>
        <p>Calamari - 7.99$</p>
        <p>Garlic breaded pickles - 4.59$</p>
      </div>
    </li>

    <!-- Placeholder for Item 4 -->
      <!-- Item 2 -->
    <li>
      <input id="soupsAndSalads" type="radio" name="menu"/>
      <label for="soupsAndSalads">soups and salads</label>
      <div class="content">
        <h3>Salad Mania</h3>
        <h4>Free salad all day</h4>
        <p>Octopus Salad - <span>10.00$</span> free</p>
        <p>Pasta Salad - <span>4.59$</span> free</p>
      </div>
    </li>

  </ul>
</div>
```


## <input type="checkbox" checked> Task 2: Inserting CSS Style Rules

```css 

.accordion {
  border: 1px solid black;
  width: 800px;
  height:auto;
  border-radius: 10px;
}

.accordion ul {
  padding: 0;
  margin: 10px auto;
  width: 780px;
  list-style:none;
}


.accordion label:hover  {
  color: #fff;
  background-color:#C1263F;
  font-weight:600;
}

label {
  margin-top: 2px;
  border:1px solid black;
  padding:10px;
  font-size:20px;
  color:#641C19;
  letter-spacing: 1px;
  font-weight: 500;
  font-family: sans-serif;
  background-color:#DB5A3F;
  text-transform:uppercase;
  transition: background-color .5s ease-out ;
  display: block;
  position: relative;
  cursor:pointer;
}

.accordian input + label {
  transition: all 1s ease-in-out;
}

.content {
  overflow:hidden;
  padding: 0 1em;
  width:inherit;
  height: 2px;
  border: inherit;
  background-color:#fff;
  transition: all .5s ease-in-out; 
  border:none;
  font-family: sans-serif;
}

.content h3 {
  font-size: 20px;
  letter-spacing: 1px;
  color:#4F1843;
}

.content h4 {
  font-size:17px;
}

.content p {
  color:#303740;
  margin:2px;
  font-size:17px;
}

.content span {
  text-decoration:line-through;
}

[type="radio"] {
  display:none;
}

[type="radio"]:checked ~ label {
    color: #fff;
  background-color:#C1263F;
  font-weight:600;
}

[type="radio"]:checked  ~ .content {
  height: 200px;
  border: 1px solid black;
  border-top: none;
}

```
<br>

## <input type="checkbox" checked> Task 3: Adding a new Accordion Item


<p data-height="501" data-theme-id="0" data-slug-hash="oBXpXW" data-default-tab="result" data-user="nopity" data-embed-version="2" data-pen-title="accordian tab" class="codepen">See the Pen <a href="http://codepen.io/nopity/pen/oBXpXW/">accordian tab</a> by oscar (<a href="http://codepen.io/nopity">@nopity</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

<br><br>

<h1 style="color:#3CCAE6">Project Assignment 3: Create a Business Card Component</h1>

## <input type="checkbox" checked> Task 1: Updating HTML Markup

```html 

<section class="card">
<input type="radio" id="flipIcon" name="flip">
  
   <div class="front">
      <div class="frontIntro">
         <h1>Oscar Rodriguez</h1>
         <p>Full-Stack Developer</p>
         <label for="flipIcon">
            <img src="../images/ic_flip_black_24dp_2x.png">
         </label>
         <p class="aboutMe">Oscar is a front-end and backend developer who specializes in not knowing what to write about.</p>
      </div>
      <ul>
         <li><a href="email">oscarrobertrodriguez@gmail.com</a></li>
         <li><a href="https://www.oscarrobertrodriguez.github.io">OscarRR.com</a></li>
      </ul>
      <div class="bookmarkFront">
         <img src="../images/enc1.png">
         <p>Oscar Rodriguez <br> on <a href="#">Bov Academy</a></p>
      </div>

      <div class="socialMediaIcons">
         <a href="#"><img src="../images/twitter.png"></a>
         <a href="#"><img src="../images/github1.png"></a>
         <a href="#"><img src="../images/facebook.png"></a>
         <a href="#"><img src="../images/linkedin.png"></a>
      </div>

   </div>
 <input type="radio" id="flipToFront" name="flip">
   <div class="back">
      <label for="flipToFront">
         <img src="../images/ic_flip_black_24dp_2x.png">
      </label>

      <div class="bottomName">
         <p>Oscar Rodriguez</p>
      </div>

   </div>
</section>
```

## <input type="checkbox" checked> Task 2: Inserting CSS Style Rules

## <input type="checkbox" checked> Task 3: Adding Vendor Prefixes

```css 


.card {
    height: 300px;
    width: 600px;
    position: relative;
    -webkit-perspective: 300px;
            perspective: 300px;
    -webkit-transform-style: preserve-3d;
    -webkit-transition: -webkit-transform 1s;
    transition: -webkit-transform 1s;
    transition: transform 1s;
    transition: transform 1s, -webkit-transform 1s;
    margin: 50px auto;
}

.front, .back {
    position: absolute;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    background-color: orange;
    -webkit-backface-visibility: hidden;
            backface-visibility: hidden;
    -webkit-transition: 1s;
    transition: 1s;
}

.back {
    -webkit-transform: rotateX(180deg);
            transform: rotateX(180deg);
    background: url("project assets/backPhoto.jpg") no-repeat;
    background-size: cover;
}

/*Front of Card*/

.front {
    background: url("project assets/bg1.png") no-repeat;
    background-size: cover;
}

.card:hover .front {
    -webkit-transform: rotateX(10deg);
            transform: rotateX(10deg);
    box-shadow: 0 15px 15px lightgrey;
}

/* animation code */

[type="radio"] {
    display: none;
}

[type="radio"]:checked ~ .front {
    -webkit-transform: rotateX(-180deg);
            transform: rotateX(-180deg);
}

[type="radio"]:checked ~ .back {
    -webkit-transform:rotateX(0deg);
            transform:rotateX(0deg);
}

/*end animation */

.frontIntro {
    position: relative;
}

.frontIntro h1 {
    padding: 10px;
    margin-left: 10px;
    color: #fff;
    font-size: 45px;
    letter-spacing: 1px;
    font-family: Arial, serif;
}

.aboutMe, .bookmarkFront p {
    font-family: sans-serif;
    font-size: 14px;
    font-weight: 100;
    color: #fff;
    padding: 0;
    margin-left: 22px;
    top: 70px;
    left: 25px;
}

.frontIntro > p:nth-child(2) {
    position: absolute;
    font-size: 16px;
    font-family: sans-serif;
    font-weight: 100;
    color: lightgray;
    padding: 0;
    margin: 0;
    top: 70px;
    left: 25px;
}

.frontIntro img {
    position: absolute;
    top: 0;
    right: 40px;
    cursor: pointer;
}

.frontIntro img:hover {
    background-color: #fff;
    border-radius: 5px;
    -webkit-transform: rotateY(180deg);
            transform: rotateY(180deg);
}

.front ul {
    margin: 30px 0 0;
    padding: 0;
    list-style: none;

}

.front li {
    display: inline-block;
    margin: 0 10px 0 24px;
}

.front a {
    font-variant: small-caps;
    font-size: 15px;
    text-decoration: none;
    color: #C464E5;
}

.front a:hover {
    color: #d47ec3;
}

.bookmarkFront {
    position: absolute;
    bottom: 4px;
    left: 20px;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    margin-left: 4px;
    width: 180px;
    -webkit-box-pack: justify;
        -ms-flex-pack: justify;
            justify-content: space-between;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
}

.bookmarkFront img {
    height: 50px;
    width: 50px;
}

.socialMediaIcons {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    width: 250px;
    height:45px;
    -ms-flex-pack: distribute;
        justify-content: space-around;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    position: absolute;
    bottom: 15px;
    right: 30px;
}


.socialMediaIcons img:hover {
    border-radius:50%;
    border:3px solid #fff;
}

/* flip code*/







/*Back Of Card*/


.back img {
    position: absolute;
    top: 30px;
    right: 40px;
    cursor: pointer;
}

.back img:hover {
    background-color: #fff;
    border-radius: 5px;
    -webkit-transform: rotateY(180deg);
            transform: rotateY(180deg);
}

#flipToFront[type="radio"]:checked ~ .front {
    -webkit-transform: rotateX(0deg);
            transform: rotateX(0deg);
}

#flipToFront[type="radio"]:checked ~ .back {
    -webkit-transform: rotateX(180deg);
            transform: rotateX(180deg);
}


.bottomName {
    position: absolute;
    bottom:10px;
    left:20px;
    background-color: #EFEDE0;
    opacity:0.8;
    border-radius:5px;
}

.bottomName p {
    color:#7C30D2;
    padding:5px;
    margin: 0;
}

```



## <input type="checkbox" checked> Task 4: Create Your Own Digital Business Card



<section class="card">
<input type="radio" id="flipIcon" name="flip">
  
   <div class="front">
      <div class="frontIntro">
         <h1>Oscar Rodriguez</h1>
         <p>Full-Stack Developer</p>
         <label for="flipIcon">
            <img src="../images/ic_flip_black_24dp_2x.png">
         </label>
         <p class="aboutMe">Oscar is a front-end and backend developer who specializes in not knowing what to write about.</p>
      </div>
      <ul>
         <li><a href="email">oscarrobertrodriguez@gmail.com</a></li>
         <li><a href="https://www.oscarrobertrodriguez.github.io">OscarRR.com</a></li>
      </ul>
      <div class="bookmarkFront">
         <img src="../images/enc1.png">
         <p>Oscar Rodriguez <br> on <a href="#">Bov Academy</a></p>
      </div>

      <div class="socialMediaIcons">
         <a href="#"><img src="../images/twitter.png"></a>
         <a href="#"><img src="../images/github1.png"></a>
         <a href="#"><img src="../images/facebook.png"></a>
         <a href="#"><img src="../images/linkedin.png"></a>
      </div>

   </div>
 <input type="radio" id="flipToFront" name="flip">
   <div class="back">
      <label for="flipToFront">
         <img src="../images/ic_flip_black_24dp_2x.png">
      </label>

      <div class="bottomName">
         <p>Oscar Rodriguez</p>
      </div>

   </div>
</section>


<br><br>

<h1 style="color:#3CCAE6">Project Assignment 4: Create a Simple Image Gallery</h1>
<br>

## <input type="checkbox" checked> Task 1: Complete the HTML structure



```html 

<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <title>Title</title>
   <link rel="stylesheet" href="main.css">
</head>
<body>




<div class="container">



   <!-- Thumbnails at the top -->
   <ul class="thumbnailNav">

      <li>
         <label for="car1">
            <img src="images/thumbNail-car1.jpg">
         </label>
      </li>

      <li>
         <label for="car2">
            <img src="images/thumbNail-car2.jpg">
         </label>
      </li>

      <li>
         <label for="car3">
            <img src="images/thumbNail-car3.jpg">
         </label>
      </li>

      <li>
         <label for="car4">
            <img src="images/thumbNail-car4.jpg">
         </label>
      </li>

      <li>
         <label for="car5">
            <img src="images/thumbNail-car5.jpg">
         </label>
      </li>


      <div class="grabber"> <span>==</span>      <span>==</span>      <span>==</span> </div>
   </ul>


<!-- Container for backdrop image-->

   <input type="radio" id="car" name="cars" checked>
   <label>
   <div class="bigImage firstImage">

      <img src="images/car1.jpg">
   </div>
   </label>

   <input type="radio" id="car1" name="cars">
   <div class="bigImage">

      <img src="images/car1.jpg">
   </div>


   <input type="radio" id="car2" name="cars">
   <div class="bigImage">

      <img src="images/car2.jpg">
   </div>


   <input type="radio" id="car3" name="cars">
   <div class="bigImage">

      <img src="images/car3.jpg">
   </div>


   <input type="radio" id="car4" name="cars">
   <div class="bigImage">
      <img src="images/car4.jpg">

   </div>


   <input type="radio" id="car5" name="cars">
   <div class="bigImage">
      <img src="images/car5.jpg">

   </div>



</div>


</body>
</html>
```
<br><br>

## <input type="checkbox" checked> Task 2: Inserting CSS Style Rules

```css 
body {
    box-sizing: border-box;
}


.container {
    position: relative;
    min-width: 100%;
    min-height: 100%;

}



/* thumbnail bar */

ul.thumbnailNav {
    position: fixed;
    top:0;
    left: 0;
    width: 250px;
    margin:0;
    padding:0;
    border: none;
    background: rgba(0, 0, 0, .5);
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    opacity: .8;
    z-index: 1000;
    transition: opacity .5s ease, transform 1s ease-in-out;
    transform: translateX(-240px);
    border-top-right-radius: 10%;
    border-bottom-right-radius: 10%;
}


    .thumbnailNav li {
        list-style-type: none;
        width:200px;
        display: inline-block;
        padding:5px;
    }


    .thumbnailNav img {
        width: 200px;
        height:100px;
        border-radius: 5px;
    }

    .thumbnailNav img:hover {
        border: 2px solid yellow;

    }

    .thumbnailNav label {
        cursor: pointer;
    }


    .thumbnailNav:hover {
        opacity: 1;
        transform: translateX(0);
    }

    .grabber {
        position: absolute;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        right:0;
        width:20px;
        height: 250px;
        border-top-right-radius: 50%;
        border-bottom-right-radius: 50%;
        border:1px solid #fff;
        background-color: white;
        transform: translateX(20px);
        cursor: pointer;
    }

        .grabber span {
            margin-top: 20px;
            color:grey;
        }



    /*Back drop image*/



div.bigImage {
    position: fixed;
    top:0;
    left: 0;
    min-width: 100%;
    min-height: 100%;
    transform: translateX(-100%);
    opacity: 0;
    transition: opacity 1s ease-in, transform .7s ease;
}

    div.bigImage img {
        width:100%;
        height: 100%;
    }


    div.firstImage {
        opacity: 1;
        z-index: 4;
        transform: translateX(0);
    }





    /*Animation for background image change*/


[type="radio"]{
    display: none;
}



    [type="radio"]:checked + .bigImage{
    z-index: 5;
    opacity:1;
    transform: translateX(0);
    }


    [type="radio"]:not(:checked) + label {
    display: none;
    }

    [type="radio"]:not(:checked) + .bigImage {
    visibility: hidden;
    }

```


<br><br>

## <input type="checkbox" checked> Task 3: Adding a new Image


[Finished Image Gallery Link](https://oscarrobertrodriguez.github.io/bov-imageGallery/)


<br>
<br>







