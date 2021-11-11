# Thu Nov 11 2021

## What we covered
- [Getting started](#getting-started)
- [Printing to the console](#printing-to-the-console)
- [Naming variables, methods, and classes](#naming-variables-methods-and-classes)
- [Primitives](#primitives)
- Declaration
- Initialization
- Assignment
- Strings & String methods
- Arithmetic operators

### Getting started

Java class files look something like this:

```java
public class Main {
    public static void main(String[] args) {
      ...
    }
}
```

The name of the class **MUST** be the same as the filename, ie. `Main.java` defines the class `Main`.

### Printing to the console

`System.out.print` prints the string to the console, without creating a new line. `System.out.println` prints the string to the console, and makes a new line. Examples:

```java
System.out.print("Hello, world!");
>>> Hello, world!
```

```java
System.out.print("Hello, ");
System.out.print("world!");
>>> Hello, world!
```

```java
System.out.println("Hello, world!");
>>> Hello, world!
>>> 
```

```java
System.out.println("Hello, ");
System.out.println("world!");
>>> Hello, 
>>> world!
```

### Naming variables, methods, and classes

See [here](https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html) for a similar overview to what is written below.

In Java, it is conventional to use **camelcase** syntax, ie. `myFunction`.

#### Naming variables

**VALID**
  - A variable name can contain letters, digits, and underscores.
  - A variable name can **begin** with a letter, underscore, or dollar sign, ie. `bool $isOn = false; bool _isOff = true;`

**INVALID**
  - A variable name cannot contain the dollar sign character, ie. `int numberOf$InWallet;`
  - A variable name cannot contain the underscore character, ie. `String my_name;`
  - A variable name cannot begin with a digit, ie. `float 2pi = 6.28f;`
  - A variable name cannot contain white space, ie. `int hello there;`
  - Keywords are not valid variable names, ie. `bool true;`

To be clear, variables can **BEGIN** with `_` or `$`, but **CANNOT** contain these characters anywhere else.

#### Naming methods

Method names also use camelcase by convention, and are virtually exactly the same as naming variables.
Methods should be verbs, in mixed case with the first letter lowercase, with the first letter of each internal word capitalized.

```java
run();
runFast();
getBackground();
```

#### Naming classes

The only difference in naming classes is that they should have the first letter capitalized, and they should be nouns (this part is just conventional).

```java
class Raster;
class ImageSprite;
```

### Primitives

There are several primitive types in Java. You must know their purpose (ie. when to use each) and their limits (to prevent numerical overflow, you don't need to know the bounds exactly, just a rough understanding). Here's an overview of all the primitive types. Note that `String` is **NOT** a primitive in Java, but rather a class.

**For storing integer values, we have `byte`, `short`, `int`, and `long`, storing 8, 16, 32, and 64 bits, respectively.**

- byte: 8-bit signed integer, minimum value -128, maximum value 127
```java
byte redColorComponent = 90; // This is fine
byte studentsInGrade = 240; // OVERFLOW ERROR! Too big. Should use short instead.
```
- short: 16-bit signed integer, minimum value -32,768, maximum value 32,767
```java
short minutesPerYear = 525600; // OVERFLOW ERROR! Should be using int instead
short townPopulation = 22_642; // Just right
```
- int: 32-bit signed integer, minimum value -2,147,483,648 (-1 * 2^32), maximum value 2,147,483,647 (2^32)
```java
int counter = 1; // Ok
int tooBig = 2 ** 33; // Overflow, uh oh!
```
- long: 64-bit signed integer, minimum value -9,223,372,036,854,775,808 (-1 * 2^63), maximum value 9,223,372,036,854,775,807 (2^63)
```java
long worldPopulation = 8_700_000_000; // Good time to use a long. Remember underscores can be used for readability.
long peopleInMyHouse = 4; // Shouldn't be using long, since this will surely not exceed 2^32. Should use int instead.
```

**For storing decimal values, we have `float` and `double`, storing 32 and 64 bits respectively. `float` truncates to 7 digits after the decimal; `double` allows more precision, up to 16.**

- float: 32-bit IEEE 754 floating point number, minimum value -3.4028235 x 10^38, maximum value 3.4028235 x 10^38
```java
float pi = 3.1415926535f; // float only stores 7 decimal digits, so this number will surely be truncated
float twoPi = 6.28; // SYNTAX ERROR! Forgot that to initialize a float, you must have the number end in an f.
float averageChildrenPerHousehold = 2.2f; // This is good
```
- double: 64-bit IEEE 754 floating point number, minimum value -1.7976931348623157 x 10^308, maximum value 1.7976931348623157 x 10^308
```java
double percentCompleted = 50.0; // Should NOT use double; since value will only be between 0 and 100, you might as well use float.
double e = 2.71828182845904523; // Good. Taking advantage of that extra precision.
```

**For storing characters, we have `char`.**
- char: 16-bit Unicode character
