# Comments

## Overview
Ideally, every programmer tries its best to make their code readable and understandable. However, there might be scenarios in which extra explanation is very welcomed.

In such scenarios, programmers leave comments in their code that the compiler/interpreter will ignore but people reading the code may find useful.

In Bleach, a programmer is allowed to write two different types of comments inside the code present in a Bleach file (```.bch```).


## Single-Line Comments
In Bleach, a single-line comment starts with two slashes (```//```), and the comment continues until the end of the line, just like the example below:
```c
// Here you can put some extra information that the person reading your code might find useful.
```
For comments that extend beyond a single line, you’ll need to include ```//``` on each line, like this:
```c
// This is the beginning of what it's going to be a very long comment.
// Instead of making the user go all the way to the end of the line above
// we can divide comments in different lines. However, always needing to use
// // character seems to be very cumbersome.
```
Remember that comments can also be placed at the end of lines containing code:
```ts
let x = 123.45; // It's allowed to put a comment after a line of code.
```
However, Bleach, as Rust, recommends that the comment should appear on a separate line above the code it’s annotating:
```ts
// The variable below holds an approximate value of the constant Pi.
let pi = 3.14159;
```


## Multi-Line Comments
For the reason mentioned above, Bleach also has support for multi-line comments.

In Bleach, a multi-line comment has a beginning and also and ending. The beginning is denoted by a ```/*```, while the ending is denoted by a ```*/```. Everything that is written between these characters is considered a comment and, therefore, will be ignored by the Bleach Interpreter during runtime.

The example below shows how to use them properly:
```ts
/*
This
is
a
multi-line
comment.

Below, we are storing an
approximation of Euler's
constant inside the variable "e".
*/
let e = 2.71;
```
