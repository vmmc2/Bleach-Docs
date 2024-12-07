# Variables

## Overview
A variable, as in most programming languages, can be viewed as just a name associated with a storage location in memory. Such storage location is responsible for holding data that can be changed during the execution of a program.


## Variables in Bleach
In Bleach this is not different. Variables still have this main functionality. However, they have some particularities that might differ from variables in other programming languages. Such peculiarities are listed below:
  * In Bleach, all variables are mutable. In other words, once a variable is declared, any amount of assignments are allowed to be performed on this declared variable.
  * A direct consequence of the particularity explained above is that there is no concept of constants in Bleach.
  * In Bleach, to declare a new variable, the let keyword must be used:
  ```ts
  let s = "A value of type 'str'";
  ```
  * In Bleach, if the declaration of a variable does not have an initializer, then, by default, the variable will store the ```nil``` value:
  ```ts
  let someVariable;
  print someVariable; // nil
  ```
  * Since Bleach is a dynamically-typed programming language, variables do not have types associated with them. Instead, it is the value stored inside of a variable that has a type. The most important consequence of this fact is that a variable can hold values of different types at different points in time:
  ```ts
  let a = "hello";
  print a; // "hello"

  a = nil;
  print a; // nil

  a = 3.14 + 2.71;
  print a; // 5.85
  ```


## Global Variables
__In case you need a refresh, a global variable is just a variable that has been declared outside of all functions, methods or classes, making it accessible from any part of the program.__

Unlike local variables, that are confined to the scope in which they are declared (e.g., within a function), a global one has a larger scope and, thus, can be accessed, modified, or referenced from anywhere in the program, including within functions, methods or other code blocks.

__One point that makes Bleach kind of unique is the fact that the programmer is allowed to redeclare a global variable anytime. This decision was made considering the fact that Bleach's interpreter is not only restricted to execute Bleach files, but can also run in a REPL mode and keeping track of which global variables were declared in such scenario is kind of annoying most of the times. Thus, this implementation decision was made.__

In practice, this means that the line of code below is perfectly valid:
```ts
let pi = 3.14159;
// write some code in the global scope.
let pi = 9.51413;
```


## Local Variables
As expected from most programming language, Bleach supports local variables, which are those declared within a specific block of code, such as a function, method, an ```if-elif-else``` statement or a loop statement (```while```, ```do-while```, ```for```).

In this regard, it is important to remember the reader that the scope of a local variable is limited to the block in which it is defined, meaning it can only be accessed and used within that block. Furthermore, once the block of code finishes executing, the local variable is normally destroyed, and its memory is released.

The code snippet below shows an example of a variable that been declared inside a function and, thus, is an example of a local variable:
```ts
function foo(){
  let bar = "This is a local variable";
  print bar;

  return;
}

foo();
```


## Variable Assignment
As shown above, a variable in Bleach can be declared through the use of the ```let``` keyword.

Moreover, since there is no idea of immutability of variables in Bleach, it is allowed to assign different values of different types at different points in time to the declared variable. To do that, the programmer uses the assignment operator ```=```.

Before moving forward, it is important to explain 2 semantic details of variable assignment in Bleach:
  * The first one is that, in Bleach, an assignment is an expression. Not a statement. This has some interesting consequences. For example, since a variable assignment is an expression, it produces a value. Such value is the one that is being assigned to the variable:
  ```ts
  let foo;
  print foo = 20; // 20
  ```
  * The second one, which is a direct consequence of the first one, is that it is completely possible to assign a value to more than one variable at once in the same assignment expression:
  ```ts
  let x = 20;
  let y = 42;

  x = y = 13;

  print x; // 13;
  print y; // 13;
  ```


## Variable Shadowing
In case you are not familiar (or do not remember), variable shadowing is a process that commonly happens in programming.

It is an effect where a variable declared within a certain scope (typically a local scope) has the same name as a variable in an outer scope.

Then, the inner variable "shadows" or "hides" the outer variable within the scope where it is declared, meaning that within that scope, the inner variable takes precedence, and the outer variable cannot be directly accessed.

The shadowing effect occurs because, before the program actually starts its execution, usually compilers and interpreters (and this includes the Bleach interpreter) do a static-time pass through the source code called "resolving". In this pass, variables are resolved by searching through scopes, starting from the innermost scope and moving outwards. If a variable is found in an inner scope with the same name as one in an outer scope, the inner variable is used, effectively "shadowing" the outer one.

Pay attention to the fact that the shadowing effect is limited to the scope of the inner variable. Once the program exits that scope, the outer variable becomes "visible" to the program again.

The example below shows a clear example of variable shadowing:
```ts
let a = 42;

print a; // 42

{
  let a = "Hello, there!";
  print a; // "Hello, there!" --> In this scope, the variable a that holds the value "Hello, there!" hides the other one that has the same name but stores a different value: 42.
}

print a; // 42
```

Another example, now involving functions:
```ts
let foo = "hi";

print foo; // "hi"

function f(){
  let foo = 42;
  print foo; // 42;

  return;
}

f();

print foo; // "hi"
```
