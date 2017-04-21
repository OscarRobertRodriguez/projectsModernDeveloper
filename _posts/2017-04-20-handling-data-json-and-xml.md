---
layout: post
title:  "Handling data jason and xml"
---

<h1 style="color:#3CCAE6">Project Assignment 1: Construct JSON and Create JSON-XML Parser</h1>

Given that we’ve covered both XML and JSON in this chapter, this assignment is going to comprise of two parts. First, you will create a JavaScript object that contains an array of people objects; these could be friends, colleagues, family members, or acquaintances. Each people object should contain string properties for things like name, gender, and address; a numerical age property, and a children property containing an array of child objects. Each child object should also be a people object and so should also have the same properties. You should end up with at least 5 people objects, and the structure of the object should look like this:

<span class="label label-warning">Answer:</span><br>

<p data-height="537" data-theme-id="0" data-slug-hash="qmbJbb" data-default-tab="js" data-user="nopity" data-embed-version="2" data-pen-title="jason to xml" class="codepen">See the Pen <a href="https://codepen.io/nopity/pen/qmbJbb/">jason to xml</a> by oscar (<a href="http://codepen.io/nopity">@nopity</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>


<h1 style="color:#3CCAE6">Project Assignment 2: Create Simplified JSON Validator</h1>

Create a simplified JSON validator that checks any inputted JSON for errors. This JSON validator doesn’t have to validate any and all JSON. It should, however, be able to simplify simple JSONs, such as the JSON you will create in Project Assignment 3 below.

<span class="label label-warning">Answer:</span><br>

<h1 style="color:#3CCAE6">Project Assignment 3: Create JSON for Your Portfolio</h1>

Create a JSON data structure for your entire portfolio webpage. This JSON file should include all the text data for your portfolio, including the text shown in the Skills section. Use the following sample JSON as a reference:

<span class="label label-warning">Answer:</span><br>


```jason 
{
  "about": {
    "sectionTitle": "About Me",
    "fullName": "Oscar Rodriguez",
    "bioIntro": "I like making things with the power of the internet."
  },
  "projects": {
    "forms": {
      "source": "https://github.com/OscarRobertRodriguez/md-forms",
      "demo": "https://oscarrobertrodriguez.github.io/md-forms/"
    },
    "calculator": {
      "source": "https://github.com/OscarRobertRodriguez/calculator",
      "demo": "https://oscarrobertrodriguez.github.io/calculator/"
    },
    "buttons": {
      "source": "https://github.com/OscarRobertRodriguez/learning-web-components",
      "demo": "https://oscarrobertrodriguez.github.io/learning-web-components/components/buttons/"
    },
    "businessCard": {
      "source": "https://github.com/OscarRobertRodriguez/business-card",
      "demo": "https://oscarrobertrodriguez.github.io/business-card/"
    },
    "shoppingCart": {
      "source": "https://github.com/OscarRobertRodriguez/product-listing",
      "demo": "https://oscarrobertrodriguez.github.io/product-listing/"
    },
    "accordion": {
      "source": "http://codepen.io/nopity/pen/oBXpXW",
      "demo": "http://codepen.io/nopity/pen/oBXpXW"
    },
    "uiFramework": {
      "source": "https://github.com/OscarRobertRodriguez/md-forms",
      "demo": "https://oscarrobertrodriguez.github.io/md-forms/"
    },
    "imageGallery": {
      "source": "https://github.com/OscarRobertRodriguez/bov-imageGallery",
      "demo": "https://oscarrobertrodriguez.github.io/bov-imageGallery/"
    },
    "innovativeCarousel": {
      "source": "https://github.com/OscarRobertRodriguez/carousel-dropping-circle",
      "demo": "https://oscarrobertrodriguez.github.io/carousel-dropping-circle/"
    }
  },
  "skills": {
    "pieCircles": {
      "frontend": "70%",
      "backend": "30%"
    },
    "graphs": {
      "frontend": {
        "javascript": "competent",
        "html/css": "proficient",
        "reactjs": "learning",
        "pug": "competent",
        "Jquery": "learning"
      },
      "backend": {
        "nodejs": "learning",
        "golang": "learning",
        "postgresql": "learning",
        "aws": "learning",
        "docker": "learning"
      },
      "otherSkills": {
        "writtenCommunication": "learning",
        "problemSolving": "competent",
        "projectManagement": "learning",
        "research": "competent",
        "publicSpeaking": "learning"
      }
    }
  },
  "contact": {
    "name": "",
    "email": "",
    "message": ""
  }
}
```
