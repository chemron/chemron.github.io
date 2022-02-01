---
layout: post
title: "How does a web form work"
---

# How does a web form work
To submit information to the server the computer needs to use the `POST` http request. To prompt the computer to do this, we can use a form as follows.

1. Get the web page that has the form e.g. `GET /signup`
2. The server will return the html for the webpage including the form e.g. `<form action=“/users” method=“post”> ... </form>` 
3. When the form is submitted, the computer will use the `POST` method from the page specified e.g. `POST /users`
4. This sends the form information to the server 

#notes/internet