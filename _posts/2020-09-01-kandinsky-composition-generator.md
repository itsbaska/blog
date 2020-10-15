---
layout: post
title: "Kandinsky Composition Generator"
date: 2020-09-01 19:04:06 -0500
categories: p5js generative art
---

I love art and I love coding so I thought why not combine them. A long while ago I created a Kandinsky composition generator. And I thought I would share my process here.

For those who aren't familiar Kandinsky was a painter and art theorist who was a pioneer for abstract art.

Here are some examples of his works that he calls compositions:

<img src="/assets/2020-09-01-kandinsky-composition-generator/kandinsky-composition-1.jpg" alt="Kandinsky" height="150"/>
<img src="/assets/2020-09-01-kandinsky-composition-generator/kandinsky-composition-2.jpeg" alt="Kandinsky 2" height="150"/>

---

For this project I used p5.js, css, and just plain old html.

After setting up a frame, I started off with getting a random background colour. I limited the amount of background colors to tan or grayish colours to emulate what Kandinskys background colour typically looks like.

```javascript
var colours = [
  "#F5EBE1",
  "#2E346E",
  "#CB2A15",
  "EC5F43",
  "#DB6B12",
  "#284620",
  "#352748",
];

function getRandomColour(colours) {
  return colours[Math.floor(Math.random() * colours.length)];
}
```

The result looks a little something like this:

<img src="/assets/2020-09-01-kandinsky-composition-generator/state-gifs/state1.gif" alt="state 1"/>

The next step I took was to add a main 
