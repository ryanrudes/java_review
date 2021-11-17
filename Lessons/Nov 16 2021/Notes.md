# Tue Nov 16 2021

## What we covered
- [Logical operators `== != > >= < <= ! && || ?:`](logical-operators)
  - [**AND** Operator `&&`](and-operator)
  - [**OR** Operator `||`](or-operator)
  - [Operator Precedence](operator-precedence)

### Logical Operators
Here's a list of the logical operators we have covered so far:
- `==`: is equal to?
- `!=`: is not equal to?
- `>`: is greater than?
- `>=`: is greater than or equal to?
- `<`: is less than?
- `<=`: is less than or equal to?
- `!`: negation operator (**NOT**)
- `&&`: **AND** operator
- `||`: **OR** operator

#### **AND** Operator (`&&`)

The **AND** operator (`&&`) returns `true` **only if** both conditions are true.

```java
true && true // this is true
true && false // this is false
false && true // this is false
false && false // this is false
```

#### **OR** Operator (`||`)

The **OR** operator (`||`) returns `true` if *either* condition is true. Therefore, it is sufficient for just one of the conditions to be true, whereas the **AND** operator requires both to be true.

```java
true || true // this is true
true || false // this is true
false || true // this is true
false || false // this is false
```

#### Operator Precedence

Since we've covered quite a lot of operators so far (both arithemetic and conditional): here's a list summarizing the precedence operators take over eachother, ie. which ones are computed first. Recall that PEMDAS applies to arithmetic expressions in code just as it does in math. See [here](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html) for more info on how Java operator precedence works.

1. **Postfix**: `expr++` (increment) and `expr--` (decrement)
2. **Unary**: `!` (negation)
3. **Multiplicative**: `*` (multiplication), `/` (division), and `%` (modulus)
4. **Additive**: `+` (addition) and `-` (subtraction)
5. **Relational**: `<` (less than), `>` (greater than), `<=` (less than or equal to), `>=` (greater than or equal to)
6. **Equality**: `==` (equality) and `!=` (inequality)
7. **Logical AND**: `&&` (and)
8. **Logical OR**: `||` (or)
9. **Assignment**: `=` (assignment), `+=` (increase), `-=` (decrease), `*=` (multiply), `/=` (divide), `%=` (modulo)

There are still several more operators that we have yet to cover, we'll learn more soon. But the ones we have already covered are the most common ones.
