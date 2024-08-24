# Control Flow Structures

## Overview
Control Flow Structures are constructs that dictate the order in which statements are executed. They allow the program to make decisions, repeat operations, and manage the flow of execution based on certain conditions.

## Conditional Statements
Such statements allow the program to execute certain blocks of code based on whether a condition evaluates to ```true``` or ```false```.

### ```if``` Statement
The ```if``` statement is one of the fundamental control flow structures in programming.

It allows the program to execute a block of code only if a specified condition is true.

If the condition is false, then the code block associated to the ```if``` is not executed, and alternative blocks of code can be executed by using ```elif``` clauses or an ```else``` clause.

Remember that, during runtime, the clauses of an ```if``` statement are evaluated from top to bottom. Also, once the condition of a clause is met, its associated block will be executed and then the rest of clauses won't even be looked at by the interpreter. Instead, it goes straight forward to the next statement. Bleach is no exception in this matter.

Also remember that is completely possible to nest an infinite amount of ```if``` statements in a program. Bleach can handle such scenarios with no issues.

It's important to mention that one does not need to add a block after an ```if```, ```elif``` or ```else``` clause. This means that the code snippet below executes without any problems:
```ts
let foo = "hi";

if(foo == "hi")
  print "Found a 'hi' string!";
elif(foo == "oi")
  print "Fount an 'oi' string!";
else
  print "Found something else inside the 'foo' variable";
```

__Last but not least, Bleach, different from some other programming languages, allows the programmers to declare variables inside the code blocks associated to the clauses of an ```if``` statement. If you do this, you must keep in mind that the scope of such variable will be restricted to the block associated to the specific clause.__

Simple example of a code snippet that uses an ```if``` statement:
```ts
let number = 2;

if(number == 3){
  print "The value of 'number' is 3.";
}elif(number == 2){
  print "The value of 'number' is 2."; // "The value of 'number' is 2."
}else{
  print "The value of 'number is something else.";
}
```

Another example of a code snippet that also uses an ```if``` statement. However, now there are nested ```if``` statements:
```ts
let n = 42;
let s = "Meaning of life";

if(n == 42){
  if(s == "Meaning of life"){
    print "The value of n is 42 and the value of s is not 'Meaning of life'";
  }else{
    print "The value of n is 42 and the value of s is not 'Meaning of life'";
  }
}else{
  print "The value of n is not 42";
}
```


## Loops
Loop statements are used to repeat a block of code multiple times, either a fixed number of times or until a certain condition is met.

One important thing to mention is that, for all types of loop structures, there is support for early exiting (with the ```break``` keyword) and iteration skipping (with the ```continue``` keyword).

### While
This one is a control flow structure present in almost every programming language that allows the programmer to repeatedly execute a block of code as long as a specified condition remains true.

It is typically used when the number of iterations is not known beforehand and the loop should continue while a certain condition is met. When such condition is not met anymmore, then the execution of the loop terminates.

Also remember that the condition of a ```while``` loop is evaluated before each iteration of the loop. Which means that, in some cases, the ```while``` loop might not even execute.

Another thing that is important to mention is that the programmer can use a variable of any type as the condition of a ```while``` loop.

__As we've seen, each value, no matter its type is considered either "truthy" or "falsey". In practice, this means that you don't need to necessarily only use values of type ```bool``` or expressions that evaluate to such type.__

__One important peculiarity of ```while``` loops in Bleach is that they need a block after the condition. In practice, this means that the following code snippet will not even execute:__
```ts
let counter = 0;

while(counter < 10) // No block present.
  counter = counter + 1;
```

__However, the following code snippet executes without any problems:__
```ts
let counter = 0;

while(counter < 10){ // A block is present.
  counter = counter + 1;
}
```

### Do-While Loop
This is another a type of control flow structure very similar to the ```while``` loop present above and that is ubiquitous in programming languages.

A ```do-while``` executes a block of code at least once before checking its condition.

That is key difference between a ```do-while``` loop and a regular ```while``` loop: the condition in a ```do-while``` loop is checked after the loop’s code has executed, not before. This guarantees that the loop’s code will always run at least once, even if the condition evaluates to the ```false``` value. This might sound problematic, but there are some niche scenarios where this behavior comes in handy.

Another thing that is important to mention is that, as the programmer could use a variable of any type as the condition of a ```while``` loop, he/she/they can do the same thing in a ```do-while``` loop.

As we've seen, each value, no matter its type is considered either "truthy" or "falsey". In practice, this means that you don't need to necessarily only use values of type ```bool``` or expressions that evaluate to such type.

__Last, but not least, as the ```while``` loops require, the ```do-while``` loops in Bleach need a block between the keywords ```do``` and ```while```. In practice, this means that the following code snippet will not even execute:__
```ts
let counter = 0;

do
  counter = counter + 1;
while(counter <  10);
```

__On the other hand, the following one will execute without any issues:__
```ts
let counter = 0;

do{
  counter = counter + 1;
}while(counter < 10);
```

### For Loop
Finally! Here is the last kind of control flow structure that fits into the loops category. The ```for``` statement is a control flow structure that allows the programmer to repeatedly execute a block of code not only by a specific number of times but also until some condition evaluates to ```true```.

Unlike the ```while``` and ```do-while``` loops, a ```for``` loop is particularly useful in scenarios where the developer knows in advance how many times he/she/they want such loop to iterate.

In case you don't remember the structure of a ```for``` loop, let's do a simple refresh: A ```for``` loop has 4 components, which are:
* __Initialization:__ This is where you declare and initialize a loop control variable. This happens only once, at the beginning of the loop. __In Bleach, the programmer is also allowed to put an expression statement in this place.__
* __Condition:__ This is a logical expression that is evaluated before each iteration of the loop. If the condition evalutes to ```true```, the loop continues. Otherwise, if it evaluates to ```false```, the loop finishes its execution.
* __Increment:__ This is an expression that updates the loop control variable after each iteration. It usually increments or decrements the loop variable. To be honest, this can be any kind of expression. Not necessarily an expression that updates the loop control variable of the ```for``` loop.
* __Code Block:__ The block of code that will be executed each time the condition is true.

__It's also important to mention that the first three components might be absent inside the structure of a ```for``` loop.__

In short, this is the expected structure of a ```for``` loop in Bleach:
```ts
for(initialization; condition; increment){
  // the code of the block goes here.
}
```


__Last, but not least, as the ```while``` and ```do-while``` loops require, the ```for``` loops in Bleach need a block between the keywords after its ```)``` character. In practice, this means that the following code snippet will not even execute:__
```ts
for(let counter = 0; counter < 10; counter = counter + 1)
  print counter;
```

__On the other hand, the following one will execute without any issues:__
```ts
for(let counter = 0; counter < 10; counter = counter + 1){
  print counter;
}
```


## Branching
Branching statements allow the program to jump to a different part of the code based on certain conditions during runtime.

__In Bleach, there are just two keywords that allow the user to execute such statements:__
  * ```break```
  * ```continue```

The statements that use these keywords are used to control the flow of loops (```for```, ```while``` and ```do-while```) statements.

They provide mechanisms that allow the programmer to modify the normal flow of loop execution based on particular conditions. This is useful when the developer wants to exit a loop early based on a dynamic condition instead of waiting for the loop to naturally complete all its iterations.

### The ```break``` keyword/statement
This statement is used to immediately exit a loop.

When the ```break``` statement is encountered (```break;```), the program stops the execution of the innermost loop that contains such statement and goes on to the first line of code after such loop block.

__Usage of the ```break``` statement inside a loop in Bleach:__
```ts
for(let counter = 0; counter < 10; counter = counter + 1){
  if(counter == 9){
    break;
  }
  print counter;
}
```

__The output of the code snippet above will be:__
```txt
0
1
2
3
4
5
6
7
8
```

### The ```continue``` keyword/statement
The statement is used to skip the remaining code in the current iteration of a loop and immediately proceed to the next iteration.

It does not exit the loop. Instead it moves the control back to the top of the loop, where the next iteration begins.

A ```continue``` statement is normally used when the programmer wants to skip certain iterations of a loop based on a condition, but still wants the loop to keep running for the other iterations.

__Usage of the ```continue``` statement inside a loop in Bleach:__
```ts
for(let counter = 0; counter < 10; counter = counter + 1){
  if(counter == 0 or counter == 2 or counter == 4 or counter == 6 or counter == 8){
    continue;
  }
  print counter;
}
```

__The output of the code snippet above will be:__
```txt
1
3
5
7
9
```