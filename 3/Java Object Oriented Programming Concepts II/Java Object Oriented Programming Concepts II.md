## Java Object Oriented Programming Concepts



#### 1. Java Packages & API

A package in Java is used to group related classes. Packages are divided into two categories:

	1. Built-in Packages (packages from the Java API)
 	2. User-defined Packages (create your own packages)



``` java
import package.name.Class;   // Import a single class
import package.name.*;       // Import the whole package
```



To create a package, use the package keyword

``` java
package mypack;
class MyPackageClass {
  public static void main(String[] args) {
    System.out.println("This is my package!");
  }
}
```



#### 2. Inheritance

Inheritance, in short, inherit fields and methods from one class to another.

-   subclass (child class): the class that inherits from another class
-   superclass (parent class): the class being inherited from

Use extends keyword to **inherit** from a class.

``` java
public class Main {
    public static void main(String[] args) {

        AndroidCourse AndroidCourseObject = new AndroidCourse();
        AndroidCourseObject.courseName = "Android App Development";
        AndroidCourseObject.courseNumber = 4410;
        AndroidCourseObject.logInfo();
    }
}

class ITCourse {

    String courseName;
    int courseNumber;

    public void logInfo() {

        System.out.println(courseName);
        System.out.println(courseNumber);
    }
}

class AndroidCourse extends ITCourse{

    String courseContent;

}
```



#### 3. Abstraction

Abstraction keyword is used for classes and methods:

-   Abstract class: cannot be used to create objects.
-   Abstract method: can only be used in an abstract class, and it does not have a body. The body is provided by the subclass. 

``` java
public class Main {
    public static void main(String[] args) {

        Login login = new Login(); // Error
        UserLogin userLogin = new UserLogin();
    }
}

abstract class Login {

    abstract void login();
    abstract void logout();
    abstract boolean isLoggedin();
}

class UserLogin extends Login{

    @Override
    void login() {
        // TODO Auto-generated method stub
    }

    @Override
    void logout() {
        // TODO Auto-generated method stub
        
    }

    @Override
    boolean isLoggedin() {
        // TODO Auto-generated method stub
        return false;
    }
}
```



#### 4. Interface

Interface is another way to achieve abstraction in Java.

To access the interface methods, the interface must be "implemented" (kinda like inherited) by another class with the implements keyword (instead of extends). The body of the interface method is provided by the "implement" class.

Use interface keyword to create an interface: 

``` java
interface Course {
  
  public void logCourseNumber();
  public void logCourseName();
}
```



##### Multiple Interfaces

``` java
interface FirstInterface {

    public void myFirstMethod();
}
  
interface SecondInterface {

    public void mySecondMethod();
}

interface ThirdInterface extends SecondInterface {
    
    public void myThirdMethod();
}
  
class DemoClass implements FirstInterface, ThirdInterface  {
    public void myFirstMethod() {
        System.out.println("myFirstMethod");
    }
    public void mySecondMethod() {
      System.out.println("mySecondMethod");
    }
    public void myThirdMethod() {
        System.out.println("myThirdMethod");
    }
}
  
class Main {
    public static void main(String[] args) {
      DemoClass myObj = new DemoClass();
      myObj.myFirstMethod();
      myObj.mySecondMethod();
      myObj.myThirdMethod();
    }
}
```





#### 5. Inner Classes

Inner class is also known as nested class. The purpose of nested classes is to group classes that belong together, which makes your code more readable and maintainable.

``` java
class OuterClass {
  int x = 10;

  class InnerClass {
    int y = 5;
  }
}

public class Main {
  public static void main(String[] args) {
    OuterClass myOuter = new OuterClass();
    OuterClass.InnerClass myInner = myOuter.new InnerClass();
    System.out.println(myInner.y + myOuter.x);
  }
}

// Outputs 15 (5 + 10)

```







