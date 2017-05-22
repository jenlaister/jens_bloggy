---
layout: post
title:  "Making Moves: How to Animate Objects on Your Screen"
date:   2017-07-02 11:50:27 -0400
categories: Jen's bloggy
---

For one of our projects, we had to build a game using Javascript and jQuery. My partner and I decided to do an animated game with a space theme. The objective of the game was for our spaceship that held ‘Naut, our dog astronaut to get to the other side of the board without colliding into any asteroids.


We hit couple of challenges trying to actually make objects on our screen move. Our objects were on the screen but they were static and weren’t moving. Either that or one of the many things on our screen would move….the rest just kind of hung out and didn’t move, which defeated the purpose of our game.

We were able to make our spaceship move across the screen using the method window.requestAnimationFrame():

The method window.requestAnimationFrame(callback_function) takes in a callback function as an argument. It eliminates the use of a setTimeout() or setInterval() which delays a function for a certain amount of milliseconds before running the function again. Instead, window.requestAnimationFrame() works in a recursive manner in which you would call the method within the method — method-ception! Using window.requestAnimationFrame() to animate something on the screen will prevent inconsistent delays between animation frames and doesn’t put the browser in cardiac arrest where it’s forced to perform repeated calls of functions to change the page and display the animation. If the user has a system with limited performance capabilities, this may cause janky page loads and inconsistent delay time intervals between animation frames.

For moving our asteroids, I found alternate way to animate our objects using jQuery’s .animate method:

We used properties and duration as arguments for our .animate method.
This animation method does require setInterval() and a delay time (in milliseconds) before running the function again. We only had five asteroids on our screen so our browser didn’t hate us and there were no visible animation delays. We did try the method without a setInterval() and the browser didn’t like it as there were too many call stacks being made to repeatedly animate the asteroids. The method .animate is another way to animate specific objects on the screen randomly.

jQuery’s method .animate takes in arguments (properties, [duration], [easing], [complete]) as objects:


The arguments easing and complete are optional and there are plenty of other optional arguments that you can use for the method. If you do pass in easing as an argument, you will need a jQuery plugin that provides a easing function.

[Continue on to read about how to detect collision]()…

[To play Spazz Out Space Cadet](https://jenlaister.github.io/space_cadet/)
