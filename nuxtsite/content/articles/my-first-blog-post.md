---
title: My first Blog Post
description: Learning how to use @nuxt/content to create a blog
img: first-blog-post.jpg
alt: IMAGE OF my first blog post
author: 
  name: Michael Fudge
  bio: Mike is a freelance writer for blahblah.com. He likes horses and chicken nuggets.
  image: https://secure.gravatar.com/avatar/abc9968f853c25383d5e1b23e9230741
---

## What can I say that hasn't been said already?

Welcome to my first post !!! Some things I will talk about:

- sjhdgfshdaf
- sadhfgksadf
- sadhfgkjshdgf
- hsajdfgkjsagdf
- sajdhfgkjsagd

### The Source

```js{1,3-5}[server.js]
const http = require('http')
const bodyParser = require('body-parser')

http.createServer((req, res) => {
  bodyParser.parse(req, (error, body) => {
    res.end(body)
  })
}).listen(3000)
```

## This is a heading

This is some more info

### This is a sub heading

This is some more info

### This is another sub heading

This is some more info

## This is another heading

This is some more info

### Other stuff

jhsdklfgsajhd flh ljfhasldjfalskjdfhl kjsad


<pre>this could be code</pre>