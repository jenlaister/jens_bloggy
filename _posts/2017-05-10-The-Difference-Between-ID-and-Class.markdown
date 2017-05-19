---
layout: post
title:  "The-Difference-Between-ID-and-Class"
date:   2017-05-10 11:50:27 -0400
categories: Jen's bloggy
---

When I was reviewing object oriented CSS, I came across class and id for HTML element definition. I knew that both were similar in that each one can define elements to build HTML markups. However, I realized that I didn’t know the exact difference between the two and in which cases I should use one over the other or even both.

So, what is the difference?

Id is the primary identity of an element whereas class is the secondary. They both differ in reusability. Ids are unique and should only be used once for that one particular element. Classes are not unique and the same class can be used on multiple elements. Thus classes are reusable for elements throughout your markup.

_To remember the difference — id is the unique name of an element and class is a type of element._

When you use an id to identify an element, this also will be the hash value in your URL.

ex: http://website.com#post
_*post is your element id_

The uniqueness of ids allows JavaScript to use the function getElementById to help identify and extract that specific element. At the same time, the browser uses the id of an element to locate and bring to focus that specific element on the page into view.

In what cases do you use id over class and vice versa?

Use id to identify your element if it is unique and there is only ONE of that particular element on the page.

If you want to style multiple elements with the same styling, use class to identify your element. An element can also take on more than one class if you want to apply multiple styles to that element. Classes can define either visual or behavioral styling.

How to define an id and class?

In your markup/HTML, you can define an id and class on the same element because they are different from each other:

<div id='idName' class='className'>
  </div>

OR you can define them separately if you want different styles on each element:

<div id='idName'>
  <div class='className'>
    </div>
  </div>

In CSS, you need ids or classes to help identify the select element you want to apply your styling on. You can use the prefix **.** to define your id and **#** for class.

div#id {
  align-text: center;
}

div.class {
  display: relative;
}

For object oriented CSS, you do not need to define both the element AND Id or element AND class. You would just need to define the id (#) or class (.).


#id {
  align-text: center;
}

.class {
  display: relative;
}
