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

# Version 0.4.0 (Chapter 8)
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