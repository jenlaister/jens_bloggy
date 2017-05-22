---
layout: post
title:  "CSS: The Display Property"
date:   2017-05-19 11:50:27 -0400
categories: Jen's bloggy
---

When you design a website, each page is your canvas. The elements that you create will take up a defined allocated amount of space on your page. These elements can be displayed in a certain way depending on how you set them. With CSS, you can control the layout of your page and define how you want to display your element(s).

Every element has a default value depending on it’s type. The two most common default _display properties_ are **block** and **inline**. A **block** element is also known as a **block-level** element. It takes up the maximum full width that is available horizontally and starts a new line. However, when a defined height and width has been set for that element, a block element will display itself within those boundaries. The common block elements are: ``<div>, <p>, <form>, <header>, <section>, <h1> to <h6>`` and ``<footer>``.

An **inline** element wraps text, data or other inline elements within an element to prevent the interference with other elements. Think of it as element inception. An inline element is a smaller element nested within another content element. It doesn’t start a new line and is limited within the element that it is wrapped in. You cannot set a height or width for this display. However, you can control the left and right margins and padding. These elements are usually ``<span> , <img>`` or ``<a href>`` links that line up horizontally.

Other display properties include:

**None**: The element will not appear on the page and it will not effect your layout as it doesn’t occupy any space. There is also the **visibility** setting, in which you can set to **hidden** or **visible**. When the element is hidden it will take up space but won’t be visible or it can be visible depending on the function you use and setting you set for the display. This is helpful in cases where you don’t want to delete or recreate an element.

**Inline-block**: This display is a combination of block + inline. You can set a height and width on this element and it will flow within it’s defined limits. The element will take up the space within it’s surrounding element.

**Flex**: This display will set your element as a block element within a flex container. The element will adjust it’s size accordingly and relative to your flex container. Flex gives the element flexibility to either grow to fill up the available space or shrink to prevent overflow.

To learn more about [CSS display properties and see visual examples of each property](https://css-tricks.com/almanac/properties/d/display/).
