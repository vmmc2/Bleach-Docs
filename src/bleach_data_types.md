# Data Types


## Overview
* In short, Bleach's built-in types are just the 5 listed below (4 built-in types have been implemented by now):
  * __Scalar Types:__
    * ```bool```
    * ```num```
    * ```nil```
  * __Compound Types:__
    * ```str```
    * ```list``` (Not implemented yet)

* It's important to mention that such built-in types are divided into two groups: __scalar types__ and __compound types.__ I'll walkthrough each of such groups and their respective types, giving brief explanations and examples.


## Scalar Types
* A scalar type is a type that can only represent a single value. As seen above, Bleach has three primary scalar types: ```bool```, ```num``` and  ```nil```. You may recognize these from other programming languages. Let’s see how they work in Bleach:

### (1) Type ```bool```
* The Boolean type. Such type is used to perform logical operations and is vastly used in logic and Boolean algebra.
* In Bleach, things are not different, we have two possible values for such type (and, obviously, a literal for each value):
```c++
true
false
```

### (2) Type ```num```
* For the sake of simplicity, Bleach has only one type to represent numbers: the ```num``` type.
* Behind the scenes, such type is implemented using a double-precision floating point number (The C++ ````double``` type).
* I implemented it this way because double-precision floating point numbers can also represent a wide range of integers, covering a lot of territory, while maintaining the simplicity that I innitialy envisioned.
* Usually, mature and popular programming languages have lots of syntax for numbers (binary, hexadecimal, octal, scientific notation, etc).
* Since Bleach's purpose is to be a programming language , we'll settle for basic integer and decimal literals, like the ones shown below:
```c++
2.71828
3.14159
23
```

### (3) Type ```nil```
* This is an old friend to many of us.
* The nil type is a type that has only one value (```nil```). It conveys the idea of “no value” or "absence of a value".
```ruby
nil
```
* In other programming languages, such type is called ```null```, ```nil```, ```NULL``` or ```nullptr```.
* Here, in Bleach, we are going to follow Ruby's influence and use ```nil``` to denote this idea. This will help us distinguish between Bleach's ```nil``` value and C++ ```nullptr``` value (which is the equivalent value in the underlying implementation language).
* I know what you might be thinking right now... There are lots of arguments for not having a null value in a language since null pointer errors have been causing a lot of headache since Tony Hoare introduced this idea back in the 60s.
* However, according to Robert Nystrom (author of the "Crafting Interpreters" book and creator of the Lox programming language, which are both the major references Bleach where got its inspiration), if you want to implement a statically-typed language, it would be worth trying to ban NULL values. However, in a dynamically-typed language (which is Bleach's case), eliminating it is often more annoying and troublesome than allowing it. So I opted to follow Nystrom's advice on this matter.


## Compound Types
* Compound types are basically types that can group multiple values into one. Bleach has two primitive compound types: ```str``` and ```list```. Let's take a look at them:

### (4) Type ```str```
* Again, nothing new here. If you have some experience with programming you already recognize this type. In Bleach, the ```str``` type represents an indexed-sequence of characters (a string), typically used to store and manipulate text.

* Some examples of literal values of this type:
```c++
"I am a string";
""; // The empty string.
"123"; // This is a string, not a value of type "num".
```

* There are some aspects of this type that might differ from what you have seen in the previous languages you have worked with. Thus, I think it's a good idea to explain such aspects in more details:
  * It's a sequence type. This means that value of the ```str``` type can be indexed. Indexing allows you to access individual characters from the value (which, in Bleach, are also values of type ```str```).
  * In Bleach, literals values of this type are __always__ enclosed by double quotes.
  * Finally, this type has the following methods associated with it:
    * __```clear```:__ Returns ```nil```. This method cleans the contents from the value of ```str``` type. This change is made in-place.
    * __```empty```:__ Returns a ```bool``` value that signals whether the ```str``` value is empty or not.
    * __```find```:__ Returns a ```num``` value that identifies the index where there is the first occurrence of a provided substring (a value of type ```str```) inside another value of type ```str```. If the provided substring doesn't appear, the method returns ```-1```.
    * __```length```:__ Returns a ```num``` value that represents the number of characters in the ```str``` value.
    * __```pop_back```:__ Returns a ```str``` value. This method removes the last character from the ```str``` value.
    * __```push_back```:__ Returns ```nil```. This method adds another value of type ```str``` at the end of the ```str``` value.
    * __```size```:__ Returns a ```num``` value that represents the number of characters in the ```str``` value.
    * __```substr```:__ Returns a value of type ```str``` which is the substring of another value of type ```str```. Such method expects two indexes (left, right), both of which are inclusive.

### (5) Type ```list```
* If you are familiar with Python, then here it is an old friend of you. In Bleach, the ```list``` type represents an indexed-sequence of elements.

* Some examples of literal values of this type:
```c++
[0, 1, 2, 3, 2.71, 3.14159]; // A list where all elements are of type "num".
["hello", "there"]; // A list where all elements are of type "str".
[]; // An empty list.
[false, true]; // A list where all elements are of type "bool".
[nil, nil, nil]; // A list where all elements are of type "nil".
[false, "Brazil", 9.98, true, nil]; // A list where elements are of different types. This is allowed in Bleach.
```

* There are some aspects of this type that might differ from what you have seen in the previous languages you have worked with. Thus, I think it's a good idea to explain such aspects in more details:
  * It's a sequence type. This means that lists can be indexed. Indexing allows you to access individual elements from the list.
  * Finally, this type has the following methods associated with it:
    * __```back```:__ Returns the last element of a value of type ```list```. However, it does not make any changes to the value of type ```list```.
    * __```clear```:__ Returns ```nil```. This method cleans the content from the value of ```list``` type. This change is made in-place.
    * __```empty```:__ Returns a ```bool``` value that signals whether the ```list``` value is empty or not.
    * __```front```:__ Returns the first element of a value of type ```list```. However, it does not make any changes to the value of type ```list```.
    * __```pop_back```:__ Returns the last element of a value of type ```list```. This method removes the last element from the ```list``` value.
    * __```push_back```:__ Returns ```nil```. This method adds an element of any type (whether it's a built-in or user-defined one) at the end of the ```list``` value.
    * __```size```:__ Returns a ```num``` value that represents the number of elements in the ```list``` value.
