# Data Types

## Overview
In short, Bleach's built-in types are just the 6 listed below:
  * ```bool```
  * ```num```
  * ```nil```
  * ```str```
  * ```list```
  * ```dict```

It's important to mention that such built-in types are divided into two groups: __scalar types__ and __compound types.__ I'll walkthrough each of such groups and their respective types, giving brief explanations and examples.

## Scalar Types
A scalar type represents a single value. Bleach has three primary scalar types: ```num```, ```bool``` and  ```nil```. You may recognize these from other programming languages. Let’s see how they work in Bleach:

### 1) ```bool```
The Boolean type. Such type is used to perform logical operations and is vastly used in logic and Boolean algebra. In Bleach, things are not different, we also just have two possible values for such type (and, obviously, a literal for each value):
```c++
true
false
```
### 2) ```num```
For the sake of simplicity, Bleach has only one type two represent numbers: the ```num``` type. Such type is actually a double-precision floating point number. I implemented it this way because double-precision floating point numbers can also represent a wide range of integers, covering a lot of territory, while maitaining the simplicity that I wanted.

Usually, mature and popular programming languages have lots of syntax for numbers (hexadecimal, octal, scientific notation, etc). Since this is a basic (yet functional language), we'll settle for basic integer and decimal literals, like the ones shown below:
```c++
2.71828
3.14159
23
```

### 3) ```nil```
This is an old friend to many of us. The nil type is a type that has only one value (```nil```). It represents “no value” or "the absence of a value".
```ruby
nil
```

It’s called “null” or "nil" or "NULL" or "nullptr" in many other languages. Here, in Bleach, we are going to follow the Ruby and Crystal conventions and use "nil". This will help us distinguish between Bleach's ```nil``` value and C++ ```nullptr``` value (which is our underlying implementation language).

I know what you might be thinking right now... There are lots of arguments for not having a null value in a language since null pointer errors have been causing a lot of headache since Tony Hoare introduced this idea in Computer Science.

According to Robert Nystrom, If you want to implement a statically-typed language, it would be worth trying to ban it. However a dynamically-typed one (which is Bleach's case), eliminating it is often more annoying than having it.


## Compound Types
Compound types can group multiple values into one type. Bleach also has three primitive compound types: ```str```, ```list``` and  ```dict```. Let's take a look at them:

### 4) ```str```
Nothing new here. In Bleach, the ```str``` type represents a sequence of characters (a string), typically used to store and manipulate text.

Some examples of literal values of this type:
```c++
"I am a string";
""; // The empty string.
"123"; // This is a string, not a number.
```

__There are some aspects of this type that might differ from what you have seen in the previous languages you have worked with. Thus, I think it's a good idea to explain such aspects in more details:__
* __In Bleach the values of this type are immutable, meaning once it's is created, it cannot be changed.__
* __It's a sequence type. This means that strings can be indexed. Indexing allows you to access individual characters.__
* __In Bleach, literals values of this type are always enclosed in double quotes.__
* __Finally, this type has some methods associated with it, which are useful. Such methods are:__
  * fdf
  * dfdfd
  * dfdfd
  * fdf

### 5) ```list```

### 6) ```dict```
