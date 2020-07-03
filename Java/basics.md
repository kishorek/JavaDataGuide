- [What is Object Oriented](#what-is-object-oriented)
- [Why Java?](#why-java)
- [What is JRE, JDK & JVM?](#what-is-jre-jdk--jvm)
- [Battle of JDKs. OpenJDK vs Oracle JDK](#battle-of-jdks-openjdk-vs-oracle-jdk)
- [Datatypes](#datatypes)
  - [Character vs String](#character-vs-string)
  - [Boxing & Unboxing](#boxing--unboxing)
- [Language features](#language-features)
  - [Constructors](#constructors)
  - [Can the constructor be overridden?](#can-the-constructor-be-overridden)
  - [Difference between overloading and overriding?](#difference-between-overloading-and-overriding)
  - [Difference between interface & abstract class](#difference-between-interface--abstract-class)
  - [Difference between instance variables & local variables](#difference-between-instance-variables--local-variables)
  - [Object creation](#object-creation)
  - [Access Modifiers](#access-modifiers)
  - [Other modifiers](#other-modifiers)
  - [Static](#static)
  - [Deconstructing the main](#deconstructing-the-main)
  - [Interning](#interning)
  - [Mutable & Immutable](#mutable--immutable)
  - [StingBuilder vs StringBuffer and immutability](#stingbuilder-vs-stringbuffer-and-immutability)
  - [equals](#equals)
  - [hashCode](#hashcode)
  - [equals + hashCode](#equals--hashcode)
  - [final](#final)
  - [Pass by Reference or Pass by Value?](#pass-by-reference-or-pass-by-value)
  - [System object](#system-object)
  - [Deep copy vs Shallow copy](#deep-copy-vs-shallow-copy)
  - [References **](#references)
  - [Decompiling](#decompiling)
- [Serialization](#serialization)
- [I/O](#io)
  - [Stream vs Reader](#stream-vs-reader)

## What is Object Oriented

Object-oriented is a programming paradigm that relates the programming to logical objects. Like real life objects, programming objects will have their characteristics(state) & functionalities(methods). Some other features like inheritance (Deriving or sharing common traits), abstraction (expose only the high level implementation), polymorphism (change behaviour based on the context or input), encapsulation (hiding the data implementation) will be applied to programming too.

A car is a type of vehicle which has a brand, registration no, mileage etc and it can be driven, gears can be shifted.

```java
class Car extends Vehicle{
    protected String brand;
    protected String regNo;
    protected Double mileage;

    public void drive(){
        // Drive the car
    }

    public void shiftGear(int gear){
        // Shift gear
    }

}
```


## Why Java?
Java achieves platform indepedency with JVM. So ideally a program written in one operating system can be run on any operating system with JVM in it.

Java is a purely Object Oriented language, apart from the primitive data types and keywords pretty everything else is an object in java.

Java converts the code into bytecode and JVM converts it into machine code which provides great performance. Multi threading is built right into the core, so writing applications with concurrent threads are highly possible.

Java is secure by design. Lots of opensource libraries, big and mature community support, readily available frameworks and highly proven IDEs support accelerated development.

## What is JRE, JDK & JVM?
pic-here

JRE - Java Runtime Environment
JRE is an environment which is designed to run programs. It contains the class libraries, loader class, and JVM. It is platform dependent.

JVM - Java Virtual Machine
JVM is an engine that provides a runtime environment to drive the Java Code or applications. It converts Java bytecode into machine language. JVM is a part of Java Run Environment (JRE). It cannot be separately downloaded and installed. To install JVM, you need to install JRE. The full form of JVM is Java Virtual Machine. It is platform independent.

JDK - Java Developer Kit
JDK is a software development environment used for making applets and Java applications. It contains developing, debuggin & monitoring libraries. It is platform dependent.


```
Tips:

rt.jar contains all the java runtime libraries.
rt - Run Time
```

## Battle of JDKs. OpenJDK vs Oracle JDK
Sun microsystems owned the JDK until Oracle acquired Sun microsystems. So Sun JDK has become Oracle JDK after the acquisition. Oracle maintains the Oracle JDK.

OpenJDK is an open source implementation of the Java Standard Edition platform with contribution from Oracle and open Java community. OpenJDK was the reference implementation for Java 7, maintained by Oracle.

Oracle JDK is built from the OpenJDK, so technically there are no much differences apart from the enterprise support and bug fixes Oracle JDK provides. However Oracle SDK provides better performance over OpenJDK.

OpenJDK is released under license `GPL v2` wherein Oracle JDK is licensed under `Oracle Binary Code License Agreement`.

Oracle JDK has Flight Recorder, Java Mission Control, and Application Class-Data Sharing features, while OpenJDK has the Font Renderer feature.

## Datatypes
![Data Types](../images/Java_Datatypes.png?raw=true "Data Types")

### Character vs String
char (Character) datatype (primitive) is a single character surrounded by single quotes. It occupies 2 bytes of memory size. String is a non primitive Object, it is usually one or more characters surrounded by double quotes.

```
Eg:
char -> 'a','1','.' etc
String -> "a", "a is an English alphabet", "1 + 1 = 2"
```

### Boxing & Unboxing
`Autoboxing` is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes. For example, converting an int to an Integer, a double to a Double, and so on. If the conversion goes the other way, this is called `unboxing`.

|Primitive type|Wrapper class|
|--- |--- |
|boolean|Boolean|
|byte|Byte|
|char|Character|
|float|Float|
|int|Integer|
|long|Long|
|short|Short|
|double|Double|

Since Java is a Object Oriented language, in order to utilize the Object level features like Collections it is necessary for the primitive datatypes need to be converted to Objects. Java provides Autoboxing to facilitate this.

## Language features
### Constructors
Constructors are special methods that are invoked during the object creation. Constructors look like normal methods except that they do return anything.

By default all the Classes will have a default constuctor which takes no arguments. If we create any new constructor for a class with arguments, that will become the default constructor. i.e. Whenever we create an object of the class using `new` operator, the arguments should be passed. We can override this by providing an additional constructor with no argument. A class can have any number of constructors. We can use access modifiers on the constructors to set the access on who can instantiate the class (or create the object).

### Can the constructor be overridden?
No. Overriding happens when a subclass has the same name, number/type of parameters, and the same return type as an instance method of the superclass. But constructors are special methods that are assigned to a class to be invoked during Object creation. Similarly they can not be inherited, though it can be accessed using `super`.

### Difference between overloading and overriding?
Overloading - When two or more methods in a class have the same method name but different parameters.

Overriding - Having two methods with the same method name and parameters (i.e., method signature). This will be used between parent and subclasses. Where a subclass can override the method available in the parent to modify the purpose of the method. The actual method can always be called from the subclass using `super`

### Difference between interface & abstract class

|Abstract class|Interface|
|--- |--- |
|1) Abstract class can have abstract and non-abstract methods.|Interface can have only abstract methods. (Since Java 8, it can have default and static methods also.)|
|2) Abstract class doesn't support multiple inheritance.|Interface supports multiple inheritance.|
|3) Abstract class can have final, non-final, static and non-static variables.|Interface has only static and final variables.|
|4) Abstract class can provide the implementation of interface.|Interface can't provide the implementation of abstract class.|
|5) The abstract keyword is used to declare abstract class.|The interface keyword is used to declare interface.|
|6) An abstract class can extend another Java class and implement multiple Java interfaces.|An interface can extend another Java interface only.|
|7) An abstract class can be extended using keyword "extends".|An interface can be implemented using keyword "implements".|
|8) A Java abstract class can have class members like private, protected, etc.|Members of a Java interface are public by default.|
|9)Example: public abstract class Shape{public abstract void draw();}|Example: public interface Drawable{void draw();}|

Ref: [https://www.javatpoint.com/difference-between-abstract-class-and-interface]()

After Java 8, the difference between them has been changed. Mainly since interfaces now can have default & static methods.
```java
public interface MyInterface {
     
    // regular interface methods
     
    default void defaultMethod() {
        // default method implementation
    }

    static double convertToFarenheit(double celcius) {
        return (celcius * 9/5) + 32;
    }
}

//Usage:
MyInterface.convertToFarenheit(40)

MyClass object = new MyClass(); //MyClass implements MyInterface
object.defaultMethod()

```

### Difference between instance variables & local variables
Local variables:
They are scoped inside a method/block. Outside the method or block they do not exist. They do not have any default value.

Instance variables:
They are bound to an object always. They are declared in a class. The access is restricted by the access modifiers. Every instance of the class will have their own copy of variables. i.e. Changing the variable on one object doesn't change it on another object. Whenever an object is allocated in heap, a slot is allocated for this variable. So its lifecycle starts and ends along with the object.

### Object creation
An object is said to be created when the class is instantiated (mostly by using `new`, some exceptions are String literals, auto boxing of primitive data etc). The below process happens during the object creation.

1. Memory is allocated.
2. Fields are instantiated to their default values.
3. First line of the corresponding constructor is executed.
4. The instance initializer is executed and the fields are initialized to their requested values.
5. The rest of the constructor code is executed

### Access Modifiers
Java uses different access modfiers to set the access levels on variables, methods, constructors and classes.

* Visible to the package, the default. No modifiers are needed.
* Visible to the class only - `private`
* Visible to the world - `public`
* Visible to the package and all subclasses - `protected`

### Other modifiers
Apart from the access modifiers, the below keywords aka Non-Access modifiers can be used to achieve different functionalities.
* Creating class methods and variables - `static`
* Finalizing the implementations of classes, methods, and variables - `final`
* Creating abstract classes and methods - `abstract`
* For threads - `synchronized` & `volatile`

### Static
Static variables are also known as class variables. These variables exist independently of creation of instances. They can be accessed directly via classes. Regardless of how many instances of a class is created, there will always be a single copy static variable exist. They can be accessed using `ClassName.variable`.

Similar to variables, methods also can be marked as static to make them class methods. They can be called using `ClassName.method()`.

Since static methods are tied to class, it can not use any instance variable or methods (non static). But non-static methods can access or call static variables/methods.

Static block is used for initializing the static variables.This block gets executed when the class is loaded in the memory. A class can have multiple Static blocks, which will execute in the same sequence in which they have been written into the program

```java

class StaticSample{
  private static final String ENDPOINT = "/test";

  //Static block
  {

  }

  public static String fetchEndpoint(String baseUrl){
    return baseUrl + ENDPOINT;
  }

  public void printEndpoint(){
    System.out.println(ENDPOINT)
  }
}

```

### Deconstructing the main](#deconstructing-the-main)
Any java class that has to be executed needs an entrypoint. A class should contain `main()` if the class wants to initiate the execution.

```java
public static void main(String[] args) {

}
```

The above is a sample `main()`. `public` access modifier exposes the method outside the current package. `static` enables this method can be executed without instantiating any class. `main()` method can take string arguments which can be passed as command line parameters during the execution.

### Interning
String Interning is a method of storing only one copy of each distinct String Value, which must be immutable.

In Java, String class has a public method `intern()` that returns a canonical representation(Standaridized representation) for the string object. Java’s String class privately maintains a pool of strings, where String literals are automatically interned.

When the `invoke()` method is invoked an a String object, if the String literal is available in the pool, the reference of the object is returned from the pool. If it is not available in the pool, the object is added to the pool and the reference returned.

But when a String object is created with `new String()` a new object is created in Heap memory and returned. So this way of String initialization is mostly discouraged on performance grounds.

### Mutable & Immutable
When an object can change it's state, it is called a mutable Object. (In X-Men, people can can alter their form or abilities are called mutables).

Immutability provides Security, Performance & Thread Safety.

```
Tip:
Normally immutability in java is achieved through following steps :

1. Don’t provide mutator methods for any field
2. Make all fields final and private
3. Don’t allow subclasses by declaring the class final itself
4. Return deep cloned objects with copied content for all mutable fields in class
```

### StingBuilder vs StringBuffer and immutability


### equals
Every object in Java has this method to compare it with another object. By default, it checks the reference. If both the object has the same references, it will be decided equal. But there are scenarios where we want to define the equality by checking the instance variables, that is when we will override this method.

As per Java SE, the below is the contract that any `equals()` should satisfy.

* It is reflexive: for any non-null reference value x, x.equals(x) should return true.
* It is symmetric: for any non-null reference values x and y, x.equals(y) should return true if and only if y.equals(x) returns true.
* It is transitive: for any non-null reference values x, y, and z, if x.equals(y) returns true and y.equals(z) returns true, then x.equals(z) should return true.
* It is consistent: for any non-null reference values x and y, multiple invocations of x.equals(y) consistently return true or consistently return false, provided no information used in equals comparisons on the objects is modified.
For any non-null reference value x, x.equals(null) should return false.


```java
public class Car {
    private int registrationNo;
    private String model;

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;

        Car car = (Car) o;

        return registrationNo == car.registrationNo;
    }
}
```

### hashCode

`hashCode()` returns an integer representation of the current instance of the class.

Similar to `equals()`, `hashCode()` also has the below contract.

* Whenever it is invoked on the same object more than once during an execution of a Java application, the hashCode method must consistently return the same integer, provided no information used in equals comparisons on the object is modified. This integer need not remain consistent from one execution of an application to another execution of the same application.
* If two objects are equal according to the `equals(Object)` method, then calling the hashCode method on each of the two objects must produce the same integer result.
* It is not required that if two objects are unequal according to the `equals(java.lang.Object)` method, then calling the hashCode method on each of the two objects must produce distinct integer results. **However, the programmer should be aware that producing distinct integer results for unequal objects may improve the performance of hash tables.**


```java
public class Car {
    private int registrationNo;
    private String model;

    @Override
    public int hashCode() {
        int result = registrationNo;
        result = 31 * result + model.hashCode();
        return result;
    }
}

```
### equals + hashCode
We should calculate `hashCode()` in consistent with the definition of equality for the class. Thus if we override the `equals()` method, we also have to override `hashCode()`. Mainly because the `equals()` and `hashCode()` should be aligned for checking equality and provide support for HashMap etc. All the modern IDEs provide an option to generate these 2 methods.

```java
public class Car {
    private int registrationNo;
    private String model;

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;

        Car car = (Car) o;

        if (registrationNo != car.registrationNo) return false;
        return model.equals(car.model);
    }

    @Override
    public int hashCode() {
        int result = registrationNo;
        result = 31 * result + model.hashCode();
        return result;
    }
}

```

### final
`final` is where everything is finalized and there is no change is allowed. A class can be marked as final to avoid being extended (methods can not be overloaded or overridden). For example, `String` class is marked as final. `String` class is designed to be immutable in nature. But its also marked as `final` to avoid being extended to destroy its immutability.

Methods marked with `final` can not be overridden in the subclasses.

`final` can be used to mark any instance variable as constant. `final` variables can not be modified once declared.

```
Tip:
Method arguments can be marked as final to avoid getting their value changed inside the method's scope
```
### Pass by Reference or Pass by Value?
**Java is always pass by value.** Mutable arguments, can get their values changed. But that doesn't mean Java is pass by reference. Because the reference to the object never changes. It's only the values that are mutated. This can be explained easily with primitive data passed to methods, which never gets changed.

### System object
The System class contains several useful class fields and methods. It cannot be instantiated.

It provides options like accessing Standard Inputstream, Outputstream, Garbage Collection, Time, Environment variables, System proerties etc.

### Deep copy vs Shallow copy
Java provides `clone()` for all the Objects, which can be used to clone an object (The class should implement `Cloneable` interface). But there is a catch, it will work very well for immutable and primitive fields. When the cloned object modifies the refered mutable object, it also changes the original object's fields since the cloning copies only the references. This is Shallow Copy.

```java
class Car implements Cloneable{
    int no;
    String model;
    Engine engine;
    final int num = 1000;
    
    public Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}

class Engine{
    String make;
}

//Execution
Car car1 = new Car();
car1.no = 100;
car1.model = "Benz";

Engine engine = new Engine();
engine.make = "2020";
car1.engine = engine;

Car car2 = (Car) car1.clone();

System.out.println("Car 1: "+car1.no+" "+car1.engine.make);
System.out.println("Car 2: "+car2.num+" "+car2.engine.make);
car2.engine.make = "2021";
System.out.println("Car 1: "+car1.no+" "+car1.engine.make);

/* Output

Car 1: 100 2020
Car 2: 1000 2020
Car 1: 100 2021

*/

```

Deep Copy on the other side, copies all the fields recursively and copies the values into the new object. So there will not be any references maintained. This process is slower than Shallow Copy and tedious to implement. There are libraries to implement

### References **
Supported References:
1. Strong Reference
2. Weak Reference
3. Soft Reference
4. Phantom Reference

Strong Reference:
Whenever we create an object and assign it, it will be a strong reference by default.

```java
Employee emp = new Employee();
```

Here `emp` is strong referenced and it can't be garbage collected until the reference becomes null.

```java
emp = null;
```

Weak Reference:  
This can be created by creating from `java.lang.ref.WeakReference` explicitly. Any object with weak reference will be marked for garbage collection, and whenever the system needs memory this object will be Garbage collected.

```java
// Strong Reference
Employee emp = new Employee();

WeakReference<Employee> weakref = new WeakReference<Employee>(emp);

//Now, emp is ready to be garbage collected when JVM needs memory
emp = null;

// But we can retrieve back the weakly referenced object. if its not Garbage collected
emp = weakref.get();
```

Soft Reference:  
This can be created using `java.lang.ref.SoftReference`. Only difference from Weak reference is, here the object will be garbage collected only when JVM runs out of memory (Not during normal garbage collection).


Phantom Reference:
This can be created using `java.lang.ref.PhantomReference`. Before garbage collection, the object will be put in a reference queue.

### Decompiling
When Java compiles, it creates bytecode (`.class` files) from the `.java` files. The class files are not human readable.

There are times we may need to decompile for debug or peek into the libraries that doesn't come with documentation. We can decompile the class files into java files back to read through (unless the source code is obfuscated). This can be done in Eclipse IDE using a plugin called `Enhanced Class Decompiler (ECD)`. IntelliJ IDEA provides this by default.

I personally prefer [JD-GUI](http://java-decompiler.github.io/) for decompiling the jar files.

## Serialization


## I/O
### Stream vs Reader
