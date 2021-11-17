# Tue Nov 16 2021

## What we covered
- [Logical operators `== != > >= < <= ! && ||`](#logical-operators)
  - [**AND** Operator `&&`](#and-operator)
  - [**OR** Operator `||`](#or-operator)
  - [Operator Precedence](#operator-precedence)
- [Conditional Expressions and Conditional Statements](#conditional-expressions-and-conditional-statements)
  - [If-Else Statement (`if`, `else if`, `else`)](#if-else-statement)
  - [Switch Case (`switch`, `case`, `default`)](#switch-case)
- [Type Casting](#type-casting)

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

#### Switch Case

An if-then-else statement can test expressions based on conditions involving a *range of values*, for instance:

> Is `x` greater than or equal to 5? \
> If so, do this.
> Otherwise, is it greater than 3? \
> If so, do this instead. \
> Otherwise, do something else.

Whereas a switch statement tests expressions based solely on a single integer, enumerated value, or String object. It is a condenced and more readable way of implementing an if-then-else statement for situations like this:

**Context**: Let's say your have an object you created (most likely an enum), that describes the cloud cover. It can take on any of these values:
- Clear
- Partly Cloudy
- Moderately Cloudy
- Mostly Cloudy

You could you a switch statement for a situation like this. Note that we can omit the `default` case **only because** our enum can **only** take on these four values, so it would be impossible for none of these cases to be satisfied.

```java
switch (cloudCover) {
  case .clear:
    System.out.println("It is clear outside.");
    break;
  case .partlyCloudy:
    System.out.println("It is partly cloudy.");
    break;
  case .moderatelyCloudy:
    System.out.println("It is moderately cloudy.");
    break;
  case .mostlyCloudy:
    System.out.println("It is mostly cloudy.");
    break;
}
```

Switch statements are **NOT** applicable for situations involving conditional operators such as `>`, `>=`, `<`, `<=`, and the like. It is only for condensing if-then-else statements involving equalities.

The other key similarities/differences between if-else and switch are as follows:
- Switch statements use colons (`:`) to separate cases, whereas if-else uses curly braces (`{}`)
- Switch statements have an optional `break` keyword. But **be careful**, as omitting the `break` keyword will cause execution to continue on into the next case, **even if it already found a prior case to be true and executed code accordingly**. By ommitting the `break` keyword, the switch case can potentially execute multiple cases. You will typically want the `break` keyword to end each `case`, except `default`, for which it doesn't matter since this is always the last case. We will revisit the `break` keyword when we get into loops.
- If-else has the `else` keyword, while switch case has the `default` keyword. These are both optional, and they are for executing code when none of the prior conditions were satisfied. You must be careful if you choose to omit them from if-else or switch statements.

### Type Casting

Recall how we have many different primitive types in java for storing various-sized quantities with different amounts of precision. Each primitive type has its own numerical limits, and a precision limit.

In order of least to greatest capacity & precision, the primitives are as follows (even though `float` takes up half the space of `int`, it is considered a wider primitive because it is a floating-point type, ie. it can store digits after the decimal):

```java
// byte - stores 1 byte (8 bits) and doesn't store any digits after the decimal
// char - stores 2 bytes (16 bits) and doesn't store any digits after the decimal
// short - stores 2 bytes (16 bits) and doesn't store any digits after the decimal
// int - stores 4 bytes (32 bits) and doesn't store any digits after the decimal
// long - stores 8 bytes (64 bits) and doesn't store any digits after the decimal
// float - stores 4 bytes (32 bits) and truncates at 7 digits after the decimal
// double - stores 8 bytes (64 bits0 and truncates at 15 digits after the decimal.
```

Since each primitive type varies in its capacity & precision, we need to be careful when working with variables of different types to avoid these two kinds of logical errors:
- Numerical Overflow: occurs when the value of a variable exceeds the bounds permitted by its type, causing the value to cycle back around to the opposite sign. For instance, if an integer variable exceeds the maximum value `int` can store, it changes to the minimum value, ie. some large negative number.
- Rounding Errors: Since the number of bits we can use to represent a decimal value is always finite, we have to set some limits upon the precision. `float` can store 7 digits after the decimal, while `double` can store 15. For this reason, is would be a bad assumption to assume the behavior of these primitive types is identical to how you might treat, say, rational numbers in mathematics. For instance, consider this:
```java
float x = 1f;
float y = 3f;
System.out.println((x / y) * y); // Prints "0.9999999"
```

There are two types of type casting, **widening casting**, which is done **automatically** by Java, and **narrowing casting**, which must be done manually. Widening casting occurs when a type is casted onto a type with greater precision (refer back to the order of precision for the primitive types). Narrowing casting is when the opposite occurs, a value with a more precise type is manually casted onto a less precise type.

Here's an example of automatic widening casting:
```java
public class Main {
  public static void main(String[] args) {
    int myInt = 9;
    double myDouble = myInt;        // Automatic casting: int to double

    System.out.println(myInt);      // Outputs 9
    System.out.println(myDouble);   // Outputs 9.0
  }
}
```

And here's an example of manual narrowing casting:
```java
public class Main {
  public static void main(String[] args) {
    double myDouble = 9.78d;
    int myInt = (int) myDouble;     // Manual casting: double to int

    System.out.println(myDouble);   // Outputs 9.78
    System.out.println(myInt);      // Outputs 9
  }
}
```
