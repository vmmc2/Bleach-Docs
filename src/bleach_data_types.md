# Data Types

## Overview
In short, Bleach's built-in types are just the 5 listed below. These data types are divided into 2 categories (Scalar Types and Compound Types):

* __Scalar Types:__
  * ```bool```
  * ```nil```
  * ```num```

* __Compound Types:__
  * ```list``` 
  * ```str```


## Scalar Types
A scalar type is a type that can only represent a single value. As seen above, Bleach has three primary scalar types: ```bool```, ```nil``` and  ```num```. You may recognize these from other programming languages. Let’s see how they work in Bleach:

### Type: ```bool```
This data type is used to represent one of two possible values: true or false. Such values are used to express logical conditions and to control the execution of certain parts of a program’s source code. As in other languages, the only two possible values for this specific data type are:
```c++
true
false
```

In this context, it is important to mention that Bleach takes inspiration from Ruby and other modern programming languages and implement the concept of "truthy" and "falsey" values in order to evaluate the truthiness or the falseness of values when they are being evaluated inside ```if``` statements, loops (```while```, ```do-while```, ```for```) and ternary operators (```condition ? expression_1 : expression_2```).

Essentially, this means that, in Bleach, values of any type (built-in or user-defined) can be used in places where a value of type ```bool``` is expected. Moreover, Bleach opted to follow the same convention of Ruby in this matter:
  * __Falsey values:__ ```false```, ```nil```.
  * __Truthy values:__ Any other value that is not ```false``` nor ```nil```.

### Type: ```nil```
This type is an old acquaintance for most programmers. The nil type has just one possible value, the ```nil``` value. In short this value conveys the idea of "no value" or the "absence of a value".
```ruby
nil
```

In other programming languages, such type might be called ```null```, ```nil```, ```NULL``` or ```nullptr```. Here, in Bleach, we are going to follow Ruby's influence and use ```nil``` to denote this idea. 

It is common knowledge that there are lots of arguments for not having such type in a language since null pointer errors have been causing a lot of headache since Tony Hoare introduced this idea back in the 60s.

However, according to Robert Nystrom (author of the "Crafting Interpreters" book and creator of the Lox programming language, which are both the major references Bleach where got its inspiration), if you want to implement a statically-typed language, it would be worth trying to ban this type. However, in a dynamically-typed language (which is Bleach's case), eliminating it is often more annoying and troublesome than allowing it. Thus, Nystrom's advice was followed on this matter.

### Type: ```num```
In favor of simplicity, Bleach has only one type to represent numbers: the ```num``` type. This type can be used to represent both integers and floating-point numbers.

Behind the scenes, this type is implemented with a double-precision floating-point type, which allows Bleach to cover a lot of territory when it comes to numerical values while still keeping the simplicity initially envisioned for the language.

Usually, mature and popular programming languages have lots of syntax for numbers (binary, hexadecimal, octal, scientific notation, etc).

Since Bleach's purpose is to be an educational programming language, it has support for just basic integer and decimal literals, like the ones shown below:
```c++
2.71828
3.14159
23
-16
-9.9845
```


## Compound Types
Compound types are basically types that can group multiple values into one. Bleach has two primitive compound types: ```list``` and ```str```. Let's take a look at them:

### Type: ```list```
Taking inspiration from Python, Bleach has this type. Here, the ```list``` type represents a linear-sequence of elements. As previously stated, Bleach is a dynamically-typed language, just like Python. Thus, the ```list``` type can store values of different typeswith no issues. Moreover, Bleach has support for list literals, just as the ones shown below:
```c++
[0, 1, 2, 3, 2.71, 3.14159]; // A list where all elements are of type "num".
["hello", "there"]; // A list where all elements are of type "str".
[]; // An empty list.
[false, true]; // A list where all elements are of type "bool".
[nil, nil, nil]; // A list where all elements are of type "nil".
[false, "Brazil", 9.98, true, nil]; // A list where elements are of different types. This is allowed in Bleach.
```

There are some aspects of this type that might differ from what you have seen in the previous languages you have worked with. The ```list``` type in Bleach has the following useful methods that makes the student’s life easier when working with this type.

Finally, this type has the following methods associated with it:
  * __```append```:__ Responsible for adding one value of any type to the end of the list value it was called on. Returns ```nil```.
  * __```clear```:__ Method responsible for deleting every element that is currently stored inside
the list value it was called on. Returns ```nil```.
  * __```empty```:__ Responsible for checking whether the list value it was called on currently
has values stored inside it or not. Returns a ```bool``` value.
  * __```fill```:__ Responsible for resizing the list value it was called on to a provided size and
also filling all of its indexes with a provided value of any type. Returns ```nil```.
  * __```getAt```:__ Responsible for returning the value present at the provided index. Returns
a value of any type.
  * __```pop```:__ Responsible for deleting and returning the last element present inside a list
value, if any. Returns a value of any type.
  * __```setAt```:__ Responsible for setting the value stored at the provided index to the value
that was provided. Returns ```nil```.
  * __```size```:__ Responsible for checking and returning the current amount of elements that
the list value it was on called on currently has. Returns a ```num``` value.

__Side Note #1: The ```list``` type does not have support for indexing using square brackets (```[]```). However, by using the methods ```getAt``` and ```setAt``` one can obtain the same behavior.__

__Side Note #2: It is important to highlight that any misuse of the methods presented above will result in a runtime error during the program’s execution.__

### Type: ```str```
Also taking inspiration from Python, Bleach has this type. The str type represents an indexed-sequence of characters (a string), typically used to store and manipulate text. Just as the ```list``` type, Bleach also has support for literal values of this type, as shown below:

```c++
"I am a string";
""; // The empty string.
"123"; // This is a string, not a value of type "num".
```

There are other aspects about the str type that must be mentioned.

First of all, it is important to recall that it is a sequence type. In short, it means that values of this  type can be indexed. In a string, indexing usually allows the programmer to access individual characters from the value, which, in the Bleach programming language, are also values of the ```str``` type.

Also, in Bleach, literals values of this type are always enclosed by double quotes (```""```).

Finally, as in Python, this type has the some methods available:
  * __```empty```:__ Responsible for checking whether the str value it was called is equal to ""
or not. Returns a bool value.
  * __```find```:__ Responsible for trying to figure out if the provided sub-string (a str value)
exists within the str value the method was called on. Returns a num value which
denotes the index at which the sub-string appears, otherwise returns -1.
  * __```getAt```:__ Responsible for returning the str value of length 1 present at the provided
index. Returns a str value.
  * __```length```:__ Responsible for checking and returning the current amount of characters
(which are also values of type str) that the str value it was on called on currently
has. Returns a num value.
  * __```split```:__ Responsible for generating a list where each value is of str type. This
method receives as its unique argument a value of str type that works as the sepa-
rator. Returns a list value.
  * __```setAt```:__ Responsible for setting the value stored at the provided index to the value
that was provided (which must be a str value of length 1). Returns nil.
  * __```substr```:__ Responsible for retrieving a sub-string from the str value it was called on.
The method receives two arguments of num type that work as the start and end
delimiters. Returns a str value.

__Side Note #1: The ```str``` type does not have support for indexing using square brackets (```[]```). However, by using the methods ```getAt``` and ```setAt``` one can obtain the same behavior.__

__Side Note #2: It is important to highlight that any misuse of the methods presented above will result in a runtime error during the program’s execution.__
