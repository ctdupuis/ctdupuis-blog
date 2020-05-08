---
layout: post
title:      "The Difficulties of AJAX"
date:       2020-05-08 04:19:05 +0000
permalink:  the_difficulties_of_ajax
---


For the past 8 months, everything I have learned to code has been synchronous. What does that mean? Well, it's simple. One line of code will run at a time, no matter what. This makes code more uniform and easier to predict.

*However*, JavaScript has this wonderful method of processing called AJAX that allows for different blocks of code to run simultaneously. 

This new method of processing, just like every other aspect of programming, is a very powerful tool that can cause many headaches if you don't fully understand how it happens. When introduced to AJAX, I had to switch gears and understand that if I had any functions that relied on one another, they would have to execute one at a time, or synchronously. 

The JavaScript project taught me just how frustrating asynchronous code can be. The amount of times where my render functions were being called on a pending promise are astronomical. Those alone were enough to force me to really adapt this new style of processing data.

Since JavaScript runs functions asynchronously unless specified otherwise, it forces you to structure your functions around the order you want them to run in. This can be done by using the `await` keyword on an async function or invoking the dependent function inside of the parent.

Compared to Ruby, JavaScript seems to be more spread out. Since Ruby is natively synchronous, the learning process is more straight forward. Ruby gets you in the habit of dictating exactly what will happen simply by putting one line in front of the next. I simply decide the order of execution by the order in which I write my code. With JavaScript, I felt like I had to constantly be aware of how my entire code base interacts with one another. I was always having to make sure that if one of my functions depended on another, that the independent function needs to completely resolve or else my code simply won't work.

Another main difference between the two is error messaging. I never thought I would say this, but man do I really miss Ruby taking the time to completely stop my execution and scream at me for making a mistake. Ruby errors aren't always the most descriptive, but I'll take those over JavaScript anyday. JavaScript's most descriptive error I've come across is just `error: getData is not a function` even though I'm looking at `getData() { return data }` on my screen in disbelief. The problem wasn't that `getData` wasn't a real function, but just that when I would try to invoke that function, the call stack was in a state that hadn't reached the function's declaration.

All things said and done, my experience with JavaScript has been an emotional rollercoaster, going from the highs of dynamically manipulating DOM elements and having a page that feels truly alive, to the terrible frustrations of having functions accidentally being invoked at the wrong time or multiple times for no obvious reason. JavaScript was the introduction to a new way of interpreting and processing data, and I'm ready to take these experiences - good and bad - with me on my coding journey to React and Redux.
