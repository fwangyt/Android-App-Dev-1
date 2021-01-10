## JAVA Basics I

Introduction to Java by Oracle: [Oracle Java.](https://www.oracle.com/java/)



### 1. Overview

* Java statements must end with a semicolon.
* Indentation of 4 spaces.
* The main method is the starting point to start execution of a Java program.

```java
class JavaBasics {

    public static void main(String[] args) {
        
        System.out.println("JAVA Basics I");

        // single line comment
        // System.out.println("Comment me!");

        // Multi-line comments
        /*
        System.out.println("Comment Us!");
        System.out.println("Comment Us!");
        System.out.println("Comment Us!");
        */
    }
}
```



For JAVA code style, refer to  [Google Java Style Guide.](https://google.github.io/styleguide/javaguide.html)



### 2. Variables and Data Types

Variables are containers for storing data values.

To create a variable, you must specify the type (and assign it a value).

```java
type variable = value; // assign a value
type variable; // defulat value
```



The Java programming language is **statically-typed**, which means that all variables must first be declared before they can be used. 

**Primitive types** are the most basic data types available within the Java language.

| Data Type | Default Value | **Description**                                 |
| --------- | ------------- | ----------------------------------------------- |
| byte      | 0             | 8-bit signed two's complement integer           |
| short     | 0             | 16-bit signed two's complement integer          |
| int       | 0             | 32-bit signed two's complement integer          |
| long      | 0L            | 64-bit two's complement integer                 |
| float     | 0.0f          | single-precision 32-bit IEEE 754 floating point |
| double    | 0.0d          | double-precision 64-bit IEEE 754 floating point |
| char      | '\u0000'      | two possible values: true and false             |
| boolean   | false         | single 16-bit Unicode character                 |



``` java
short shortNumber = 546;
int intNumber = 12;
long longNumber = 234;
float floatNumber = 1.231f;
double doubleNumber = 35.2d;
boolean isTrue = false;
char charA = 'A';
```



### 3. Operators

#### 3.1 Arithmetic Operators

Arithmetic operators are used to perform common mathematical operations.

| Operator | Name           | Description                            | Example |
| :------- | :------------- | :------------------------------------- | :------ |
| +        | Addition       | Adds together two values               | x + y   |
| -        | Subtraction    | Subtracts one value from another       | x - y   |
| *        | Multiplication | Multiplies two values                  | x * y   |
| /        | Division       | Divides one value by another           | x / y   |
| %        | Modulus        | Returns the division remainder         | x % y   |
| ++       | Increment      | Increases the value of a variable by 1 | ++x     |
| --       | Decrement      | Decreases the value of a variable by 1 | --x     |



#### 3.2 Assignment Operators

Assignment operators are used to assign values to variables.

| Operator | Example | Same As    |
| :------- | :------ | :--------- |
| =        | x = 5   | x = 5      |
| +=       | x += 3  | x = x + 3  |
| -=       | x -= 3  | x = x - 3  |
| *=       | x *= 3  | x = x * 3  |
| /=       | x /= 3  | x = x / 3  |
| %=       | x %= 3  | x = x % 3  |
| &=       | x &= 3  | x = x & 3  |
| \|=      | x \|= 3 | x = x \| 3 |
| ^=       | x ^= 3  | x = x ^ 3  |
| >>=      | x >>= 3 | x = x >> 3 |
| <<=      | x <<= 3 | x = x << 3 |



#### 3.3 Comparison Operators

Comparison operators are used to compare two values.

| Operator | Name                     | Example |
| :------- | :----------------------- | :------ |
| ==       | Equal to                 | x == y  |
| !=       | Not equal                | x != y  |
| >        | Greater than             | x > y   |
| <        | Less than                | x < y   |
| >=       | Greater than or equal to | x >= y  |
| <=       | Less than or equal to    | x <= y  |



#### 3.4 Logical Operators

Logical operators are used to determine the logic between variables or values.

| Operator | Name        | Description                                             | Example            |
| :------- | :---------- | :------------------------------------------------------ | :----------------- |
| &&       | Logical and | Returns true if both statements are true                | x < 5 && x < 10    |
| \|\|     | Logical or  | Returns true if one of the statements is true           | x < 5 \|\| x < 4   |
| !        | Logical not | Reverse the result, returns false if the result is true | !(x < 5 && x < 10) |



#### 3.5 Bitwise Operators

Bitwise operators are used to perform binary logic with the bits of an integer or long integer.

| Operator | Description                                                  | Example | Same as      | Result | Decimal |
| :------- | :----------------------------------------------------------- | :------ | :----------- | :----- | :------ |
| &        | AND - Sets each bit to 1 if both bits are 1                  | 5 & 1   | 0101 & 0001  | 0001   | 1       |
| \|       | OR - Sets each bit to 1 if any of the two bits is 1          | 5 \| 1  | 0101 \| 0001 | 0101   | 5       |
| ~        | NOT - Inverts all the bits                                   | ~ 5     | ~0101        | 1010   | 10      |
| ^        | XOR - Sets each bit to 1 if only one of the two bits is 1    | 5 ^ 1   | 0101 ^ 0001  | 0100   | 4       |
| <<       | Zero-fill left shift - Shift left by pushing zeroes in from the right and letting the leftmost bits fall off | 9 << 1  | 1001 << 1    | 0010   | 2       |
| >>       | Signed right shift - Shift right by pushing copies of the leftmost bit in from the left and letting the rightmost bits fall off | 9 >> 1  | 1001 >> 1    | 1100   | 12      |
| >>>      | Zero-fill right shift - Shift right by pushing zeroes in from the left and letting the rightmost bits fall off | 9 >>> 1 | 1001 >>> 1   | 0100   | 4       |



### 4 Statements

- Use `if` to specify a block of code to be executed, if a specified condition is true
- Use `else` to specify a block of code to be executed, if the same condition is false
- Use `else if` to specify a new condition to test, if the first condition is false
- Use `switch` to specify many alternative blocks of code to be executed



#### 4.1 if-else statements

``` java
boolean isTrue = true;
if (isTrue) {
  // true
}

if (5 <= 10) {
  // true
}

int a = 1;
if (a = 6) {
  // try this
}

int grade = 60;
if (grade < 60) {
  // below 60
} else if (grade >= 60 && grade < 80) {
  // between 60 and 80
} else {
  // above 80
}
```



#### 4.2 switch statements

``` java
int day = 4;
switch (day) {
  case 1:
    System.out.println("Monday");
    break;
  case 2:
    System.out.println("Tuesday");
    break;
  case 3:
    System.out.println("Wednesday");
    break;
  case 4:
    System.out.println("Thursday");
    break;
  case 5:
    System.out.println("Friday");
    break;
  case 6:
    System.out.println("Saturday");
    break;
  case 7:
    System.out.println("Sunday");
    break;
}
```

- When Java reaches a `break` keyword, it breaks out of the switch block.

- The `default` keyword specifies some code to run if there is no case match:



#### 4.3 while statements

The ```while``` loop loops through a block of code as long as a specified condition is true.

The `do/while` loop is a variant of the `while` loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

``` java
int i = 0;
while (i < 5) {
  i++;
}

int j = 0;
do {
  j++;
}
while (j < 5);



int flag = true;
while (flag) {
  // infinite loop
}


```



#### 4.4 for statements

When you know exactly how many times you want to loop through a block of code, use the `for` loop instead of a `while` loop.

``` java
for (statement 1; statement 2; statement 3) {
  // code block to be executed
}
```

- **Statement 1** is executed (one time) before the execution of the code block.

- **Statement 2** defines the condition for executing the code block.

- **Statement 3** is executed (every time) after the code block has been executed.

``` java
for (int i = 0; i < 10; i++) {
  // 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
}
```



There is also a "for-each" loop, which is used exclusively to loop through elements in an array

``` java
String[] colors = {"black", "white", "red", "green"};
for (String i : colors) {
  
}
```



### 5 Array

Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.

``` java
int[] nums = {1, 2, 3, 4, 5};
String[] colors = {"blue", "green", "red", "yellow"};
```

*More Array APIs, https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Arrays.html



### 6 String

Strings are used for storing text. 

A String variable contains a collection of characters surrounded by double quotes.

``` java
String str = "hey";
// txt.length() = 3
// str.charAt(0) = h
// str.compareTo("Hey")
```

*More String APIs, https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/String.html.