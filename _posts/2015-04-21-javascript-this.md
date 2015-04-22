---
layout: post
title: "javascript this"
description: ""
category: programming
tags: [programming, learntocode, javascript, fundamentals, this]
---
{% include JB/setup %}

[You Don't Know Javascript](https://github.com/getify/You-Dont-Know-JS) seems to have been a [Kickstarter](https://www.kickstarter.com/projects/getify/you-dont-know-js-book-series) that I hadn't previously seen.


It. Is. Awesome. 

![You Don't Know Javascript](/assets/files/ydkjs.png)


    JavaScript is awesome. It's easy to learn partially, and much harder to learn completely (or even sufficiently). When developers encounter confusion, they usually blame the language instead of their lack of understanding. These books aim to fix that, inspiring a strong appreciation for the language you can now, and should, deeply know.

[Chapter 2: `this` All Makes Sense Now!](https://github.com/getify/You-Dont-Know-JS/blob/master/this%20&%20object%20prototypes/ch2.md)

{% highlight javascript %}

function foo() {    // Function definition doesn't create a `this`
    var bob = 7;
    console.log(
        this.bob,   // => 2       Implicit binding means `this.bob` is the `bob` from within `obj`
        bob,        // => 7       `bob` is only local to foo
        this.thing  // => 'stuff' Again, foo is called in obj giving it access to local `thing`
    );
}

var obj = {
    bob: 2,
    thing: 'stuff',
    foo: foo        // This is where obj.foo() gets called from and `this` is bound
};

obj.foo(); // 2 7 'stuff'

{% endhighlight %}

