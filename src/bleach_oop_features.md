# Object-Oriented Programming Features

## Overview
This means that Bleach not only supports, but also encourages programmers to use the key concepts behind object-oriented programming. Which makes Bleach a multi-paradigm language due to the fact it also follows concepts of procedural paradigm. 

In case you don't remember, OOP is a paradigm or style of programming that uses "objects" to represent data and methods to manipulate that data.

__The key concepts of OOP include encapsulation, inheritance, polymorphism, and abstraction.__

__The concepts that were mentioned above are what enable the creation of modular, reusable, and maintainable code by organizing software into objects, entities that are capable of representing both data and behavior.__

## Classes
A class is basically a blueprint for creating objects (instances).

Usually, a class defines a set of attributes (variables) and methods (functions) that the created objects will have as its disposal.

Classes are a fundamental part of object-oriented programming (OOP) due to the fact that such featus allows the programmer to define custom data types and their associated behaviors based on his/her/their needs.

__When it comes down to the concept of classes, there are a couple of concepts that directly tied to it:__
1. __Attributes/Fields__
2. __Methods__
3. __Instances__
4. __Inheritance__

For the rest of this page, I am going to explain how each of these concepts are handled in Bleach.

In Bleach, a class declaration statement follows the syntax shown below:
```c++
class Person{
  method init(name, age){
    self.name = name;
    self.age = age;
  }

  method greet(){
    return "Hello there! " + "my name is " + self.name + " and I have " + self.age + " years.";
  }
}
```

## Attributes/Fields
Usually, in statically-typed programming languages, attributes/fields are variables that belong to the class itself.

Attributes are used to store data that is relevant to the objects that were created from the class.

However, when dealing with dynamically-typed languages (such as JavaScript or Python), this concept is a little bit different.

__In Bleach's case, attributes/fields are unique to each instance of a class. This means that there is no concept of class attributes/fields. In other words, there aren't attributes/fields that are shared across all instances of the class and, thus, be affected by a change in an instance.__

__The Bleach code snippet below shows the flexibility of dealing with attributes/fields when it comes down to classes and instances. The programmer is free to add new attributes/fields after the creation of the instance from a class with no issues:__
```c++
class Square{
  method init(length){
    self.length = length;
  }
}

let square = Square(5);

square.area = square.length * square.length;
print square.area; // 25

square.perimeter = 4 * square.length;
print square.perimeter; // 20

function compute_square_diagonal(length){
  return std::math::sqrt(2) * length;
}

square.compute_diagonal = compute_square_diagonal;
print square.compute_diagonal(square.length); // 7.071067811865476
```

## Methods
A method is just a function that belongs to a class and is responsible for defining actions and behaviors that objects created from the class can execute at runtime.

Usually, methods typically operate on the data that is stored inside the attributes/fields of an instance and,thus, can modify the state of the instance.

Making it very simple, a method is essentialy a function that is tied to a class definition.

__As seen above, in a class declaration statement, if the programmer wants to declare a new method, then he/she/they just need to follow the same syntax of a function declaration statement, but instead of using the ```function``` keyword, change it by the ```method``` keyword.__

__The ```init``` method:__ It's just a special method usually present in classes and known as the constructor of a class. It’s automatically called when a new instance of the class is created. This method is where the programmer typically sets up the initial state of an object by initializing instance attributes.

## Instances
Essentialy, an instance is an individual object created from a class.

Remember that each instance has its own unique set of attributes/fields, but shares methods with other instances of the same class.

__In short, you can think of an instance of just a bag of data that can change during runtime and that has methods associated with it that might operate on such data.__

## Self
The keyword ```self``` serves for a very specific purpose inside the methods of a class: It's a reference to the current instance of the class. It's used to refer to the current instance on which a method is being invoked.

By using it, the progammer is able to access and modify the instance’s attributes and methods. Contrary to Python's approach, in Bleach the name ```self``` is mandatory if the programmer wants to refer to the current instance of the class. 

## Inheritance
__As we all know, inheritance is a fundamental concept in object-oriented programming which allows a class to inherit attributes and methods from another class.__

__The major purpose for the existence of inheritance is to promote code reuse and to establish a natural hierarchy between classes.__

__In Bleach, as in other popular languages such as C++, C#, Java , JavaScript and Python, inheritance allows the programmer to create a new class based on an existing class, extending or modifying its functionality.__

Going further, Bleach follows a very similar implementation of inheritance to that of Python with just one major difference: __For simplicity purposes, Bleach only supports single inheritance whereas Python has support for multiple inheritance (Talking about this, such a thing can be easily added to the Bleach Interpreter and it's a good practice for students to deepen their knowledge).__

As usual, the code snippet below shows how inheritance, method overriding and the ```super``` keyword work in practice:
```c++
class Animal{
  method init(name){
    self.name = name;
  }

  method speak(){
    std::io::print(self.name, "makes a sound.");
  }
}

class Dog inherits Animal{
  method init(name, breed){
    super.init(name);
    self.breed = breed;
  }

  method speak(){
    std::io::print(self.name, "is a ", self.breed, "and barks.");
  }
}

class Cat inherits Animal{
  method init(name, breed){
    super.init(name);
    self.breed = breed;
  }

  method speak(){
    std::io::print(self.name, "is a ", self.breed, "and meows.");
  }
}

let dog = Dog("Thor", "Rottweiller");
dog.speak(); // "Thor is a Rottweiller and barks."

let cat = Cat("Felicia", "Siamese");
cat.speak(); // "Felicia is a Siamese and meows."
```
