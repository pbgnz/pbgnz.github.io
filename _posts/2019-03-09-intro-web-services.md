---
layout: post
title:  "A brief introduction to web services"
date:   2019-03-09
excerpt: "Services delivered over the web."
tag:
- software engineering
- web services
- web development
---

## What are web services ?

W3C's definition:
> A web service is a software system designed to support interoperable machine-to-machine interaction over a network.

There are 3 note-worthy concepts in the definition; interoperable, machine-to-machine, and over a network. Let's break
down what each one means.

1- **interoperable** means that an application written in PHP should be able to communicate with an application written in Java.

2- **machine-to-machine** means that web service are designed for application-to-application interaction. For example,
a simple TODO app written in HTML and JavaScript is not considered a web service as the latest is designed for human interaction. 

3- **over a network** means that the web service must be able to communicate with other applications using some sort of networking protocol such as HTTP.

## How does data exchange between web services take place ?

Data exchange between web services must follow a protocol in order for the services to communicate with each other. The standard protocol used in the world wide web (WWW) is HTTP and it consists of a series of exchanges between the client and the server in order to communicate. There are other protocols out there but that is for another blog post.

An example of a simple HTTP request asking for the index.html page of www.example.com would look something like this:

``` sh
GET /index.html HTTP/1.1
Host: www.example.com
```

The server from www.example.com would return the index.html page in the response to the client:

``` sh
HTTP/1.1 200 OK
Date: Mon, 23 May 2005 22:38:34 GMT
Content-Type: text/html; charset=UTF-8
Content-Length: 138
Last-Modified: Wed, 08 Jan 2003 23:11:55 GMT
Server: Apache/1.3.3.7 (Unix) (Red-Hat/Linux)
ETag: "3f80f-1b6-3e1cb03b"
Accept-Ranges: bytes
Connection: close

<html>
<head>
  <title>An Example Page</title>
</head>
<body>
  Hello World, this is a very simple HTML document.
</body>
</html>
```

It is through a protocol that different types of web services can communicate with each other regardless of the programming language that the application was built on. Furthermore, there are two popular formats for the requests and responses:

1- **XML.** XML stands for Extensible Markup Language and it is has a similar look to HTML syntax. 

``` sh
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>Don't forget me this weekend!</body>
</note>
```

2- **JSON.** JSON stands for JavaScript Object Notation and it is the most popular format today.

``` sh
{
    "name":"John", 
    "age":31, 
    "city":"New York"
}
```