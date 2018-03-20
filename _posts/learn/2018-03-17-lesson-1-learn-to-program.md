---
layout: post
title:  "Learn To Program With The World's Most Popular Programming Language"
date:   2018-03-17
lesson: 1
category: "learn"
excerpt: "JavaScript and the absolute basics. We will set up our development environment and learn to write our very first bit of code."
image: "/images/learn/lesson1/laptop-notepad.jpg"
---

## Why Javascript?
According to Github, Javascript is by far the most popular programming language, making up 22% of all code hosted on github servers. Besides that, javascript lends itself well to newbies. It's easy to run on almost any machine, and you don't _need_ to install anything to get started, and it's pretty lenient, as far as programming languages go.

## What's Needed?
To run javascript, or see it in action, you only need a browser. However, I'm going to assume you want to write your own code, so in that case you should be downloading [Google Chrome](https://google.com/chrome) and [Microsoft's Visual Studio Code](https://code.visualstudio.com/). Install VS Code and open it. If you've used a text editor before then you'll realize VS Code is a mix between notepad/textedit and Word or Google Doc.

## Getting Started
<div class="box">
<p class="image"><span class="image right"><img src="{{ "/images/learn/lesson1/scratch.jpg" | absolute_url }}" alt="" /></span>
Create a folder at the root of your machine, called Developer. Create another folder inside Developer called <code>scratch</code>.</p>
</div>

Back in VS Code, go to File > Open. Navigate to the `scratch` folder you just created, highlight it by clicking it once, and click 'open'.

<div class="box">
<p class="image"><span class="image right"><img src="{{ "/images/learn/lesson1/new-file.png" | absolute_url }}" alt="" /></span>
Click the icon in the project tree to create a new file. Name the file <code>main.js</code>. This tells VS Code that we're working in a javascript file, VS Code is pretty helpful in that it will try to help you write and syntax highlight your code. Create another new file, save this empty file as <code>index.html</code>.</p>
</div>

_Whoa man, I thought we were learning to program, not make a website!_

Relax. I'll have you writing desktop and mobile apps with JS in no time, but for now we just need a canvas to start sketching on. Add the following code to `index.html`

`index.html`
```
<!DOCTYPE html>
<html>
    <head>
        <title>My site</title>
        <script src="main.js"></script>
    </head>
    <body>
    </body>
</html>
```

Cool. Nice blank website. Very modern-minimalist.

We can access the html page (which includes our js file) by navigating to the index.html file in Chrome's address bar, for example:
`file:///Users/corey/Developer/scratch/index.html`

<div class="box">
<p class="image"><span class="image right"><img src="{{ "/images/learn/lesson1/disable-cache.png" | absolute_url }}" alt="" /></span>
First, lets disable the cache in Chrome. Right click anywhere on your blank page and click 'inspect'. This opens the developer tools. Click the 'Network' tab in the developer tools and check the box 'Disable Cache'. This is really important, if you don't do this then you may not see your code working. Keep developer tools open while working in Chrome.</p>
</div>

Let's make sure everything is hooked up properly. Back in VS Code, go to `main.js`, write and save this code:

`main.js`
```
alert("Hello World");
```

Refresh the page in chrome, you should see a native popup (this is the alert box) that says `Hello World` inside. Congratulations! Not only did you write your first bit of javascript, but you also used Chrome's [alert API](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)!

<hr>
## TLDR
<div class="box">
    <ol>
        <li>Download Google Chrome and VS Code.</li>
        <li>Create a directory, <code>Developer/scratch</code> to work in.</li>
        <li>Add two blank files to <code>/scratch</code>: main.js & index.html</li>
        <li>Add some html boilerplate to index.html and include main.js.</li>
        <li>Disable the cache in Chrome, otherwise you won't see code changes.</li>
        <li>Insert a single line of javascript into main.js to test that its all working.</li>
    </ol>
</div>

