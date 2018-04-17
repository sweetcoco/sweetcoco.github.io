---
layout: post
title:  "JavaScript Programming Fundamentals: Variables & Data Types"
date:   2018-03-18
lesson: 2
group: "fundamentals"
category: "learn"
excerpt: ""
patreon-post: https://www.patreon.com/posts/17747159
---

## Computers are dumb
Computer's are not magic. In fact, there's a running joke that a computer is really just [a rock with lightning inside that we tricked into thinking](https://twitter.com/daisyowl/status/841802094361235456). A computer will do exactly what you tell it to do, even if you didn't mean what you said. The computer's strength is its ability to remember and then do work on given variables extremely fast. Thats about all it's good at.

I've seen intros to programming go on at length trying to explain a philosophical introduction to programming... and I wrote a few and deleted them in the place of this very paragraph. We're going to just jump in to writing code. I just want you to remember back to your algebra days. Lets do a simple algebra problem with JavaScript.

## Variables
`x + 4 = 6`

As a human, its obvious that _x_ is 2. Lets write a program that can solve this problem. Clear out the code in main.js. Ready?

{% highlight js linenos %}
{% raw %}

// main.js
var x = 6 - 4;

document.write(x + " + 4 = 6"); 

{% endraw %}
{% endhighlight %}

JavaScript _sytax_ for _declaring_ a variable is `var` followed by a space, and then the _name_ of the variable. So it's easy to see on line 2, we have declared a variable named _x_.

<fieldset class="box"><legend>Variables in (some) depth</legend>
Variables are a store of data. Under the hood, a computer has assigned an address in its memory to hold the value of a given variable. Thats part of the beauty of high level programming languages like JavaScript. We need not concern ourselves with finding available addresses in the computer's memory and assigning/moving bytes of data, etc. We can instead just use variables, and know that the <i>compiler</i> or <i>interpreter</i> (the browser is a javascript interpreter) is doing all of that for us, freeing us up to just write code.
</fieldset>

### Some Quick Notes On Variables (and general programming)
Programmers use conventions to keep us from going insane. So, for example, in my above code I used essentially three lines to write my program (lines 2, 3, & 4). I could've written that on one line though, JavaScript only cares about the semicolon at the end of the statement, not the line breaks, so this is completely valid:
{% highlight js linenos %}
{% raw %}
var x = 6 - 4;document.write(x + " + 4 = 6");
{% endraw %}
{% endhighlight %}

The problem is... this is really hard to read. The convention is to break up your code appropriately with new lines and indents as necessary.

**CONVENTIONS:**

- **[Camel Case](https://en.wikipedia.org/wiki/Camel_case)** - our variable here is just named _x_ but what if it was _firstNumber_? this is called camel case. The first word of your variable is lowercase, then capitalize the following first letters.
- **Descriptive but brief** - Sure, its valid to name your variable _theSquareRootOfFirstNumberAndTheResultOfPiDividedByProbability_ but if you have an entire program written like this, your code will become unwieldy, take forever to type, and god help the next engineer that comes along to read this greek epic.

**RULES:**
- **Picky about first characters** - you cannot start a variable with a number, _1stNumber_ is not valid, you will get an error. Some special characters are valid, like the underscore: _\_firstNumber_ is a legit variable name. Dont get too fancy with these, stick with regular alphabet characters.
- **Reserved keywords** - JavaScript has some reserved keywords that you cannot use as variable names because JavaScript uses them for its own purposes. Here's a list of them, we're not going to go over it, just know it exists: [Reserved Keywords](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords).
- **No Spaces** - you cannot have any spaces in a variable name.
- **No Hyphens** - you cannot have any hyphens in a variable name.


## JavaScript Data Types
Remember that whole thing about computers being dumb? They think in binary, which means everything in a computer's memory is a 0 or a 1. Turns out, if you put eight 0's or 1's next to each other, you get 256 possible combinations, right? (2^8 = 256 math!). 8 bits = 1 byte. A character is 1 byte, always. For example, the letter _a_ is represented as _01100001_, or _096_ if you convert it to a number.  So... this lesson is a lot of bytes. Not a lot for a computer, but a lot for a human.

Why am I telling you this? I want you to understand what a data type is, and why knowing them matters to the computer. A single character is just that, something like _!_ or _z_. If you string a bunch of these together you get a... **String**. Strings are everywhere. A Facebook comment is a string, a tweet is a string, this post is a string. In JavaScript, strings are represented by wrapping your code in either single or double quotes:
{% highlight js linenos %}
{% raw %}
var myString = "Thank you for reading my string! Wowee!";
{% endraw %}
{% endhighlight %}
If you don't wrap that string in quotes, your program will crash, because it is actual nonsense to the computer. The computer needs to know what to do with different kinds of data - it ends up writing it all in binary but it does work on different data types differently (good luck multiplying a string by the number 100), so you have to be explicit about what you're writing.

**Here's a table of JavaScript Data Types**

| Type         | Description  |
| ------------ |:-------------|
|[**String**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Text_formatting)    | a string is a list of characters 'strung' together. An example of a string would be a facebook comment, or the body of an      email. "This is a string, always wrapped in quotes." |
|[**Number**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)    | a number is a literal number. In javascript, a number can be _10_ or it can be _10.5_. Both are valid numbers. _"10"_ is not a number, it is a string.      |
|[**Boolean**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Boolean_type)   | a boolean is a funny word, named after [George Boole](https://en.wikipedia.org/wiki/George_Boole). A Boolean is _true_ or _false_. It can only be true or false. It is not "true" or "false". It is **true** or **false**. |
|[**Object**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Objects)    | an object is a _dictionary_, or blueprint, made up of key-value pairs: `{favoriteFood: "tacos"}`. (we'll get to this later. I know it sounds confusing.) |
|[**undefined**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Undefined_type) | undefined is the value of a variable that has no value. lol. |



## Lets Use Them
Copy this into your main.js.

{% highlight js linenos %}
{% raw %}
// main.js
// this is called a comment, the program skips everything after // on a single line
// its just for humans to read.

/*
this is a multiline comment
so you don't have to do the // on every line,
you can instead just wrap a long comment like this.
*/

// myNumber and aDecimal are both numbers.
var myNumber = 6 - 4;
var aDecimal = 2.4;

// fullName is a string.
var fullName = "Casey Jones";

// needsCoffee and isHungry are booleans.
var needsCoffee = true;
var isHungry = false;

// sum is undefined, could also be sum = undefined.
var sum;

// we are now setting sum equal to the sum of this equation.
sum = aDecimal + myNumber;

// lets print this out to the browser
document.write("My name is " + fullName);
document.write("<br />"); // this is just html to add a new line between these.
document.write("The sum of myNumber and aDecimal is " + sum);
document.write("<br />");
document.write("I need coffee: " + needsCoffee);
document.write(" I am hungry: " + isHungry);
{% endraw %}
{% endhighlight %}

### Lets talk about whats going on here
First, JavaScript executes from the top down. So the code on line 12 runs before the code on line 26. Which is good, because the code on line 26 is using the code from line 12 to do its equation. Next, we need to talk about what is happening in these _document.write()_ methods.

When you see something like this in js: `"my name is " + fullName` this is called **string concatenation**. Again, you're seeing that _+_ operator (we talk about operators in the next lesson) but it doesn't mean to do math in this useage. Js does its best to guess what you want to do with the _+_ operator, based on the _DATA TYPES_ its being used with in context. We concatenated _fullName_ onto our string above, so it just makes it one string, inputting the value of _fullName_ into the string for us. Useful stuff. 

Now, you might be asking yourself... _"Isn't sum a number type?"_ and wooo boy you're a sharp one. When you concatenate any data type onto a string, it becomes a string as well. This is called _coercion_, it's useful but also dangerous. Other languages aren't so forgiving.

I explained what comments were in the code, and then I used comments to explain the code. So you should understand comments by now, they're ignored by the compiler and only meant for me and you to read.

## Introduction To The Console
So far, we have been using _document.write()_ to see the results of our code. As a developer, you have much better tools to read the output of your code. In the developer tools window (which you should always keep open when programming in the browser, so as to keep the cache disabled) you have a tab named "Console". Lets start using the console. Change all of the _document.write()_ to _console.log()_, and replace the "\<br />" with "\n".
{% highlight js linenos %}
{% raw %}
// lets print this out to the browser
console.log("My name is " + fullName);
console.log("\n"); // this is a newline character, we could put this in the log above or below as well.
console.log("The sum of myNumber and aDecimal is " + sum);
console.log("\n");
console.log("I need coffee: " + needsCoffee);
console.log(" I am hungry: " + isHungry);
{% endraw %}
{% endhighlight %}

## Conclusion
Great job. I know this might be somewhat overwhelming. There is a trick to learning how to write code: you need to write your own. You don't know much right now, but as lessons go on you'll be armed with more and more knowledge, and even though we will eventually build an app together, you should be writing code on your own, independent of our project(s).

I want you to mess around with this code, try some things out, look at errors you might see in the console.