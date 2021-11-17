# Tue Nov 16 2021

## What we covered
- [Logical operators `== != > >= < <= ! && || ?:`](#logical-operators)
  - [**AND** Operator `&&`](#and-operator)
  - [**OR** Operator `||`](#or-operator)
  - [Operator Precedence](#operator-precedence)
- [Conditional Expressions and Conditional Etatements](#conditional-expressions-and-conditional-statements)
  - [If-Else Statement (`if`, `else if`, `else`)](#if-else-statement)
  - [Switch Case (`switch`, `case`, `default`)](#switch-case)

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

#### **AND** Operator

The **AND** operator (`&&`) returns `true` **only if** both conditions are true.

```java
true && true // this is true
true && false // this is false
false && true // this is false
false && false // this is false
```

#### **OR** Operator

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

### Conditional Expressions and Conditional Statements

#### If-Else Statement

**The if-then Statement (`if`)**

The if-then statement checks the given condition; if it is true, then it runs the code placed inside the `if` block. Otherwise, it simply moves on.

Remember the syntax for a simple if-then statement:

```java
if (condition) {
  // do something
}
```

If you only put one line inside the `if` block, you may omit the brackets without raising an error:

```java
if (condition)
  System.out.println("Hello, World!")
```

**The if-then-else Statement** (`if`, `else`)**

The if-then-else statement checks the given condition; if it is true, then it runs the code placed inside the `if` block. Otherwise, it runs the code placed inside the `else` block.

Remember the syntax for an if-then-else statement:

```java
if (condition) {
  // do something
} else {
  // do something else
}
```

**The if-else-if ladder Statement (`if`, `else if`, `else`)**

The if-else-if ladder statement executes one condition from multiple statements. It first checks the condition in the `if` clause. If this is true, it executed that block of code accordingly. Otherwise, it moves onto the first `else if`. If that condition is true, it runs *that* block of code. if this is followed by yet another `else if`, it repeats this process. It eventually either reaches the end of the conditions, at which point it simply moves on, or falls back to a final `else` condition, executing that block of code accordingly.

An `else` clause is **NOT** mandatory in Java, just as the `default` case is not necessary in a switch case. `else` is to the if statement as `default` is to the switch case.

Remember the syntax for an if-else-if ladder statement:

```java
if (condition) {
  // do something
} else if (other condition) {
  // do something else
} else if (yet another condition) {
  // do this thing
} else {
  // do something different
}
```

Here's what it looks like if you omit the `else` case. **Make sure** to be **very careful** when ommitting the `else` case. Know what the possible scenarios are for your if statement. Be aware that if none of your `else if` conditions are satisfied and you omit the `else` case, the entire if statement will have no effect. Only omit `else` when you are absolutely sure that there are no other possibilities you want to consider, ie. it doesn't matter if none of your `if` and `else if` blocks are run.

Here's an example of an if-else-if ladder that considers an integer variable `grade` and prints the letter corresponding to the numerical grade:

```java
if (grade >= 95) {
  System.out.println("A");
} else if (grade >= 85) {
  System.out.println("B");
} else if (grade >= 75) {
  System.out.println("C");
} else if (grade >= 65) {
  System.out.println("D");
} else {
  System.out.println("F");
}
```

#### Switch Case (`switch`, `case`, `default`)
