---
layout: post
title:  "Architecture of the Internet, the Web, and the Browser"
---
<h1 style="color:#3CCAE6">Projects</h1>

1. **Page Rendering** <br>
Analyze the HTML code given below and parse it to identify all the tokens. Create a DOM tree for the same HTML code. Is the HTML code malformed? Provide justification with proper reasoning. The HTML code to be used is given below.

 <h2 style="color:#3CCAE6">Provided Code For Project:</h2>  
```html
<html>
 
 <head>
 
  <title>
 
  HTML5 Table Rendering
 
  </title>
 
 </head>
 
 <body>
 
  <h4>NFL Points Table</h4>
 
  <table id="table1">
 
   <thead>
 
    <tr>
 
    <th>NFL Franchise</th>
 
    <th>Wins</th>
 
    <th>Losses</th>
 
    </tr>
 
   </thead>
 
   <tbody>
 
    <tr>
 
    <td>Carolina Panthers</td>
 
    <td>15</td>
 
    <td>1</td>
 
    </tr>
 
    <tr>
 
    <td>Denver Broncos</td>
 
    <td>12</td>
 
    <td>4</td>
 
    </tr>
 
    <tr>
 
    <td>Dallas Cowboys</td>
 
    <td>4</td>
 
    <td>12</td>
 
    </tr>
 
   </tbody>
 
   <tfoot>
 
    <td colspan="3"><small>Official NFL League Standings 2015</small></td>
 
   </tfoot>
 
  </table>
 
 </body>
 
</html>
```

 <h2 style="color:#3CCAE6">Code Rendered on Page: </h2>  

<html>
 
 <head>
 
  <title>
 
  HTML5 Table Rendering
 
  </title>
 
 </head>
 
 <body>
 
  <h4>NFL Points Table</h4>
 
  <table id="table1">
 
   <thead>
 
    <tr>
 
    <th>NFL Franchise</th>
 
    <th>Wins</th>
 
    <th>Losses</th>
 
    </tr>
 
   </thead>
 
   <tbody>
 
    <tr>
 
    <td>Carolina Panthers</td>
 
    <td>15</td>
 
    <td>1</td>
 
    </tr>
 
    <tr>
 
    <td>Denver Broncos</td>
 
    <td>12</td>
 
    <td>4</td>
 
    </tr>
 
    <tr>
 
    <td>Dallas Cowboys</td>
 
    <td>4</td>
 
    <td>12</td>
 
    </tr>
 
   </tbody>
 
   <tfoot>
 
    <td colspan="3"><small>Official NFL League Standings 2015</small></td>
 
   </tfoot>
 
  </table>
 
 </body>
 
</html> <br>

<span class="label label-warning">Answer:</span><br>

The question first ask us to take all the list all the tokens in the html, lets do that.

 <p style="color:#3CCAE6">Tokens:</p>

 `<html>`,`<head>`,`<title>`,`HTML5 Table Rendering`,`</title>`,`</head>`,
 `<body>`,`<h4>`,`NFL Points Table`,`</h4>`,`<table id="table1">`,`<thead>`,`<tr>`,`<th>`,`NFL Franchise`,`</th>`,`<th>`,`Wins`,`</th>`,`<th>`,`Losses`,`</th>`,`</tr>`,`</thead>`,`</tbody>`,`<tr>`,`</thead>`,`<tbody>`,`<tr>`,`<td>`,`Carolina Panthers`,`</td>`,`<td>`,`15`,`</td>`,`<td>`,`1`,`</td>`,`</tr>`,`<tr>`,`<td>`,`Denver Broncos`,`</td>`,`<td>`,`12`,`</td>`,`<td>`,`4`,`</td>`,`</tr>`,`<tr>`, `<td>`,`Dallas Cowboys`,`</td>`,`<td>`,`4`,`</td>`,`<td>`,`12`,`</td>`,`</tr>`,`</tbody>`,`<tfoot>`,`<td colspan="3">`,`<small>`,`Official NFL League Standings 2015`,`</small>`,`</td>`,`</tfoot>`,`</table>`,`</body>`,`</html>`

 Whoa that was a lot now let's draw an image of this mapped similar to how it would appear in a DOM tree.


<img style="display:block; margin: 0 auto; width: 800px; height: 600px" src="../images/Dom.png">  

To finish up this project let's answer the final question as to whether this code is malformed. I would say that yes this code is malformed but in a small way in that on line 69 the td element is not surrounded by a tr element so :

```html 
<td colspan="3"><small>Official NFL League Standings 2015</small></td>
```

Should look like this :

```html 
<tr>
    <td colspan="3"><small>Official NFL League Standings 2015</small></td>
</tr>    
```

The way I found this out is using DevTools and seeing if there was any difference in the original code. It is a small error that for the chrome browser does not appear to affect the table in any noticeable way. 


2. **HTTP Status Codes**<br>
HTTP Status Codes are grouped into five specific classes with each class’ first digit specifying the response type. All the HTTP Status/Response codes are listed on the following W3C resource: HTTP Status Codes.1

Using this information, list three status codes from each class, starting from 1XX to 5XX, along with a brief description and the situation in which it will be returned.

The second task is to explore unofficial codes which are not a part of the W3C recommendation. Some third-party services expand the 4XX error space. List any five such response codes and their significance.


<span class="label label-warning">Answer:</span><br>

To answer th first part of this project let's break down each class of error codes for 1XX to 5XX and list three for each section with a brief description and situation it will be returned in.


 <h2 style="color:#3CCAE6">Error Codes:</h2>

<p style="color:#3CCAE6"> Informational 1XX</p>

* **100 Continue** 
   * Description - to inform client that initial request has been received and has not been rejected by server
   * Situation - You want to check that the server is going to accept your request as it may be in your favor to do so to save from errors and time 
* **101 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.
<p style="color:#3CCAE6"> Successful 2XX</p>
* **200 Continue** 
   * Description - to inform client that initial request has been received and has not been rejected by server
   * Situation - You want to check that the server is going to accept your request as it may be in your favor to do so to save from errors and time 
* **202 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.
* **202 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.

<p style="color:#3CCAE6"> Redirection 3XX</p>
* **100 Continue** 
   * Description - to inform client that initial request has been received and has not been rejected by server
   * Situation - You want to check that the server is going to accept your request as it may be in your favor to do so to save from errors and time 
* **101 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.
* **202 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.
<p style="color:#3CCAE6"> Client Error 4XX</p>
* **100 Continue** 
   * Description - to inform client that initial request has been received and has not been rejected by server
   * Situation - You want to check that the server is going to accept your request as it may be in your favor to do so to save from errors and time 
* **101 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.
* **202 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.
<p style="color:#3CCAE6"> Server Error 5XX</p>
* **100 Continue** 
   * Description - to inform client that initial request has been received and has not been rejected by server
   * Situation - You want to check that the server is going to accept your request as it may be in your favor to do so to save from errors and time 
* **101 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.
* **202 Switching Protocols**
   * Description - sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too 
   * Situation - You want to allow move from an incompatiable protocol version - not in common use.