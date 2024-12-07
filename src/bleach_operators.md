# Operators

## Overview
As you also already know, operators in a programming language are symbols that are responsible for executing an operation on one or more operands (values or variables) in order to produce a result.

Operators are fundamental building blocks in a programming language, allowing the programmer to manipulate data, perform calculations, compare values, and much more.

In this page, the operators provided by Bleach are going to be presented to us. Also, there will be explanations about how each of them behave in different scenarios and, at the end, the precedence table of Bleach's is presented for consulting purposes.

## Unary Operators
These operators expects just 1 operand. Bleach has 2 operators that fall in this class.

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
These operators expects just 2 operands. Bleach has 13 operators that fall in this class.

### Arithmetical
#### __Addition (```+```):__ This operator expects 2 operands. However it behaves differently depending on the types of the two received operands.
__Left operand (```num```) and Right operand (```num```):__ Adds the second (right) operand to the first (left) operand, producing a new value of type ```num```.
```ts
print 2 + 3; // 5
print 2.71 + 3.14159; // 5.85159
```

__Left operand (```str```) and Right operand (```str```):__ Concatenates the second (right) operand to the first (left) operand, producing a new value of type ```str```.
```ts
print "hello," + " there!"; // "hello, there!"
print "a" + "b"; // "ab"
```

__Left operand (```num```) and Right operand (```str```):__ Converts the first (left) operand from the ```num``` type to the ```str``` type. Then, concatenates the second (right) operand to the first (left) operand, producing a new value of type ```str```.
```ts
print 2 + "two"; // "2two"
```

__Left operand (```str```) and Right operand (```num```):__ Converts the second (right) operand from the type ```num``` to the type ```str```. Then, concatenates the second (right) operand to the first (left) operand, producing a new value of type ```str```.
```ts
print "two" + 2; // "two2"
```

__Left operand (```list```) and Right operand (```list```):__ Concatenates the second (right) operand to the first (left) operand, producing a new value of type ```list```.
```ts
print [1, 2, 3] + [4, 5, 6] // [1, 2, 3, 4, 5, 6]
```

__Left operand (```str```) and Right operand (```BleachInstance```):__ Calls the ```"str"``` method of the second (right) operand, which is an instance of an user-defined type (this is a default method that returns the string representation of an instance of an user-defined type). Then, concatenates the second (right) operand to the first (left) operand, producing a new value of type ```str```.

__Left operand (```BleachInstance```) and Right operand (```str```):__ Concatenates the second (right) operand to the string representation of the first (left) operand, which is an instance of an user-defined type. This happens because the ```"str"``` method of the first (left) operand is called, which also returns a value of type ```str```. This produces a new value of type ```str```.


#### __Subtraction (```-```):__ This operator expects 2 operands of type ```num```. It subtracts the second (right) operand from the first (left) operand.
```ts
print 5 - 3; // 2
```

#### __Multiplication (```*```):__ This operator expects 2 operands of type ```num```. It multiplies the first (left) operand by the second (right) operand.
```ts
print 1.5 * 4; // 6
```

#### __Division (```/```):__ This operator expects 2 operands of type ```num```. It divides the first (left) operand by the second (right) operand.
```ts
print 5 / 2; // 2
print 1 / 3; // 0.333333333333333
```

#### __Remainder(```%```):__ This operator expects 2 operands of type ```num```. It divides the first (left) operand, also called dividend, by the second (right) operand, also called divisor, and returns the remainder of this division (a value of type ```num```). It is worth mentioning that if the value of the divisor is 0, then a runtime error will be thrown.
```ts
print 5 % 2; // 1
print 1 % 3; // 1
print -10 % 4; // -2
```


### Comparison/Relational
#### __Greater Than (```>```):__ This operator expects 2 operands of type ```num``` or 2 operands of type ```str```. It checks whether or not the first (left) operand is greater than the second (right) operand.
```ts
print 5 > 2; // true
print 1 > 3; // false
```
```ts
print "z" > "a"; // true
print "a" > "z"; // false
```

#### __Greater Than or Equal (```>=```):__ This operator expects two operands of type ```num``` or 2 operands of type ```str```. It checks whether or not the first (left) operand is greater than or equal to the second (right) operand.
```ts
print 5 >= 2; // true
print -1 >= -1 // true
print 1 >= 3; // false
```
```ts
print "aa" >= "aa"; // true
print "za" >= "zz"; // false
```

#### __Lesser Than (```<```):__ This operator expects two operands of type ```num``` or 2 operands of type ```str```. It checks whether or not the first (left) operand is lesser than the second (right) operand.
```ts
print 5 < 2; // false
print 1 < 3; // true
```
```ts
print "a" < "z"; // true
print "z" < "a"; // false
```

#### __Lesser Than or Equal (```<=```):__ This operator expects two operands of type ```num``` or 2 operands of type ```str```. It checks whether or not the first (left) operand is lesser than or equal to the second (right) operand.
```ts
print 5 <= 2; // false
print 0 <= 0; // true
print 1 <= 3; // true
```
```ts
print "z" <= "z"; // true
print "zz" <= "az"; // false
```


### Equality
#### __Equal (```==```):__ This operator expects two operands of the following built-in types (```bool```, ```nil```, ```num```, ```str```). It checks whether the values are of the same type and, if that's the case, checks whether such values are the same. Returns ```true``` if both conditions are true. Otherwise, returns ```false```.
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

#### __Not Equal (```!=```):__ This operator expects two operands of the following built-in types (```bool```, ```nil```, ```num```, ```str```). It checks whether the values are of the same type (if they are not of the same type, such comparison returns ```false```) and, if they are of the same type, it then checks whether such values are not the same. Returns ```true``` if one (or both) conditions mentioned above are not satisfied. Otherwise, returns ```false```.
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
#### __And (```and```):__ This operator returns ```true``` if both of its operands are truthy values. Otherwise, it returns ```false```. Remember that this operator performs short-circuiting when possible.
```ts
print 5 and 2; // true
print 5 and false; // false
print false and nil; // false
```

#### __Or (```or```):__ This operator returns ```true``` if one of its operands are truthy values. Otherwise, it returns ```false```. Remember that this operator performs short-circuiting when possible.
```ts
print 5 or 2; // true
print 5 or false; // true
print false or nil; // false
```

### Ternary Operator
#### __Ternary (```condition ? expression_1 : expression_2```):__  A ternary operator is, as its name suggests, an operator that expects 3 operands. The reader might be familiar with this operator since it is widely used in both C and C++. This operator provides another way of executing conditional operations. It is used to evaluate a condition and return one of two values based on whether the condition evaluates to ```true``` or ```false```. The three operands expected by the ternary operator can be of any type (built-in or user-defined). The first one is evaluated by the ternary operator with respect to its truthiness of falseness. If the value is "truthy", then the operator returns the second operand. Otherwise, it returns the third operand. The example below shows how to properly use such operator.
```ts
print 2 == 2 ? "2 is equal to 2" : "2 is not equal to two"; // "2 is equal to 2"
```


## Operator Precedence
Below, there is a scheme that shows us the precedence of all of the presented operators when a expression in being evaluated in a Bleach program at runtime.

In the list shown below, the smaller the index is, the higher the precedence of such operator is. Operators present in the same index have the same precedence and will be evaluated from left-to-right as they appear in an expression.

| Precendence       | Operator                                    |
|-------------------|---------------------------------------------|
| 1                 | ```!```, ```-``` (unary)                    |
| 2                 | ```*```, ```/```, ```%```                   |
| 3                 | ```+```, ```-``` (binary)                   |
| 4                 | ```>```, ```>=```, ```<```, ```<=```        |
| 5                 | ```==```, ```!=```                          |
| 6                 | ```and```                                   |
| 7                 | ```or```                                    |
| 8                 | ```condition ? expr_1 : expr_2``` (ternary) |
| 9                 | ```=``` (assignment)                        |
