# Functions

## Overview
A function is a reusable block of code that is usually made by a programmer with the intent to make it perform a specific task.

Functions, as we already know, are fundamental building blocks in programming, allowing programmers to organize, reuse, and manage code more efficiently.


## Functions
In other words, a function is a self-contained block of code that can be ran by calling the its name.

Functions can take inputs (or not), process them, and return an output (or not). They help in breaking down complex problems into smaller, manageable tasks.

Below, you can see a code snippet that shows the structure of a function declaration statement in Bleach:
```ts
function funtionName(parameter1, parameter2, parameter3){
    // Code to execute
    return value;
}
```

__It's important to mention that if the programmer ommits the ```return``` statement from the function declaration statement, then when such function is called, it will, by default, return the ```nil``` value.__


## Function Calls
To execute the function and get the result, you call it by its name and provide the necessary arguments:
```ts
function add(a, b){
    return a + b;
}

let a = 2;
let b = 3;

let result = add(a, b);

print result;  // 5
```

__Important limitations that must be mentioned: In Bleach, functions don't have support optional parameters, nor for default value for its parameters, and also cannot be overloaded.__


## Functions are First-Class citizens
As the title says, in Bleach, function are considered first-class citizens.

This means that functions are treated like any other value in the Bleach:
  * They can be assigned to variables
  * They can be passed as arguments to other functions
  * They can bereturned from functions
  * They can be stored in data structures.
  
Essentially, functions can be manipulated and used just like any other data type available in the Bleach language.


## Anonymous Functions (Lambda Functions)
Bleach also has support for anonymous functions (also known as lambda functions).

If you are not familiar with the concept, then bear with me: An anonymous function is a function that is defined without a name.

In many programming languages, such as C++, JavaScript, Python and Typescrip, these functions are often used for short, simple operations where defining a full named function might be considered an overkill.

Anonymous functions are typically used in situations where a function is required only temporarily, often as an argument to another function.

In Bleach, this is not different.

When it comes down to syntax, Bleach took the Python approach to this problem and added a little twist aiming for more readability. It uses the ```lambda``` keyword and also the arrow operator ```->```.

When it comes to semantics, rest assured. Bleach anonymous/lambda functions are as powerful as the normal ones.

The example below shows how to define an anonymous/lambda function and call it:
```ts
let add = lambda -> (x, y){ return x + y; };

print add(10, 5); // 15
```