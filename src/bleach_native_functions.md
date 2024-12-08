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
This native function is responsible for printing content provided by the user to console/terminal. It can take any number arguments of any type, whether it is built-in or user-defined. Then it prints the string representation of such values to the console separating them by a ``` ``` character.

Usage:
```ts
let n = 3.14;
let name = "Ryan";
let nothing = nil;
let is_earth_flat = false;

std::io::print(n, name, nothing, is_earth_flat); // 3.14 Ryan nil false
```

#### Function ```std::io::fileRead```
This native function is responsible for or receiving a value of the type ```str``` that represents the path (absolute or relative) to a ```.txt``` file, reading its contents and returning them as a ```str``` value. It takes a vlaue of type ```str``` as its unique argument and returns a value of type ```str```, the content of the ```.txt``` file.

Usage:
```ts
let filePath = "path/to/the/desired/txt/file"; // Can be absolute or relative path to the desired ".txt" file.
let fileContent = std::io::fileRead(filePath);

print fileContent; // Prints the content of the ".txt" file.
```

#### Function ```std::io::fileWrite```
This native function is responsible for receiving a value of the type ```str``` representing a path (absolute or relative) to a ```.txt``` file, a value of the type ```str``` representing the opening mode of the file to be read (which can be ```"a"``` for append or ```"w"``` for write), another value of the type ```str``` representing the content to be written to the file and a value of the type ```bool``` signaling whether or not a newline (```\n```) must be inserted at the end of such content in the file. This function returns a ```nil``` value.

Usage #1:
```ts
let filePath = "path/to/the/desired/txt/file"; // Can be absolute or relative path to the desired ".txt" file.
let openingMode = "w"; // Write Mode.
let contentToWrite = "Hello, World!";
let insertNewlineAtTheEnd = true;

std::io::fileWrite(filePath, openingMode, contentToWrite, insertNewlineAtTheEnd);
```

Usage #2:
```ts
let filePath = "path/to/the/desired/txt/file"; // Can be absolute or relative path to the desired ".txt" file.
let openingMode = "a"; // Append Mode.
let contentToWrite = "A new line below the 'Hello, World!' line.";
let insertNewlineAtTheEnd = true;

std::io::fileWrite(filePath, openingMode, contentToWrite, insertNewlineAtTheEnd);
```

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
This native function is responsible for receiving a value of type ```num``` and returning the smallest integer number that is bigger than the provided value. This function returns a value of type ```num```.

Usage:
```ts
let n = 10.23;
let ceil_n = std::math::ceil(n); // 11
```

#### Function: ```std::math::floor```
This native function is responsible for receiving a value of type ```num``` and returning the largest integer that is smaller than the provided value. This function returns a value of type ```num```.

Usage:
```ts
let n = 1.21;
let floor_n = std::math::floor(n); // 1
```

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


### Namespace: ```std::utils```
__Contains native functions related to utility functions that might be useful to the programmer in specific scenarios.__

#### Function: ```std::utils::ord```
This native function is responsible for receiving a value of type ```str``` of length 1 and returning its respective ASCII integer number, which is a value of type ```num```. Passing a value of type ```str``` with length different than 1 will result in a runtime error.

Usage:
```ts
let A_ascIICode = std::utils::ord("A");
print A_ascIICode; // 65

let a_ascIICode = std::utils::ord("a");
print a_ascIICode; // 97
```

#### Function: ```std::utils::strToBool```
This native function is responsible for receiving a value of type ```str``` that represents a boolean as its unique argument. The function converts the value of type ```str``` into its respective value of type ```bool``` and, then, returns such value. If the value of the type ```str``` does not represent a boolean, a runtime error is thrown.

Usage:
```ts
let t_as_string = "true";
print t_as_string; // "true"

let t_as_boolean = std::utils::strToBool(t_as_string);
print t_as_boolean; // true
```

#### Function: ```std::utils::strToNil```
This native function is responsible for receiving a value of type ```str``` that represents the ```nil``` value as its unique argument. The function converts the value of the type ````str``` into this value and, then, returns it. If the value of the type ```str``` does not represent ```nil```, a runtime error is thrown.

Usage:
```ts
let nil_as_string = "nil";
print nil_as_string; // "nil"

let nil_value = std::utils::strToNil(nil_as_string);
print nil_value; // nil
```

#### Function: ```std::utils::strToNum```
This native function is responsible for receiving a value of type ```str``` that represents a number as its unique argument. The function converts the value of type ```str``` into its respective value of type ```num``` and, then, returns such value. If the value of the type ```str``` does not represent a number, a runtime error is thrown.

Usage:
```ts
let num_as_string = "3.14159";
print num_as_string; // "3.14159"

let num_as_string = std::utils::strToNum(nil_as_string);
print num_as_string; // 3.14159
```
