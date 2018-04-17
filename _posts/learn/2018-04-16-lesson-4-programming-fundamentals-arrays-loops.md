---
layout: post
title:  "JavaScript Programming Fundamentals: Arrays & Loops"
date:   2018-04-15
lesson: 4
group: "fundamentals"
category: "learn"
excerpt: ""
patreon-post: https://www.patreon.com/posts/18225502
---

## Arrays
What is an array? You might already know, but an array is a **list**. To be precise, its an ordered list, meaning that whatever you put into a javascript array, it will remain in the same order unless specifically modified. Here's an array of taco ingredients:

{% highlight js linenos %}
{% raw %}
var ingredients = ["ground beef", "tomatoes", "guacamole"];
{% endraw %}
{% endhighlight %}

Put that in your console and print it out ;).

No, seriously. Paste that array into your Chrome console and press Return/Enter.

Now type `ingredients[1]` into your Chrome console and press Return/Enter.

<span class="image fit center"><img src="{{ "/images/learn/lesson4/console-1.gif" | absolute_url }}"></span>

So, we made an array called _ingredients_ and then we typed into the console _ingredients[1]_ and it printed out the second string in the array. Why?

In javascript, and in many other languages, arrays are _zero-indexed_. This means that the first item in an array is at position _0_. So if we wanted the first item in _ingredients_ we could just do _ingredients[0]_. Go ahead and try that out.

JavaScript is very forgiving. It will allow you to mix and match data types in your arrays, it's usually bad practice do it - but I'm going to show you what I mean:

{% highlight js linenos %}
{% raw %}
var myArray = ["string", 22, true];
{% endraw %}
{% endhighlight %}

The code above is completely valid, its an array where index 0 is a string, index 1 is a number, and index 2 is a boolean. Just because you _can_ do something doesn't mean you _should_. This is a bad idea in almost every scenario and is the last time you'll see me mix data types in an array.

Now that you know how to access the data at a particular index in an array, play around with it a bit, try doing something like this:
{% highlight js linenos %}
{% raw %}
var ingredients = ["ground beef", "tomatoes", "guacamole"];

console.log(ingredients[3-1]);
{% endraw %}
{% endhighlight %}

Why does it print out "guacamole"? Because index 3-1 = 2, and index 2 is "guacamole". So you can see how you can manipulate index's as needed. But, I haven't yet given you enough knowledge to really use arrays, so let's do that with loops.

<hr />

## Loops
Loops are super important in programming. Let me give you an example. You ask your database for a list of users, and you want to print each users name out.

{% highlight js linenos %}
{% raw %}
// this is our database
var users = ["Bob Smith", "Dave Thomas", "Rhonda Rousey"];

// this is the loop
for (var i = 0; i < 3; i++) {
    console.log(users[i]);
}

{% endraw %}
{% endhighlight %}

Okay, there's a little bit to unpack here. Let's go over the _for loop_ syntax. [Mozilla pretty much sums it best:](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
>The for statement creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement (usually a block statement) to be executed in the loop.

The first expression is called the initialization, you basically are declaring a variable equal to some number, in this case 0.

The second expression is called the condition, this means that each time the loop has completed, the condition will be ran, so in our example as long as _i < 3_ the loop will execute again.

The third expression is the final expression and its usually an increment or decrement of your initialized variable. In our example, the loop will execute (printing users[i]) and then it will increment i, and the condition will be tested again.

To illustrate this, lets add a bit more code:

{% highlight js linenos %}
{% raw %}
var users = ["Bob Smith", "Dave Thomas", "Rhonda Rousey"];

console.log("LOOP IS STARTING");
for (var i = 0; i < 3; i++) {
    console.log(users[i]);
}
console.log("LOOP HAS ENDED");

{% endraw %}
{% endhighlight %}

Running that code in the Chrome console will show you that nothing below the loop executes until the loop's condition is no longer true.

### Dynamic Programming
So far every example has been hard coded, meaning we are not working with dynamic data, so we know how long our _users_ array was, for example. But in the real world you don't always know how many items are in a given list. Here's how you'd tackle something like that.

{% highlight js linenos %}
{% raw %}
// our (pretend) dynamic array 
var users = ["Bob Smith", "Dave Thomas", "Rhonda Rousey"];

for (var i = 0; i < users.length; i++) {
    console.log(users[i]);
}

{% endraw %}
{% endhighlight %}

Arrays have a property called _length_. We haven't talked about Objects yet, but under the hood an array is really an Object so it has a couple _properties_ and _methods_. Lets not worry about that right now, just know you can access an array's _length_ property by using the dot notation: _users.length_ is 3.

Whats actually really convenient about this is javascript array's are zero-indexed, so just asking for users.length gives us 3, meaning we can make our condition _i < users.length_ because there is nothing at index 3, but there is "Rhonda Rousey" at index 2, so as long i is less than 3 we can safely retrieve a value out of the array at the current index.

You can try to make the loop print beyond index 2, and see what it does!

## Conclusion
Loops really give you a peak behind the curtain of how software sort of works. Let me show you an example of a common interview question software engineers are asked, to weed out the really bad ones 😛

{% highlight js linenos %}
{% raw %}
/*
this is called FizzBuzz
if you google it, you'll see it's pretty popular

Write a program that prints the numbers from 1 to 100. 
For multiples of three print "Fizz" instead of the number.
For the multiples of five print "Buzz" instead of the number. 
For numbers which are multiples of both three and five print "FizzBuzz".
*/

for (var i = 1; i < 101; i++) {

    var text = '';

    if (i % 3 === 0) {
        text = text + 'Fizz';
    }

    if (i % 5 === 0) {
        text = text + 'Buzz';
    }

    if (!text) { // an empty string in javascript is falsey
        text = i;
    }

    console.log(text);
}

{% endraw %}
{% endhighlight %}

Run that code in your Chrome console and see if my code passes the code interview!

This exercise is really cool because it encompasses a lot of the stuff we've talked about up until this point. Work on some fun loop and array stuff in VS Code and then paste your code into the Chrome console to see your baby program do it's thing!