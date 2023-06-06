---
title: 1xx - Informational
date: 2023-06-06 00:00:00 
categories: [IT]
tags: [networking, http-codes]
---

A 1xx status code is a provisional response from a server. It consists of the Status-Line and optional headers and is terminated by an empty line. There are no required headers for this class of status code.

### 100 Continue 

It's an informational status response code that indicates that everything so far is OK and that the client should continue with the request or ignore it if it is already finished.

### 101 Switching Protocols 

If the server needs to upgrade the connection, it sends back a 101 status with an Upgrade header that specifies the protocol(s) being switched to. If it does not need to upgrade, it ignores the Upgrade header and sends back a regular response (ex,200 OK).

### 102 Processing

This code indicates that the server has received and is processing the request, but no response is available yet.

As guidance, if a method is taking longer than 20 sec (a reasonable, but arbitrary value) to process the server should return a 102 response.

### 103 Early Hints

The HTTP 103 Early Hints information response status code is a code that is mostly used with the Link header. This header allows the user agent to start preloading resources while the server is still preparing a response.


%[https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#information_responses]


Thanks for the read and stay tuned! 
\- [Aadarsh K](https://twitter.com/dotAadarsh)
