---
layout: post
title:  "CSS: The Difference Between the Position Properties"
date:   2017-05-22 11:50:27 -0400
categories: Jen's bloggy
---

In my previous post, I wrote about the display position and how it helps you layout the elements on your page with CSS. To further control where your element exactly goes on the page, you can use another CSS property called position. This will detail the position of your element along with the display property.

The position property is a little more confusing than the display property. Don’t worry you’re not the only one who doesn’t know what each position does for your element. Hopefully, this post helps clarify those fuzzy areas.

Elements can be positioned with set top, bottom, left and right value relative to the where it would normally be on the page and sometimes to the page itself. However, the position property determines where they are arranged on the page. There are several position properties:

**Static**: The _default_ position for every element. There is no defined position and the element will flow onto the page as it normally would. You do not need to indicate this position value unless you are trying to override a previously set position. For example, if your website is built on a framework with previously set default positions.

**Relative**: Relatively positioned elements can have a position as long as the additional properties: top, bottom, left and right are set. The additional property will adjust the element away from it’s normal position. No empty spaces are created when you use this position. With this position, you also can use the z-index property. By default (value: auto), the element will appear on top of any other statically positioned element.

_*Note_: You can only use the **z-index** property on _positioned elements_. This property won’t work on statically positioned elements. Z-index controls the stack order of your elements. You can adjust the z-index value to control the appearance of element stack. A higher z-index would place the element in front of another element with a lower stack order and vice versa.

**Fixed**: The absolutely positioned element is positioned relative to the viewport/browser window and it stays in the same position even when the page is scrolled. If you use this position and have flex as your display, absolute positioning will still work on flex containers. However, absolute positioning conflicts with flex children (of a flex container).

**Absolute**: The absolutely positioned element is positioned relative to the nearest positioned ancestor (the parent/container element). If there is no ancestor element then the element positions itself relative to the document body. Unlike the fixed position, with absolute, the element moves with the page when you scroll. With absolute positioning, the element is removed from the flow of other elements on the document. This means that an absolutely positioned element will not affect other elements on your page and vice versa.

**Float**: Wraps text around images and used to be positioned more towards either the _left_ or _right_ side of the page.

**Clear**: Moves floated elements either to the _left_ or _right_ or both to push down the content and have the content appear after the floated element. You can also move the floated element _inline-start_ or _inline-end_.

[Check out the difference between the position properties visually](http://www.barelyfitz.com/screencast/html-training/css/positioning/) and [this is a more detailed documentation on CSS positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning).
