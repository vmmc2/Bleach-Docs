# Operators

## Overview
As you also already know, operators in a programming language are symbols that are responsible for executing an operation on one or more operands (values or variables) in order to produce a result.

Operators are fundamental building blocks in a programming language, allowing the programmer to manipulate data, perform calculations, compare values, and much more.

In this page, we'll see what operators Bleach provides to us and how each of them behave and, at the end, we'll also see what is the precedence of each of these operators.

## Unary Operators
An unary operator is, as its name suggests, an operator that expects just one operand. Bleach has two operators that fall in this category.

### Arithmetical
__Negation (```-```):__ Negates the value of an operand of type ```num```.
```ts
let number = 5;
print -number // -5;
```

### Logical
__Not (```!```):__ Inverts the value of an operand of type ```bool```.
```ts
let b = true;
print !b; // false
print !!b; // true
```


## Binary Operators
A binary operator is, as its name suggests, an operator that expects just two operands. Bleach has 12 operators that fall in this category.

### Arithmetical
__Addition (```+```):__ This operator expects two operands. However it behaves differently depending on the types of the two received operands.
* Left operand (```num```) and Right operand (```num```): Adds the second (right) operand operands to the first (left) operand.
```ts
print 2 + 3; // 5
print 2.71 + 3.14159; // 5.85159
```

* Left operand (```str```) and Right operand (```str```): Concatenates the second (right) operand to the first (left) operand.
```ts
print "hello," + " there!"; // "hello, there!"
print "a" + "b"; // "ab"
```

* Left operand (```num```) and Right operand (```str```): Converts the first (left) operand from the ```num``` type to the ```str``` type. Then, concatenates the second (right) operand to the first (left) operand, producing a new value of type ```str```.
```ts
print 2 + "two"; // "2two"
```

* Left operand (```str```) and Right operand (```num```): Converts the second (right) operand from the type ```num``` to the type ```str```. Then, concatenates the second (right) operand to the first (left) operand, producing a new value of type ```str```.
```ts
print "two" + 2; // "two2"
```

__Subtraction (```-```):__ This operator expects two operands of type ```num```. It subtracts the second (right) operand from the first (left) operand.
```ts
print 5 - 3; // 2
```

__Multiplication (```*```):__ This operator expects two operands of type ```num```. It multiplies the first (left) operand by the second (right) operand.
```ts
print 1.5 * 4; // 6
```

__Division (```/```):__ This operator expects two operands of type ```num```. It divides the first (left) operand by the second (right) operand.
```ts
print 5 / 2; // 2
print 1 / 3; // 0.333333333333333
```

### Comparison/Relational
__Greater Than (```>```):__ This operator expects two operands of type ```num```. It checks whether or not the first (left) operand is greater than the second (right) operand.
```ts
print 5 > 2; // true
print 1 > 3; // false
```

__Greater Than or Equal (```>=```):__ This operator expects two operands of type ```num```. It checks whether or not the first (left) operand is greater than or equal to the second (right) operand.
```ts
print 5 >= 2; // true
print -1 >= -1 // true
print 1 >= 3; // false
```

__Lesser Than (```<```):__ This operator expects two operands of type ```num```. It checks whether or not the first (left) operand is lesser than the second (right) operand.
```ts
print 5 < 2; // false
print 1 < 3; // true
```

__Lesser Than or Equal (```<=```):__ This operator expects two operands of type ```num```. It checks whether or not the first (left) operand is lesser than or equal to the second (right) operand.
```ts
print 5 <= 2; // false
print 0 <= 0; // true
print 1 <= 3; // true
```


### Equality
__Equal (```==```):__ This operator expects two operands of the following built-in types (```bool```, ```nil```, ```num```, ```str```). It checks whether the values are of the same type and, if that's the case, checks whether such values are the same.
```ts
print 2 == 2; // true
print 2 == (1 + 1) // true
print 2 == 3; // false
print "hello" == "hello"; // true
print "hello" == "hell"; // false
print 2 == nil; // false
print nil == nil; // true
print true == true; // true
print true == false; // false
print true == !!true; // true
```

__Not Equal (```!=```):__ This operator expects two operands of the following built-in types (```bool```, ```nil```, ```num```, ```str```). It checks whether the values are of the same type (if they are not of the same type, such comparison returns ```false```) and, if they are of the same type, it then checks whether such values are not the same.
```ts
print 2 != 2; // false
print 2 != (1 + 1) // false
print 2 != 3; // true
print "hello" != "hello"; // false
print "hello" != "hell"; // true
print 2 != nil; // true
print nil != nil; // false
print true != true; // false
print true != false; // true
print true != !!true; // false
```


### Logical
__And (```and```):__ This operator returns ```true``` if both of its operands are truthy values. Otherwise, it returns ```false```. Remember that this operator performs short-circuiting when possible.
```ts
print 5 and 2; // true
print 5 and false; // false
print false and nil; // false
```

__Or (```or```):__ This operator returns ```true``` if one of its operands are truthy values. Otherwise, it returns ```false```. Remember that this operator performs short-circuiting when possible.
```ts
print 5 or 2; // true
print 5 or false; // true
print false or nil; // false
```

## Ternary Operator
An unary operator is, as its name suggests, an operator that expects just three operands. Bleach has just one operator that fall in this category.

__Ternary (```? :```):__  This operator is essentialy a concise way to perform conditional operations in a programming language. It is used to evaluate a condition and return one of two values based on whether the condition is true or false. As previously seen, the ternary operator is called "ternary" because it operates on three operands.
```ts
print 2 == 2 ? "2 is equal to 2" : "2 is not equal to two"; // "2 is equal to 2"
```


## Operator Precedence
Below, there is a scheme that shows us the precedence of all of the presented operators when a expression in being evaluated in a Bleach program at runtime.

In the list shown below, the smaller the index is, the higher the precedence of such operator is. Operators present in the same index have the same precedence and will be evaluated from left-to-right as they appear in an expression.

| Precendence       | Operator                             |
|-------------------|--------------------------------------|
| 1                 | ```!```, ```-``` (unary)             |
| 2                 | ```*```, ```/```                     |
| 3                 | ```+```, ```-``` (binary)            |
| 4                 | ```>```, ```>=```, ```<```, ```<=``` |
| 5                 | ```==```, ```!=```                   |
| 6                 | ```and```                            |
| 7                 | ```or```                             |
| 8                 | ```? : ``` (ternary)                 |
| 9                 | ```=``` (assignment)                 |
