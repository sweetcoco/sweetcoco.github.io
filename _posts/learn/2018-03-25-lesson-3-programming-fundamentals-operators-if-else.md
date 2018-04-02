---
layout: post
title:  "JavaScript Programming Fundamentals: Operators & If Else"
date:   2018-03-25
lesson: 3
group: "fundamentals"
category: "learn"
excerpt: ""
patreon-post: https://www.patreon.com/posts/17763691
---

## Operators
We're all familiar with some operators. You know the following symbols _+ - ÷_, they're math operators that indicate the kind of math you want to do with given variables. Programmers rely on many operators, and many of them don't involve math at all, but instead they involve _comparisons_, _logic_. As usual, code speaks louder than words. Lets crush some out!

### Assignment Operator

| Type         | Description  |
| ------------ |:-------------|
|**=**  | we've seen this one already, assign a value to a variable or property.|

{% highlight js linenos %}
{% raw %}
var bestFood = "Tacos";
{% endraw %}
{% endhighlight %}

<hr />

### Comparison Operators
Recall booleans from the previous lesson. A boolean is _true_ or _false_, sometimes they are also referred to as **logical values**. Comparison operators are binary operators that compare two operands and return the logical, or boolean, value of the expression... Okay, I know that was jargon. Jargon is good for you, call people _unevaluated expressions_ under your breath. 

Also, don't be confused by the term **binary operator**, it just means it evaluates two operands whereas a **unary operator** only has one operand, we'll see unary operators later. I'm going to write a bit of code and label the jargon, ready?

{% highlight js linenos %}
{% raw %}
var myScore = 11;
var highScore = 10;

//       first operand operator second operand
//                  ↓     ↓       ↓
var myScoreWins = myScore > highScore; // myScore > highScore is the expression.
//     ↑
//  boolean (logical) value of the expression.

{% endraw %}
{% endhighlight %}

Copy and paste the above code into the console in Google Chrome and press Enter/Return. Then type _myScoreWins_ into the console and press Enter/Return. You should see this:
<span class="image fit center"><img src="{{ "/images/learn/lesson3/console-1.gif" | absolute_url }}"></span>
Our expression says _myScore_ **is greater than** _highScore_ evaluates to **true**. So, _myScoreWins_ has a value of **true**.
<br />If we were to flip the position of the values in our expression, we'd see this:
<br />_highScore_ **is greater than** _myScore_ evaluates to **false**. So, _myScoreWins_ has a value of **false**.


| Type         | Description  | example |
| :----------: |:-------------|---------|
|**===**  | Comparing two values are equal.| 1 === 2 is **false** |
|**!==**  | Comparying two values are not equal.| 1 !== 2 is **true** |
|**>**    | Value on left is greater than value on right.| 1 > 2 is **false** |
|**>=**   | Value on left is greater than or equal to value on right.| 1 >= 2 is **false** |
|**<**    | Value on left is less than value on right.| 1 < 2 is **true** |
|**<=**   | Value on left is less than or equal to value on right.| 1 <= 2 is **true** |

<hr />

### Arithmetic Operators
Sometimes you gotta do math. Its a bummer but life just be like that. Some quick maths:
{% highlight js linenos %}
{% raw %}
var year = 1;
var century = year * 100;
var decade = century / 10;
var lustrum = decade - 5;
var xv = decade + 5;
var remainder = xv % decade; // 5

// here's two operators js has that
// make common math operations easier

var someNumber = 7;
someNumber++; // the ++ operator adds 1.
console.log(someNumber); // is 8 now

someNumber--; // guess what this does.
console.log(someNumber);

{% endraw %}
{% endhighlight %}

| Type         | Description  | example |
| :----------: |:-------------|---------|
|**+**  | Add two operands together.| 10 + 2 is **12** |
|**-**  | Subtract the second operand from the first.| 10 - 2 is **8** |
|**\*** | Multiply two operands together.| 10 * 2 is **20** |
|**/**  | Divide the operand on the left by the operand on the right.| 10 / 2 is **5** |
|**%**  | Modulo. Divide the operand on the left by the operand on the right return the remainder.| 10 % 3 is **1** |
|**++** | Add 1 to a value.| 10++ is **11** |
|**-\-** | Subtract 1 from a value.| 10-\- is **9** |

A note on the ++ and -- operators:
{% highlight js linenos %}
{% raw %}
var age = 25;

// using ++ or -- after the value, will assign the 
// new value AFTER the expression is evaluated:

console.log(age++); // age will log as 25 still
console.log(age); // now it will be 26

// to get the new value immediately,
// put the ++ or -- BEFORE the value

console.log(++age); // 27 immediately

// try this out with -- operator also!

{% endraw %}
{% endhighlight %}

Congratulations, now you know math.

<hr />

### Logical Operators
Logical operators take two values (if binary) or one value (if unary) and return a boolean. They're useful for performing logical determinations within code, such as if you need to know if someone is old enough and logged in to see a video game ad, for example.
{% highlight js linenos %}
{% raw %}
var loggedIn = true;
var age = 21;
var allowEntry = loggedIn && age >= 18; // && is our logical operator here

console.log(allowEntry);
{% endraw %}
{% endhighlight %}

_allowEntry_ is true above because _loggedIn_ is true AND _age_ is higher than 18. _&&_ being our operator.

| Type         | Description  | example |
| :----------: |:-------------|---------|
|**&&**  | Left AND right operand must be true, to return true.| true && false is **false** |
|**\|\|**  | Left OR right operand must be true, to return true.| true \|\| false is **true** |
|**!** | Unary operator called NOT. Returns false if its operand is true, otherwise its true.| !true is **false** |

<hr />

## if else
Logical determinations are what programming is all about. Being able to do something IF a condition is met, or something ELSE if it is not, is the entire point of the IF ELSE statement.
{% highlight js linenos %}
{% raw %}
var coffeeCount = 5; // we want 5 coffees
var coffeeCost = 2; // a coffee is $2
var myMoney = 7; // I have $7;

// if i can buy all my coffees, shout yay!
// if i can't, then i'm sad :(

if ((coffeeCount * coffeeCost) <= myMoney) {
    alert("Yay!!");
} else {
    alert("I don't have enough :(");
}
{% endraw %}
{% endhighlight %}
Lets talk about something that i've done here, you can see this bit of code:

`(coffeeCount * coffeeCost)`

Notice that it is wrapped in its own parethesis. This is for grouping together sets of logic. Its not necessary here but it sure makes it easy to read. You can easily tell that I first want to evaluate the total of _coffeeCount_ and _coffeeCost_ and then determine if it is less than or equal to myMoney.

Again, feel free to open the console right on this page, or put this code in your main.js. Remember to refresh the page each time you want to run the code.

## Conclusion
Let's make tacos.

{% highlight js linenos %}
{% raw %}
var numberOfTortillas = 6;
var containsBeef = false;
var containsChicken = true;
var containsRedOnion = true;
var containsPico = false;
var chipsAndSalsa = false;

var isVegetarian = !containsBeef && !containsChicken;
var hasOnion = containsRedOnion || containsPico;
var canFeed5WithChips = (numberOfTortillas >= 5) && chipsAndSalsa;

if (isVegetarian) {
    console.log("These tacos are vegetarian!");
}

if (!containsPico) {
    console.log("These tacos have no pico!");
}

if (numberOfTortillas >= 5) {
    console.log("We can feed a family of 5!");
} else {
    console.log("We cannot feed a family of 5, only a family of " + numberOfTortillas + " 😤");
}

var tacoCost = 5;
var tacosOrdered = 3;

console.log("Cost of 3 tacos? "  + (tacoCost * tacosOrdered));
console.log("Cost of 2 tacos? "  + (tacoCost * --tacosOrdered));
{% endraw %}
{% endhighlight %}


Feel free to replace the code in your _main.js_ file with these code snippets and play around with the values, or just paste them into a console (refresh the page/console to try new values).