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