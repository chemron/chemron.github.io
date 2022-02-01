---
layout: post
title: "The World Wide Web"
---

# The World Wide Web
Runs on top of the internet (just like Skype or Minecraft).

The web is built from pages, which can contain links to other pages (hyperlinks). These hyperlinks create the “web”.

Text containing hyperlinks is called hypertext.

Pages link to one another through URLs (Uniform Resource Locator)
e.g. `Google.com/search`

How the World Wide Web works: 
1. Computer: DNS lookup - send domain name (`google.com`) to DNS server which returns the corresponding address
2. Computer: Creates a TCP connection to a Web Server at that address
3. Asks web server for hypertext page using HTTP (Hypertext Transfer Protocol) using the `GET` command (e.g. `GET /search`)
4. Web server replies with status code and the web page (sent as a text file - e.g. ASCII)

### HTML (Hypertext Markup Language)
We want to at the very least specify what is a link and what isn’t, so we need a special language. HTML uses tags (<…> … </…>) to specify the type of information.
### CSS (Cascading Style Sheets)
Styles the html, depending on tag, class and index

 



## Status codes
200: all good
404: Does not exist

#notes/internet