---
layout: post
title:  "JavaScript Programming Fundamentals: Variables & Data Types"
date:   2018-03-18
lesson: 2
category: "learn"
excerpt: "some wrap up"
image: "/images/learn/lesson1/laptop-notepad.jpg"
---

## Computers are dumb
Computers are not magic. A computer will do exactly what you tell it to do, even if you didn't mean what you said. Thats usually called a bug, and as a future programmer, you're going to see bugs that turn the universe upside down and make you think everything you know is a lie. And then it turns out you forgot a semi-colon somewhere and all is right in the world again.

We've all done some algebra before, where _x + 2 = 7_ and you must solve for _x_. Computers are really good at remembering what _x_ is. That's why they can be so dumb and still be useful to us. As a programmer, your job is to tell the computer how to get _x_ so it can use it later: _x = 7 - 2_

Now that _x_ is known to be 5, the computer will remember that forever. And when you need _x_ again, you don't need to solve, you can just use _x_ and the computer will put a 5 in its place. _x_ is called a variable, here.

## Variables
Variables are a store of data. Under the hood, a computer has assigned an address in its memory to hold the value of a given variable. Thats part of the beauty of high level programming languages like JavaScript. We need not concern ourselves with finding available addresses in the computer's memory and assigning/moving bytes of data, etc. We can instead just use variables, and know that the _compiler_ or _interpreter_ (the browser is a javascript interpreter) is doing all of that for us, freeing us up to just write code. Lets look at how variables work.

```
var myName = "Corey";
var myAge = 28;
```

- We have created two variables, `myName` and `myAge`.
- _var_ is used to declare a new variable.
- _=_ assigns the value to the variable name.
- "Corey" is a _string_. A string is wrapped in " " or ' '.
- 28 is a _number_. If it was "28" it would be a string.
- writing variables like `myName` is called [Camel Case](https://en.wikipedia.org/wiki/Camel_case) and is conventional for multiword variables, as opposed to snake case which looks `my_name`, or hyphenated `my-name`.
- variable names can start with letters and some characters (such as `_`) but they cannot start with numbers, and they cannot contain any spaces.
- you end statements in javascript with a semicolon: `;`

These two variables are two different data types. This is important to know because if you try to do math with a string, you'll get unexpected results. Doing math on 28 and "28" are two very different things.

### JavaScript's Data Types

| Type         | Description  |
| ------------ |:-------------|
|**String**    | a string is a list of characters 'strung' together. An example of a string would be a facebook comment, or the body of an      email. "This is a string, always wrapped in quotes." |
|**Number**    | a number is a literal number. In javascript, a number can be `10` or it can be `10.5`. Both are valid numbers.      |
|**Boolean**   | a boolean is a funny word, named after [George Boole](https://en.wikipedia.org/wiki/George_Boole). A Boolean is `true` or `false`. It can only be true or false. It is not "true" or "false". It is **true** or **false**. |
|**Object**    | an object is a _dictionary_, or blueprint, made up of key-value pairs: `{favoriteFood: "tacos"}`. |
|**undefined** | undefined is the value of a variable that has no value. lol. |

### Manipulating Variables
Lets look back at the two variables I created above. If we pretend for a moment that I wanted to write the world's lamest program, I could make a program that prints out `myAge` and `myName`. In fact, lets do that. Open main.js and delete the alert code thats currently in there.

`main.js`
```
var myName = "Corey";
var myAge = 28;
var greeting = "Hello, my name is ";

alert(greeting + myName);
```

<div class="box">
<strong>Quick note:</strong> what we've done with the <code>greeting</code> and <code>myName</code> variables, inside the alert call, is called <strong>string interpolation</strong>. You can add strings to strings with the <strong>+</strong> operator, which is the same operator you'd use to add numbers together. JavaScript does its best to try to figure out what you want it to do with the <strong>+</strong> operator. So if you try to add a number to string, it will interpolate your number into the string. So doing this: <code>myName + myAge</code> will actually result in "Corey 28". I hope that makes sense.
</div>

You should see "Hello, my name is Corey" alerted. But what if we do something to change `myName` before we print it out? lets do this:

`main.js`
```
var myName = "Corey";
var myAge = 28;
var greeting = "Hello, my name is ";

myName = "Jim";

alert(greeting + myName);
```

On line 1, we created myName and assigned it a value of **String** "Corey". Then on line 5 we reassigned myName to **String** "Jim". So by the time alert is called, myName is "Jim".

## Use The Console
This alert box is getting pretty annoying. As a developer, you have much better tools to read the output of your code. In the developer tools window (which you should always keep open when programming in the browser, so as to keep the cache disabled) you have a tab named "Console". Lets start using the console.

change main.js to look like this:

`main.js`
```
var myName = "Corey";
var birthYear = 1990;
var thisYear = 2018;
var myAge = thisYear - birthYear;
var greeting = "Hello, my name is ";

myName = "Jim";

console.log(greeting + myName);
console.log("I am " + myAge + " years old.");
```

Refreshing the page, you should see your new strings printed out in the console.

## Some Notes
JavaScript executes from the top down. That's why when we assign "Corey" to myName on line 1, it is _overwritten_ on line 7 by "Jim". Furthermore, if you were to move your console log up to line 6, you would see that "Corey" is printed out in the console, as the console is printed out before myName is reassigned to "Jim".

Try playing around with our tiny program. You can do some math with myAge and log that out in the console, write as many console logs as you like. Create some new variables and make some new strings. When you're ready, continue onto the next lesson.