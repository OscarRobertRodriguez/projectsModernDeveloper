---
layout: post
title:  "Mastering the Dom"
---

<h1 style="color:#3CCAE6">Project Assignment 1: DOM Utility Library</h1>




For the first part of your assignment, you will create a small utility library of functions that adds some “missing” DOM functions. It should include the following functions:

* getAncestorBySelector: This should be used to find the nearest ancestor that matches any CSS selector with respect to a given element, and it should take two arguments: the first should be the element to start from (as a Node) and the second should be the selector that should be used to match the ancestor (as a string). It should return the matching ancestor if found or null if no matching ancestor was found.<br>

```javascript
var getAncestorBySelector = function(elem, selector) {
   elem = document.querySelector(elem);
   ancestor = elem.parentNode;
  
  selector = document.querySelector(selector).nodeName;
  
  if(ancestor.matches(selector)) {
      return  ancestor.cloneNode().outerHTML;
     }else {
       return null ; 
     }
};

```


* getSiblingsBySelector: This method should be used to select an element that be longs to the same parent as the element it is called on. It should accept the CSS selector as an argument and return a collection of zero or more matching elements.<br>


```javascript
var getSiblingsBySelector = function(elem) {
  elem = document.querySelector(elem);
  siblings = elem.parentNode.children; 
  var siblingArray = [];
  for(var i = 0; i < siblings.length; i++) {
     siblingArray.push(siblings[i].nodeName);
  }
   
   console.log(siblingArray);
    
};
```

insertAfter: This should be used to insert a new node after an existing node in the DOM and should take two arguments: the node to be inserted and the node to insert the new node after. It should return the element that was inserted.<br>

```javascript
var insertAfter = function (elem, selector) {
  var newNode = document.createElement(elem);
   newNode.innerHTML = 'test';
  var referenceNode = document.querySelector(selector); 
  
  referenceNode.parentNode.insertBefore(newNode, referenceNode.nextSibling);
};
```

* swapElements: This function should be used to swap the position of two DOM elements and should take the two elements to swap as arguments. It should return true if the swap was successful and false otherwise.<br>

```javascript
var swapElements = function(elem1, elem2) {
    elem1 = document.querySelector(elem1);
    elem2 = document.querySelector(elem2); 
    var target = document.createElement('div'); 
  
   elem1.parentNode.insertBefore(target, elem1); 
   
   elem1.parentNode.insertBefore(elem1, elem2); 
   
   elem2.parentNode.insertBefore(elem2, target); 
  
    target.parentNode.removeChild(target); 
   
};
```

* removeAll: This function should be used to remove a number of elements from the page entirely. It should accept a CSS selector as an argument and return the elements that were removed as an array.
As a base for the assignment, use the following page, which contains a nested hierarchy of elements:

```javascript
var removeAll = function (elem) {
  
  var elementArray = [];
  
  elem = document.querySelector(elem); 
    
  elementArray.unshift(elem.nodeName);   
  
  var childList = elem.childNodes;
  
  for(var i = 0; i < childList.length; i++) {
     elementArray.push(childList[i].nodeName)
  } 
  
  elem.parentNode.removeChild(elem); 
   
  
  console.log(elementArray); 
  
}; 
```