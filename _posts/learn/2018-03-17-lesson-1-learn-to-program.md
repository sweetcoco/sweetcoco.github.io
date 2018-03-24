---
layout: post
title:  "Setting Up Your Development Environment"
date:   2018-03-17
lesson: 1
category: "learn"
excerpt: ""
patreon-post: https://www.patreon.com/posts/17747020
image: "/images/learn/lesson1/js-popular-min.jpg"
---

## Why Javascript?
JavaScript is INSANELY popular. Popular programming languages aren't good to learn just because they're _trendy_ and _smell good_. The most popular programming languanges have the largest and most vibrant communities and ecosystems. That means you're wayyy more likely to find a discussion on an obscure JavaScript feature, or bug, than you are to find the same discussion around the issue with C, or Go. 

Besides that, javascript lends itself well to newbies. It's easy to run on almost any machine, and you don't _need_ to install anything to get started. JavaScript is also pretty lenient, which can be good and bad, as far as programming languages go. You'll get the hang of it fast but don't expect every language we tackle in the future to be so cool about everything. You'll see what I mean.

## What's Needed?
To run javascript, or see it in action, you only need a browser. However, I'm going to assume you want to write your own code, so in that case you should be downloading [Google Chrome](https://google.com/chrome) and [Microsoft's Visual Studio Code](https://code.visualstudio.com/). Install VS Code and open it. If you've used a text editor before then you'll realize VS Code is a mix between notepad/textedit and Word or Google Doc.

## Getting Started
Create a folder at the root of your machine, called Developer. Create another folder inside Developer called `scratch`.
<span class="image fit center"><img src="{{ "/images/learn/lesson1/scratch.jpg" | absolute_url }}"></span>

<hr />

Back in VS Code, go to File > Open. Navigate to the `scratch` folder you just created, highlight it by clicking it once, and click 'open'.

<hr />

Click the icon in the project tree to create a new file. Name the file `main.js`. This tells VS Code that we're working in a javascript file, VS Code is pretty helpful in that it will try to help you write and syntax highlight your code. Create another new file, save this empty file as `index.html`.
<span class="image fit center"><img src="{{ "/images/learn/lesson1/new-file.png" | absolute_url }}"></span>

_Whoa man, I thought we were learning to program, not make a website!_

Relax. I'll have you writing desktop and mobile apps with js in no time, but for now we just need a canvas to start sketching on. Add the following code to `index.html`

{% highlight html linenos %}
{% raw %}
<!-- index.html -->
<!DOCTYPE html>
<html>
    <head>
        <title>My site</title>
        <script src="main.js"></script>
    </head>
    <body>
    </body>
</html>

{% endraw %}
{% endhighlight %}


Cool. Nice blank website. Very modern-minimalist.

<hr />

We can access the html page (which includes our js file) by navigating to the index.html file in Chrome's address bar, for example: 
`file:///Users/corey/Developer/scratch/index.html`

First, lets disable the cache in Chrome. Right click anywhere on your blank page and click 'inspect'. This opens the developer tools. Click the 'Network' tab in the developer tools and check the box 'Disable Cache'. This is really important, if you don't do this then you may not see your code working. Keep developer tools open while working in Chrome.
<span class="image fit center"><img src="{{ "/images/learn/lesson1/disable-cache.png" | absolute_url }}"></span>

<hr />

Let's make sure everything is hooked up properly. Back in VS Code, go to `main.js`, write and save this code:

{% highlight js linenos %}
{% raw %}

// main.js
document.write("Hello World!");

{% endraw %}
{% endhighlight %}

Refresh the page in chrome, you should now see `Hello World!` written on the page. Congratulations on your first bit of JavaScript! 

<hr>
## TLDR
<div class="box">
    <ol>
        <li>Download Google Chrome and VS Code.</li>
        <li>Create a directory, <vs>Developer/scratch</vs> to work in.</li>
        <li>Add two blank files to <vs>/scratch</vs>: main.js & index.html</li>
        <li>Add some html boilerplate to index.html and include main.js.</li>
        <li>Disable the cache in Chrome, otherwise you won't see code changes.</li>
        <li>Insert a single line of javascript into main.js to test that its all working.</li>
    </ol>
</div>