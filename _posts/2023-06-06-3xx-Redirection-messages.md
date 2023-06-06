---
title: 3xx - Redirection messages
date: 2023-06-06 00:00:00 
categories: [IT]
tags: [networking, http-codes]
---


Redirection ↪️ messages

![Redirecting](https://media.giphy.com/media/ddZ2mYhxhh69wEpSVz/giphy.gif)

### 300 Multiple Choices ✔️

The HTTP 300 Multiple Choices redirect status response code means that the thing you asked for can be given in more than one way. The user-agent or the user should choose one of them.


### 301 Moved Permanently

The HTTP 301 Moved Permanently redirect status response code indicates that the requested resource has been definitively moved to the URL given by the Location headers. A browser redirects to the new URL and search engines update their links to the resource.

### 302 Found

The HTTP 302 Found redirect status response code indicates that the resource requested has been temporarily moved to the URL given by the Location header. A browser redirects to this page but search engines don't update their links to the resource.

### 303 See Other

It redirect status response code indicates that the redirects don't link to the requested resource itself, but to another page. This response code is often sent back as a result of PUT or POST. The method used to display this redirected page is always GET.

### 304 Not Modified

This is used for caching purposes. When a client makes a request for a certain file, the server will check to see if it has a cached version of that file. If it does, it will send the cached version to the client instead of generating a new one.

### 305 Use Proxy

The Proxy-Authenticate header is used to indicate that a requested response must be accessed by a proxy. It has been deprecated due to security concerns regarding in-band configuration of a proxy.

### 306 Unused

This code is no longer used.

### 307 Temporary Redirect

If a client requests a resource from a server, and the server sends this response, that means the resource is located at a different URI. The client should make another request to the same URI with the same method that was used in the prior request.

### 308 Permanent Redirect

This means that a resource that was once located at one URI is now permanently located at another URI. The user agent (a web browser, for example) must not change the HTTP method used when making the second request to the new URI.

%[https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#redirection_messages]


Check out [1xx](https://community.codenewbie.org/engineeredsoul/1xx-informational-2bo2) and [2xx](https://community.codenewbie.org/engineeredsoul/successful-response-200-15nm), if you have missed out.
Thanks for the read. 
\- [Aadarsh](https://twitter.com/dotAadarsh)

