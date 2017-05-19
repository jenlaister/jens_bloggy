---
layout: post
title:  "Go Go Polymorphism"
date:   2017-01-08 11:50:27 -0400
categories: Jen's bloggy
---

![Alt text](/users/jlai/desktop/morphin'.gif)

**Polymorphism** is comprised of the greek root words: **‘polys’** (many) and **‘morphe’** (form or shape) and it means the quality or state of existing in or assuming different forms. In programming, it refers to the ability to use the same methods but in different ways for different objects. Polymorphism allows you to create a more dynamic application.

There are several ways to utilize polymorphism:

**Inheritance:** This is one of the features of Object Orientated Programming (**OOP**). Polymorphism gives us the flexibility to use the same method between different objects.

To achieve this polymorphism, you would make subclasses out of each different type of animal. Each subclass would inherit from the super class, the common interface. Through inheritance, the subclasses now have common methods from their super class. By doing this, it allows flexibility with your super class’s methods in terms of reusability. Your subclasses are then reserved for more detailed behaviors and outputs.

{% highlight ruby %}
class Animal

 def initialize(breed)
   @breed = breed
 end

 def make_some_noise
   puts ""
 end
end
class Cat < Animal
  def make_some_noise
    puts "Mew mew"
  end
end
class Dog < Animal
  def make_some_noise
    puts "Woof woof"
  end
end
class Duck < Animal
  def make_some_noise
    puts "Quackity quack"
  end
end

dog = Dog.new(dog)
dog.make_some_noise # => Woof woof
duck = Duck.new(duck)
duck.make_some_noise # => Quackity quack
{% endhighlight %}

Although our animals are all different types: cat, dog and duck, they do all share the same behavior — each of them can make a noise. Each type just returns a different output. This is where polymorphism steps in. Notice how you can call on the same method on a different object but it’ll return a different output. The make_some_noise method within the subclasses overrides the superclass’s method and puts out the subclasses’ own customized output — polymorphism allows the method to be more dynamic.

You can also use a module in this case because the classes have a shared behavior. With a module, you can’t create an object. A module must be mix-in through “include” in the class. The include allows the class and its’ objects to have the same behaviors declared in the module.

**Duck Typing:**
Remember how Ruby is nice and all about being dynamic…so Ruby is nice enough in that you don’t need a object class hierarchy with the common interface, which would be the super and subclasses defined or inheritance for code dependency. With duck typing you can abstract even further and decouple the classes. In turn, this makes your application even more dynamic because it reduces code dependencies and opens up flexibility. The concept of duck typing is from the below phrase:

Key concept of duck typing: If it walks, quacks and swims like a duck then it must be a duck.
If it walks like a duck, swims like a duck and quacks like a duck, Ruby is is happy enough to treat it as a duck. Ruby won’t waste time with wondering if the object is really a duck. With duck typing, the object is defined by the capabilities — what it can do and not by the type — what it is. The methods within the class are the main concern and if it can be called or not, not the class itself. Thus, even if the *thing* is not an actual duck, Ruby will treat it as a duck.

“[**Duck Typing**](http://rubylearning.com/satishtalim/duck_typing.html) refers to the tendency of Ruby to be less concerned with the class of an object and more concerned with what methods can be called on it and what operations can be performed on it.”
Rather than checking if an object is a specific type, all Ruby cares about is if the object can still answer to a method call. Ruby will allow you to pass any object that answers to a method in another class.

{% highlight ruby %}
class Cat
  def make_some_noise
    puts "Mew mew"
  end
end
class Dog
  def make_some_noise
    puts "Woof woof"
  end
end
class Duck
  def make_some_noise
    puts "Quackity quack"
  end
end
class Animal
  def make_some_noise(animal)
    animal.make_some_noise
  end
end
animal = Animal.new
animal.make_some_noise(Cat.new) #=> Meow mew
animal.make_some_noise(Dog.new) #=> Woof woof
animal.make_some_noise(Duck.new)#=> Quackity quack
{% endhighlight %}

So the above code would still work even with the class decoupled. The make_some_noise method accepts an animal as it’s variable. We can pass the Animal class any object that responds to the make_some_noise method. Once we pass the objects: Cat, Dog, and Duck into the method even if the objects are from different classes. The method just behaves differently and will output differently according to the object. However, the method still works — that’s polymorphism!

Duck typing is a try before you buy type of testing system. If it works, yay! If not, kaaaa — BOOM…it’s going to blow up in your face.

If you want further details about [**duck typing**](https://en.wikipedia.org/wiki/Duck_typing) or if you want to learn about [**polymorphic association**](https://launchschool.com/blog/understanding-polymorphic-associations-in-rails) in rails.
