Writing an interpreter from scratch in Golang  

Resources:
*Building an Interpreter in Go* by Thorsten Bell.

<!-- TODO(Pradakicks): Add postfix operators
reference prefixParseFn implementation parser/parser.go
 -->

TODO(Pradakicks): modify structs so that it efficently uses memory and then run benchmarks and document results
<https://medium.com/@sebassegros/golang-dealing-with-maligned-structs-9b77bacf4b97>
Example:
Current:
type PrefixExpression struct {
 Token    token.Token // The prefix token, e.g !
 Operator string
 Right    Expression
}
Optimized:
type PrefixExpression struct {
 Operator string
 Right    Expression
 Token    token.Token // The prefix token, e.g !
}

