# Bleach Grammar Versions

## Version 0.1.0 (Chapter 6)
```txt
expression → equality
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → NUMBER | STRING | "true" | "false" | "nil" | "(" expression ")"
```

## Version 0.2.0 (Chapter 8)
```txt
program → statement* EOF
statement → exprStmt | printStmt
exprStmt → expression ";"
printStmt → "print" expression ";"
expression → equality
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → NUMBER | STRING | "true" | "false" | "nil" | "(" expression ")
```

## Version 0.3.0 (Chapter 8)
```txt
program → statement* EOF
statement → exprStmt | printStmt | varDeclStmt
exprStmt → expression ";"
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
expression → equality
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.4.0 (Chapter 8)
```txt
program → statement* EOF
statement → exprStmt | printStmt | varDeclStmt
exprStmt → expression ";"
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
expression → assignment
assignment → IDENTIFIER "=" assignment | equality
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.5.0 (Chapter 8)
```txt
program → statement* EOF
statement → block | exprStmt | printStmt | varDeclStmt
block → "{" statement* "}"
exprStmt → expression ";"
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
expression → assignment
assignment → IDENTIFIER "=" assignment | equality
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.6.0 (Chapter 9)
```txt
program → statement* EOF
statement → block | exprStmt | ifStmt | printStmt | varDeclStmt
block → "{" statement* "}"
exprStmt → expression ";"
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
expression → assignment
assignment → IDENTIFIER "=" assignment | equality
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.7.0 (Chapter 9)
```txt
program → statement* EOF
statement → block | exprStmt | ifStmt | printStmt | varDeclStmt
block → "{" statement* "}"
exprStmt → expression ";"
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
expression → assignment
assignment → IDENTIFIER "=" assignment | logic_or
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.8.0 (Chapter 9)
```txt
program → statement* EOF
statement → block | exprStmt | ifStmt | printStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
exprStmt → expression ";"
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | logic_or
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.9.0 (Chapter 9)
```txt
program → statement* EOF
statement → block | doWhileStmt | exprStmt | ifStmt | printStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
doWhileStmt → "do" statement "while" "(" expression ")" ";"
exprStmt → expression ";"
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | logic_or
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.10.0 (Chapter 9)
```txt
program → statement* EOF
statement → block | doWhileStmt | exprStmt | forStmt | ifStmt | printStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
doWhileStmt → "do" statement "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" statement
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | logic_or
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.11.0 (Chapter 9)
```txt
program → statement* EOF
statement → block | doWhileStmt | exprStmt | forStmt | ifStmt | printStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
doWhileStmt → "do" statement "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" statement
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | primary
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.12.0 (Chapter 10)
```txt
program → statement* EOF
statement → block | doWhileStmt | exprStmt | forStmt | ifStmt | printStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
doWhileStmt → "do" statement "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" statement
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.13.0 (Chapter 10)
```txt
program → statement* EOF
statement → block | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
doWhileStmt → "do" statement "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" statement
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.14.0 (Chapter 10)
```txt
program → statement* EOF
statement → block | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | returnStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
doWhileStmt → "do" statement "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" statement
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
returnStmt → "return" expression? ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | IDENTIFIER
```

## Version 0.15.0 (Chapter 10)
```txt
program → statement* EOF
statement → block | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | returnStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
doWhileStmt → "do" statement "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" statement
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
returnStmt → "return" expression? ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | lambdaFunctionExpr | IDENTIFIER
lambdaFunctionExpr → "lambda" "(" parameters? ")" block
```

## Version 0.16.0 (Chapter 11)
```txt
program → statement* EOF
statement → block | breakStmt | classDeclStmt | continueStmt | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | returnStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
break → "break" ";"
classDeclStmt → "class" IDENTIFIER "{" methodDeclStmt* "}"
methodDeclStmt → "method" method
method → IDENTIFIER "(" parameters? ")" block
continueStmt → "continue" ";"
doWhileStmt → "do" statement "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" statement
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
returnStmt → "return" expression? ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" statement
expression → assignment
assignment → IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | lambdaFunctionExpr | IDENTIFIER
lambdaFunctionExpr → "lambda" "(" parameters? ")" block
```

## Version 0.17.0 (Chapter 11)
* __Now loops (```for```, ```do-while```, ```while```) must be followed by a block.__
```txt
program → statement* EOF
statement → block | breakStmt | classDeclStmt | continueStmt | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | returnStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
break → "break" ";"
classDeclStmt → "class" IDENTIFIER "{" methodDeclStmt* "}"
methodDeclStmt → "method" method
method → IDENTIFIER "(" parameters? ")" block
continueStmt → "continue" ";"
doWhileStmt → "do" block "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" block
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
returnStmt → "return" expression? ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" block
expression → assignment
assignment → IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | lambdaFunctionExpr | IDENTIFIER
lambdaFunctionExpr → "lambda" "(" parameters? ")" block
```

## Version 0.18.0 (Chapter 12)
* __Now loops (```for```, ```do-while```, ```while```) must be followed by a block.__
```txt
program → statement* EOF
statement → block | breakStmt | classDeclStmt | continueStmt | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | returnStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
break → "break" ";"
classDeclStmt → "class" IDENTIFIER "{" methodDeclStmt* "}"
methodDeclStmt → "method" method
method → IDENTIFIER "(" parameters? ")" block
continueStmt → "continue" ";"
doWhileStmt → "do" block "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" block
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
returnStmt → "return" expression? ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" block
expression → assignment
assignment → IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" | "." IDENTIFIER )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | lambdaFunctionExpr | IDENTIFIER
lambdaFunctionExpr → "lambda" "(" parameters? ")" block
```

## Version 0.19.0 (Chapter 12)
* __Now loops (```for```, ```do-while```, ```while```) must be followed by a block.__
```txt
program → statement* EOF
statement → block | breakStmt | classDeclStmt | continueStmt | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | returnStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
break → "break" ";"
classDeclStmt → "class" IDENTIFIER "{" methodDeclStmt* "}"
methodDeclStmt → "method" method
method → IDENTIFIER "(" parameters? ")" block
continueStmt → "continue" ";"
doWhileStmt → "do" block "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" block
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
returnStmt → "return" expression? ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" block
expression → assignment
assignment → ( call "." )? IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" | "." IDENTIFIER )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | lambdaFunctionExpr | IDENTIFIER
lambdaFunctionExpr → "lambda" "(" parameters? ")" block
```

## Version 0.20.0 (Chapter 13)
* __Now loops (```for```, ```do-while```, ```while```) must be followed by a block.__
```txt
program → statement* EOF
statement → block | breakStmt | classDeclStmt | continueStmt | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | returnStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
break → "break" ";"
classDeclStmt → "class" IDENTIFIER ( "inherits" IDENTIFIER )? "{" methodDeclStmt* "}"
methodDeclStmt → "method" method
method → IDENTIFIER "(" parameters? ")" block
continueStmt → "continue" ";"
doWhileStmt → "do" block "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" block
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
returnStmt → "return" expression? ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" block
expression → assignment
assignment → ( call "." )? IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" | "." IDENTIFIER )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | lambdaFunctionExpr | IDENTIFIER
lambdaFunctionExpr → "lambda" "(" parameters? ")" block
```

## Version 0.21.0 (Chapter 13)
* __Now loops (```for```, ```do-while```, ```while```) must be followed by a block.__
```txt
program → statement* EOF
statement → block | breakStmt | classDeclStmt | continueStmt | doWhileStmt | exprStmt | forStmt | funcDeclStmt | ifStmt | printStmt | returnStmt | varDeclStmt | whileStmt
block → "{" statement* "}"
break → "break" ";"
classDeclStmt → "class" IDENTIFIER ( "inherits" IDENTIFIER )? "{" methodDeclStmt* "}"
methodDeclStmt → "method" method
method → IDENTIFIER "(" parameters? ")" block
continueStmt → "continue" ";"
doWhileStmt → "do" block "while" "(" expression ")" ";"
exprStmt → expression ";"
forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" block
funcDeclStmt → "function" function
function → IDENTIFIER "(" parameters? ")" block
parameters → IDENTIFIER ( "," IDENTIFIER )*
ifStmt → "if" "(" expression ")" statement
         ( "elif" "(" expression ")" statement )*
         ( "else" statement )?
printStmt → "print" expression ";"
returnStmt → "return" expression? ";"
varDeclStmt → "let" IDENTIFIER ( "=" expression )? ";"
whileStmt → "while" "(" expression ")" block
expression → assignment
assignment → ( call "." )? IDENTIFIER "=" assignment | ternary
ternary → logic_or ( "?" expression ":" expression )*
logic_or → logic_and ( "or" logic_and )*
logic_and → equality ( "and" equality )*
equality → comparison ( ( "!=" | "==" ) comparison )*
comparison → term ( ( ">" | ">=" | "<" | "<=" ) term )*
term → factor ( ( "-" | "+" ) factor )*
factor → unary ( ( "/" | "*" ) unary )*
unary → ( "!" | "-" ) unary | call
call → primary ( "(" arguments? ")" | "." IDENTIFIER )*
arguments → expression ( "," expression )*
primary → "true" | "false" | "nil" | NUMBER | STRING | "(" expression ")" | lambdaFunctionExpr | IDENTIFIER | "super" . IDENTIFIER
lambdaFunctionExpr → "lambda" "(" parameters? ")" block
```