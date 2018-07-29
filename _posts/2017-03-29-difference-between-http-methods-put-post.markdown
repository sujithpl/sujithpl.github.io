---
layout: post
title:  "The Difference between the HTTP methods PUT and POST"
date:   2017-03-29 00:00:00 -0500
categories: professional
tags: [api, programming, rest]
---
It seems that almost everyone is using [RESTful](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm) APIs everywhere. A very common question that comes up is which of the two [HTTP](http://www.rfc-editor.org/info/rfc7230) methods PUT and POST should be used in a particular situation. In this post, I will describe my understanding of the difference between the two methods.

## The PUT method
- It can be used to create or update resources.
- It is idempotent. This means that multiple invocations of this HTTP method will produce the same result. In other words, there are no side effects.
- It needs an exact URI location. This can be a problem if the server is responsible for generating unique resource identifiers.
```
PUT /products/123
{ }
```

## The POST method
- It can be use to only create resources.
- It is not idempotent.
- It does not expect an URI to contain a resource identifier.
- The server should respond with a location header element.
```
Location: /products/456
```
- Returning the newly created resource object is optional.

Of course, all this looks great in theory. However, I have run into scenarios that did not fit either method perfectly. And sometimes, technical considerations have forced me to go against these guidelines. But in the majority of the cases, I have found that the above rules work well for me.