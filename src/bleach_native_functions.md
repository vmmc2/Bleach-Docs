# Bleach Language Native Functions

## Overview
__In case the reader is not familiar with this concept: Native functions (a.k.a built-in functions or intrinsic functions) are functions that are directly provided by the programming language or its runtime environment, typically written in a lower-level language (C++ in Bleach's case) and are part of the core language or runtime.__

__These functions are "native" because they are implemented at the system or runtime level rather than being written in the higher-level language itself (i.e., written in Bleach).__

## Some Key Characteristics of Native Functions
* __Performance:__ Native functions are usually optimized for performance since they are closely integrated with the language runtime (which was written in C++ in Bleach's case) or the underlying hardware.
* __Availability:__ Native Functions are readily available without needing to be explicitly imported or defined by the programmer.
* __Language-Specific:__ Native functions varies between languages and is closely tied to the language's runtime environment.

## Namespaces
__For clarity and organization purposes, Bleach's native functions are organized in namespaces.__

__If you are not familiar with this concept, a namespace is a way to logically group functions, variables and other identifiers to prevent naming conflicts and to organize code more effectively (in Bleach's case I opted to use namespaces just to group native functions as I've mentioned above).__

__By using namespaces, you can create multiple functions or variables with the same name, as long as they belong to different namespaces, thereby avoiding potential collisions in a large codebase.__

### Namespace: ```std::io```
__Contains the native functions related to input/output operations.__

#### Function: ```std::io::readLine```
This native function is responsible for reading the content provided by the user inside the console/terminal until it reaches the end of line character (```\n```). It takes 0 arguments and its return value is a value of ```str``` type: The content provided by the user in the console/terminal.

Usage:
```ts
let user_input = std::io::readLine(); // Say the user writes "hello" in console/terminal.

// At this point, the value of the user_input variable is "hello";
```

#### Function: ```std::io::print```
This native function is responsible for printing content provided by the user to console/terminal. It can take any number arguments of any type, whether it's built-in or user-defined. Then it prints the string representation of such values to the console separating them by a ``` ``` character.

Usage:
```ts
let n = 3.14;
let name = "Ryan";
let nothing = nil;
let is_earth_flat = false;

std::io::print(n, name, nothing, is_earth_flat); // 3.14 Ryan nil false
```

#### Function ```std::io::fileRead```
Not implemented yet.

#### Function ```std::io::fileWrite```
Not implemented yet.


### Namespace: ```std::chrono```
__Contains native functions related to time and clock operations.__

#### Function: ```std::chrono::clock```
This native function is responsible for calculating the amount of seconds that have been passed since "January 1, 1970, 00:00:00 UTC", which is a value of type ```num```. It takes 0 arguments. Its return value is, as said above, the amount of seconds that have been passed since the date provided above, a value of type ```num```.

This native function is, as you might have already thought, very useful for benchmarking purposes.

Usage:
```ts
let begin = std::chrono::clock();
// Execution of some code that the user wants to evaluate the performance/speed.
let end = std::chrono::clock();

let duration_in_seconds = end - begin;

std::io::print("The observed task took", duration_in_seconds, "seconds to be executed.");
```


### Namespace: ```std::math```
__Contains native functions related to mathematical operations.__

#### Function: ```std::math::abs```
This native function is responsible for calculating the absolute value of a provided value of type ```num```. It can takes just one argument of such type. Its return value is the absolute value of the provided value of type ```num```.

Usage:
```ts
let n = -10;
let absolute_number = std::math::abs(n); // 10
```

#### Function: ```std::math::ceil```
Not implemented yet.

#### Function: ```std::math::floor```
Not implemented yet.

#### Function: ```std::math::log```
This native function is responsible for calculating the logarithm of a value given the base to be used. It takes two arguments of type ```num```. The first argument is base the and the second argument is the mantissa. Its return value is the computed logarithm, a value of type ```num```, given the provided arguments.

__Important: The first argument (the base of the logarithm) must not be equal to ```1```. Also, the second argument (the argument) must be a number greater than ```0```. If either of these conditions is not met, then such native function will throw a runtime error when called.__

Usage:
```ts
let base = 2;
let mantissa = 8;
let logarithm = std::math::log(base, mantissa); // 3
```

#### Function: ```std::math::pow```
This native function is responsible for calculating the power of a value given its exponent. It takes two arguments of type ```num```. The first argument is base the and the second argument is the exponent. Its return value is the value resulted from the computation of the exponentiation operation, a value of type ```num```, given the provided arguments.

Usage:
```ts
let base = 2;
let exponent = 3;
let exponentiation_result = std::math::pow(base, exponent); // 8
```

#### Function: ```std::math::setprecision```
Not implemented yet.

#### Function: ```std::math::sqrt```
This native function is responsible for calculating the square root of a given value (the radicand). It takes just one argument of type ```num```. Its return value is the square root of the provided radicand, a value of type ```num```, given the provided argument.

__Important: This native function is not able to deal with negative values. If the user provide such a value, a runtime error will be thrown.__

Usage:
```ts
let n = 2;
let square_root_of_two = std::math::sqrt(n); // 1.414213562373095
```


### Namespace: ```std::random```
__Contains native functions related to random number generation.__

#### Function: ```std::random::random```
This native function is responsible for generating a random number that is between an interval. It takes two arguments of type ```num```. The first argument is the left boundary of the interval and the second argument is the right boundary of the interval. Its return value is the generated random number, a value of type ```num```, given the provided arguments.

__Important: If the first argument is greater than the second argument the native function will perform a swap between such arguments internally when called.__

Usage:
```ts
let left = 3.5;
let right = 3.7;
std::io::print(std::random::random(left, right));
```
