## Java Object Oriented Programming Concepts I



### OOP

OOP stands for Object-Oriented Programming.

This article helps you to understand [OOP](https://www.freecodecamp.org/news/object-oriented-programming-concepts-21bb035f7260/).



#### 1. Declare a class

Use the keyword **class** to create a class.

``` java
class MyClass {
    
}
```



#### 2. Field

A variable of the class called a **field**.

``` java
class ThreeNumbers {

    int firstNumber;
    int secondNumber;
    int thirdNumber;
}
```



#### 3. Method

A method (also known as function) is a block of code which only runs when it is called. For more information of method, [arguments](https://docs.oracle.com/javase/tutorial/java/javaOO/arguments.html).

``` java
class ThreeNumbers {

    int firstNumber;
    int secondNumber;
    int thirdNumber;

    int sumOfThreeNumbers() {

        return firstNumber + secondNumber + thirdNumber;
    }
}
```



#### 4. Constructor

A constructor in Java is a **special method** that is used to initialize/create object and it can also be overloaded like Java methods.Constructor name must be the same as its class name.

``` java
class Main {

    public static void main(String[] args) {

        ThreeNumbers constructorA = new ThreeNumbers();
        constructorA.log();
        ThreeNumbers constructorB = new ThreeNumbers(1);
        constructorB.log();
        ThreeNumbers constructorC = new ThreeNumbers(1, 2);
        constructorC.log();
        ThreeNumbers constructorD = new ThreeNumbers(1, 2, 3);
        constructorD.log();
    }
}

class ThreeNumbers {

    int firstNumber;
    int secondNumber;
    int thirdNumber;

    void log() {

        System.out.println(firstNumber);
        System.out.println(secondNumber);
        System.out.println(thirdNumber);
    }

    ThreeNumbers() {

        this.firstNumber = -1;
        this.secondNumber = -1;
        this.thirdNumber = -1;
    }

    ThreeNumbers(int firstNumber) {

        this.firstNumber = firstNumber;
        this.secondNumber = -1;
        this.thirdNumber = -1;
    }

    ThreeNumbers(int firstNumber, int secondNumber) {
        
        this.firstNumber = firstNumber;
        this.secondNumber = secondNumber;
        this.thirdNumber = -1;
    }

    ThreeNumbers(int firstNumber, int secondNumber, int thirdNumber) {
        
        this.firstNumber = firstNumber;
        this.secondNumber = secondNumber;
        this.thirdNumber = thirdNumber;
    }
}
```



#### 5. Access Modifier

There are two types of modifiers in Java: **access modifiers** and **non-access modifiers**.

The access modifiers in Java specifies the accessibility or scope of a field, method, constructor, or class. We can change the access level of fields, constructors, methods, and class by applying the access modifier on it.



#### Access Modifiers

For **classes**, you can use either `public` or *default*:

| Modifier      | Description                                                  |
| :------------ | :----------------------------------------------------------- |
| `public`      | The class is accessible by any other class                   |
| ```default``` | The class is only accessible by classes in the same package. This is used when you don't specify a modifier. |

For **fields, methods and constructors**, you can use the one of the following:

| Modifier      | Description                                                  |
| :------------ | :----------------------------------------------------------- |
| `public`      | The code is accessible for all classes                       |
| `private`     | The code is only accessible within the declared class        |
| ```default``` | The code is only accessible in the same package. This is used when you don't specify a modifier. |
| `protected`   | The code is accessible in the same package and subclasses.   |



#### Non-Access Modifiers

For **classes**, you can use either `final` or `abstract`:

| Modifier   | Description                                     |
| :--------- | :---------------------------------------------- |
| `final`    | The class cannot be inherited by other classes. |
| `abstract` | The class cannot be used to create objects.     |

For **attributes and methods**, you can use the one of the following:

| Modifier       | Description                                                  |
| :------------- | :----------------------------------------------------------- |
| `final`        | Attributes and methods cannot be overridden/modified         |
| `static`       | Attributes and methods belongs to the class, rather than an object |
| `abstract`     | Can only be used in an abstract class, and can only be used on methods. |
| `transient`    | Attributes and methods are skipped when serializing the object containing them |
| `synchronized` | Methods can only be accessed by one thread at a time         |
| `volatile`     | The value of an attribute is not cached thread-locally, and is always read from the "main memory" |



#### 6. This and super keyword

This keyword can be used to 

	1. refer current class instance variable.
 	2. invoke current class method (implicitly)
 	3. invoke current class constructor.



Super keyword can be used to 

	1. refer immediate parent class instance variable.
 	2. invoke immediate parent class method.
 	3. invoke immediate parent class constructor.



#### 7. Encapsulation

The meaning of Encapsulation is to provide public get or set methods to access and update the value of a private variable.

For **read-only** field, only create the get method.

For **write-only** field, only create the set method.

``` java
public class Person {

    private String name;

    // getter
    public String getName() {
        
      return name;
    }
  
    // setter
    public void setName(String name) {

      this.name = name;
    }
}
```



#### 8. Enum

An enum is a special "class" that represents a group of constants (unchangeable variables, like final variables).

Enum is short for "enumerations", which means "specifically listed".

``` java
public class Main {

    enum Grade {
        A,
        B,
        C,
        F
    }
    public static void main(String[] args) {

        Grade myGrade = Grade.A;
    }
}
```

