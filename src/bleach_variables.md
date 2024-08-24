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

The fourth one is that, if during the declaration of a variable, an initializer is not provided, then, by default, the variable will store the ```nil``` value inside itself:
```ts
let someVariable;
print someVariable; // nil
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

Moreover, since there is no idea of immutability of variables in Bleach, it's allowed to assign different values of different types at different points in time to the declared variable. To do that, the programmer uses the assignment operator ```=```.

However, I would like to present some interesting semantics related to variable assignment in Bleach.

The first one is that, in Bleach, an assignment is an expression. Not a statement. This has some interesting consequences.

For example, since a variable assignment is an expression, it produces a value. Such value is the one that is being assigned to the variable:
```ts
let foo;
print foo = 20; // 20
```

The second one is that it's completely possible to assign a value to more than one variable at once in the same assignment expression:
```ts
let x = 20;
let y = 42;

x = y = 13;

print x; // 13;
print y; // 13;
```


## Variable Shadowing
In case you are not familiar (or don't remember), variable shadowing is a process that commonly happens in programming.

It's an effect where a variable declared within a certain scope (typically a local scope) has the same name as a variable in an outer scope.

Then, the inner variable "shadows" or "hides" the outer variable within the scope where it is declared, meaning that within that scope, the inner variable takes precedence, and the outer variable cannot be directly accessed.

The shadowing effect occurs because, before the program actually starts its execution, usually compilers an interpreters (and this includes the Bleach interpreter) do a static-time pass through the source code called "resolving". In this pass, variables are resolved by searching through scopes, starting from the innermost scope and moving outward. If a variable is found in an inner scope with the same name as one in an outer scope, the inner variable is used, effectively "shadowing" the outer one.

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
