---
title: A quick intro to JSON {}
date: 2023-06-06 00:00:00 
categories: [Technology, Programming]
tags: [json, programming]
---

JSON, which stands for JavaScript Object Notation, is the most popular and widely accepted data exchange format, and it was originally specified by [Douglas Crockford](https://en.wikipedia.org/wiki/Douglas_Crockford).

**Features**

- JSON is an easy-to-use, purely text-based format that is lightweight and human-readable.

- It is platform and language-independent, and almost all front-line languages and frameworks provide inbuilt support for JSON.

- The official [MIME](https://en.wikipedia.org/wiki/MIME) type for JSON text is application/json.

- JSON files typically have the file name extension .json.

**Syntax**

The syntax rules for JSON are as follows:

- Data is organized in name/value pairs.
- Data is separated by commas.
- Objects are enclosed in curly braces.
- Arrays are enclosed in square brackets.

![JSON Array example](https://community.codenewbie.org/remoteimages/uploads/articles/zs2juw2gjs9t8d092p8n.png)


![JSON Object example](https://community.codenewbie.org/remoteimages/uploads/articles/47hu2b43z03iskc5cnpm.png)


Parse the data with [JSON.parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse), and the data becomes a JavaScript object.

![Parse JSON string in JS](https://community.codenewbie.org/remoteimages/uploads/articles/2o6d55zftqys5a07r4zk.png)

When sending data to a web server, the data has to be a string. Convert a JavaScript object into a string with [JSON.stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify).

![JSON Object to simple string](https://community.codenewbie.org/remoteimages/uploads/articles/70o1lcssqvsq68eh82gc.png)

**Common Problems**

- Trailing Comma - you are not allowed to add a trailing comma.
- Missing Commas - Since trailing commas are not allowed, it is easy to forget to append one before adding a new value.
- Comments - JSON does not allow comments as it is a data-interchange format.


Check out this video by quick @[beaucarnes](https://twitter.com/beaucarnes?lang=en) via freeCodeCamp for a quick introduction to JSON

{% include embed/youtube.html id='B-k76DMOj2k' %}

You can visualize your JSON data instantly into graphs with this [JSON Crack tool](https://jsoncrack.com/editor). Thanks for the read!

\- [Aadarsh K](https://twitter.com/dotAadarsh)



