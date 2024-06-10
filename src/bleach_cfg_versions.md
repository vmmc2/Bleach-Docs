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