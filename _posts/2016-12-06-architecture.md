---
layout: post
title:  "Architecture of the Internet, the Web, and the Browser"
---
<h1 style="color:#3CCAE6">Projects</h1>

<h3 style="color:#3CCAE6">1. Page Rendering</h3>
<p style="font-weight: bold">Analyze the HTML code given below and parse it to identify all the tokens. Create a DOM tree for the same HTML code. Is the HTML code malformed? Provide justification with proper reasoning. The HTML code to be used is given below.</p>

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

The question first ask us to take all html tags and form a list of all the tokens.

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

<h3 style="color:#3CCAE6">2. HTTP Status Codes:</h3>
<p style="font-weight: bold">HTTP Status Codes are grouped into five specific classes with each class’ first digit specifying the response type. All the HTTP Status/Response codes are listed on the following W3C resource: HTTP Status Codes.</p>

Using this information, list three status codes from each class, starting from 1XX to 5XX, along with a brief description and the situation in which it will be returned.

The second task is to explore unofficial codes which are not a part of the W3C recommendation. Some third-party services expand the 4XX error space. List any five such response codes and their significance.


<span class="label label-warning">Answer:</span><br>

To answer this project let's break down each class of error codes for 1XX to 5XX and list three for each section with a brief description and situation it will be returned in.


 <h2 style="color:#3CCAE6">Error Codes:</h2>

<p style="color:#3CCAE6"> Informational 1XX</p>

* **100 Continue** 
   * to inform client that initial request has been received and has not been rejected by server. You want to check that the server is going to accept your request as it may be in your favor to do so to save from errors and time 
* **101 Switching Protocols**
   * sent in response to Upgrade: request by the client, indicates the protocol the sever is switching too. You want to allow move from an incompatiable protocol version - not in common use.
<p style="color:#3CCAE6"> Successful 2XX</p>
* **200 OK** 
   * is sent back if request has succeded. Any time you request information from a server and it is found and sent back
* **201 Created**
   *  when a request is made that ruesults in a new resource being created. You give a server your email and name the sever creates an object of you in its database
* **202 Accepted**
   *  request has been accepted but processing is not complete. You are submitting your payment at a website you have to wait for a couple of seconds you see prompts that say your payment has been received but you must wait a couple of seconds for it to finalize this would send a 202 first then it would send 201 thne a 200

<p style="color:#3CCAE6"> Redirection 3XX</p>
* **301 Move Permanently** 
   * requested resource has moved to a new URI and should use one of the returned URI. Visit a link that redirects you to another site
* **302 Found**
   * requested resource is under a new URI tempory URI is returned and Should be given by the location field as a response
* **303 See Other**
   * uses the GET method to retrieve a source under a new URI
<p style="color:#3CCAE6"> Client Error 4XX</p>
* **400 Bad Request** 
   * error returned by server bad sytax causes an error request must be fixed
* **401 Unauthorized**
   * requires user authentication
* **403 Forbidden**
   * sever understands request but is refusing to grant it will be returned if permissions are not allowed also 404 code can be returned instead
<p style="color:#3CCAE6"> Server Error 5XX</p>
* **500 Internal server Error** 
   *  error returned when sever encountered an unexpected condition
* **502 Bad Gateway**
   * error that is sent when the sever sends a invalid response 
* **501 Not Implemented**
   * error that is returned when the server does not support the required tools to carry out request 
<p style="color:#3CCAE6">Unofficial Error Codes</p>
* **495 SSL Certificate Required** 
   * expansion of 400 code used when client does not provide certificate this could help in pinpoint why request is not working vs. getting a plain error code
* **444 No Response**
   * error returned when server does not return any information then connection is closed
* **440 Login Time-out**
   * error returned when the client has been on too long and must login again useful for sensitive data 
* **509 Bandnwitdth Limit exceeded**
   * error returned when bandwidth is exceeded might be useful if you run a site where data usage is payed for subscriptionally 
* **450 Blocked by Window Parental Controls**
   * Used by microsoft to let client know that Parental controls is blocking access to site. 


<h3 style="color:#3CCAE6">3. DNS:</h3>
**We looked at different types of DNS records such as A, CNAME, MX, TXT, etc. In this task, you will research the following types of records: HINFO, ISDN, NS, PTR, and SOA. Create a table with the following columns to provide the information for the above newly listed record types: DNS Record Type, Full form, Description, and Example.**
<br>
<span class="label label-warning">Answer:</span><br>
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg .tg-7fle{font-weight:bold;background-color:#efefef;text-align:center;vertical-align:top}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-ccb6{font-weight:bold;background-color:#efefef;color:#333333;text-align:center;vertical-align:top}
.tg .tg-i81m{background-color:#ffffff;text-align:center;vertical-align:top}
.tg .tg-yw4l{vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-7fle">DNS Record Types</th>
    <th class="tg-7fle">Full Form</th>
    <th class="tg-7fle">Description</th>
    <th class="tg-ccb6">Example</th>
  </tr>
  <tr>
    <td class="tg-i81m">HINFO</td>
    <td class="tg-i81m">Host information</td>
    <td class="tg-i81m">specifies the host / server's type of CPU and operating system</td>
    <td class="tg-i81m">;[name],[TTL] class HINFO,hardware,OS,IN,HINFO,Sparc-10,UNIX</td>
  </tr>
  <tr>
    <td class="tg-baqh">ISDN</td>
    <td class="tg-yw4l">Integrated Services Digital Network</td>
    <td class="tg-baqh">maps a domain name to a telephone number</td>
    <td class="tg-yw4l">user@host#show interfaces br-1/0/3isdn-options {switch-type att5e;spid1 00108005555555;calling-number 18005555555;incoming-called-number 18883333456;tei-option power-up;static-tei-val 23;t310 15;}dialer-options {pool isdn-dialer-group priority 255;</td>
  </tr>
  <tr>
    <td class="tg-baqh">NS</td>
    <td class="tg-baqh">Authoritative name server</td>
    <td class="tg-baqh">identify the DNS servers responsible for a zone</td>
    <td class="tg-yw4l">id 55396<br>opcode QUERY<br>rcode NOERROR<br>flags QR RD RA<br>;QUESTION<br>moderndeveloper.com. IN NS<br>;ANSWER<br>moderndeveloper.com. 43199 IN NS ns2.mediatemple.net.<br>moderndeveloper.com. 43199 IN NS ns1.mediatemple.net.<br>;AUTHORITY<br>;ADDITIONAL</td>
  </tr>
  <tr>
    <td class="tg-baqh">PTR</td>
    <td class="tg-baqh">domain name pointer</td>
    <td class="tg-baqh"> used to map IP addresses to domain names </td>
    <td class="tg-yw4l">id 58648<br>opcode QUERY<br>rcode NOERROR<br>flags QR RD RA<br>;QUESTION<br>moderndeveloper.com. IN PTR<br>;ANSWER<br>;AUTHORITY<br>moderndeveloper.com. 1799 IN SOA ns1.mediatemple.net. dnsadmin.mediatemple.net. 2016110402 10800 3600 1209600 43200<br>;ADDITIONAL</td>
  </tr>
  <tr>
    <td class="tg-baqh">SOA</td>
    <td class="tg-baqh">Start of authority</td>
    <td class="tg-yw4l">Name of primary DNS server and email address of responsible person</td>
    <td class="tg-yw4l">id 9144<br>opcode QUERY<br>rcode NOERROR<br>flags QR RD RA<br>;QUESTION<br>moderndeveloper.com. IN SOA<br>;ANSWER<br>moderndeveloper.com. 43199 IN SOA ns1.mediatemple.net. dnsadmin.mediatemple.net. 2016110402 10800 3600 1209600 43200<br>;AUTHORITY<br>;ADDITIONAL</td>
  </tr>
</table>






<h3 style="color:#3CCAE6">3. Network Topology:</h3>
**In the discussion about Network Architecture, we looked at networks in which all the devices were connected to each other (mesh topography) and at how the introduction of a router created a hub (star topography). What other types of physical network topographies currently exist in the real world? List any three such topologies and specify their advantages, disadvantages, and any constraints in setting them up.**

<span class="label label-warning">Answer:</span><br>

<h3 style="color:#3CCAE6">Point-to-point Topology</h3>

Link between two endpoints. The advantage over other setups is that it easy simple setup is there is a need for only one wire also the connection will have the best signal. The disadvantage is that if the wire is cut then there is no possible way to reconnect, all communication will be lost.

<h3 style="color:#3CCAE6">Ring Topology</h3>

Closed loop connection. You can visualize as a ring where data is transmited in one direction till it gets back to the starting node. Advantages are that all nodes are connected. The disadvantages are that if one node is not woring the data will not make it to all nodes. 



<h3 style="color:#3CCAE6">Star Topology</h3>

With this setup you have a central hub in the center with all other nodes connected to this central hub. Advantages to this setup is that every computer is indirectly connected and is easier than all other topologies to add additional nodes. The disadvantage is that it gives a singel point of failure.