# Variables

## Overview
As you might already know, in a programming language, a variable is just a name associated with a storage location in memory. Such storage location is responsible for holding data that can be changed during the execution of a program.

Another way to think about this is that variables allow us, developers, to store, retrieve and manipulate data by using the variable's name instead of needing to interact with the memory address where variable's data is at.

## Variables in Bleach
__The first point that is important to mention when it comes to variables in the Bleach language is that all of them are mutable.__ 

Which means that, once a variable is declared, the programmer is allowed to perform any amount of assignments later on the program that is being written.

__The second point that must be mentioned is that there is no concept of constants in Bleach. There are just mutable variables, as explained above.__

The third point is that, in order to declare a new variable in Bleach, the programmer must use the ```let``` keyword:
```ts
let variable = "A str value";
```

The last point, and maybe the most important of them all, is that since Bleach is a dynamically-typed programming language, its variables don't have types associated with them. __Instead, it's the values that have types.__ The most important implication of this is that a variable can hold a value of any type at different points in time.

In practice, Bleach allows the code snippet below with no problems:
```ts
let a = "hello";
print a; // "hello"

a = 42;
print a; // 42
```

## Global Variables
__In case you need a refresh, a global variable is just a variable that has been declared outside of all functions, methods or classes, making it accessible from any part of the program.__

Unlike local variables, that are confined to the scope in which they are declared (e.g., within a function), a global one has a larger scope and, thus, can be accessed, modified, or referenced from anywhere in the program, including within functions, methods or other code blocks.

__One point that makes Bleach kind of unique is the fact that the programmer is allowed to redeclare a global variable anytime. This decision was made considering the fact that Bleach's interpreter is not only restricted to execute Bleach files, but can also run in a REPL mode and keeping track of which global variables were declared in such scenario is kind of annoying most of the times. Thus, I opted to make this implementation decision.__

Essentialy, this means that the line of code below is perfectly valid:
```ts
let pi = 3.14159;
// write some code in the global scope.
let pi = 9.51413;
```

## Local Variables
Refreshing your mind: a local variable is a variable that is declared within a specific block of code, such as a function, method, an if statement or a loop statement. By the way, this is exactly how local variables work in Bleach.

The scope of a local variable is limited to the block in which it is defined, meaning it can only be accessed and used within that block.

Once the block of code finishes executing, the local variable is typically destroyed, and its memory is released.
