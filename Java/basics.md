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
  - [Deconstructing the main](#deconstructing-the-main)](#deconstructing-the-maindeconstructing-the-main)
  - [Accessing non-static member from static method](#accessing-non-static-member-from-static-method)
  - [Difference between interface & abstract class](#difference-between-interface--abstract-class)
  - [Difference between instance variables & local variables](#difference-between-instance-variables--local-variables)
  - [Object creation](#object-creation)
  - [Access Modifiers](#access-modifiers)
  - [Other modifiers](#other-modifiers)
  - [Static](#static)
  - [Interning](#interning)
  - [Mutable & Immutable](#mutable--immutable)
  - [StingBuilder vs StringBuffer and immutability](#stingbuilder-vs-stringbuffer-and-immutability)
  - [equals](#equals)
  - [hashCode](#hashcode)
  - [equals + hashCode](#equals--hashcode)
  - [final](#final)
  - [Exception handling](#exception-handling)
  - [System object](#system-object)
  - [Deep copy vs Shallow copy](#deep-copy-vs-shallow-copy)
  - [References](#references)
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
### Can the constructor be overridden?
### Difference between overloading and overriding?
### Deconstructing the main](#deconstructing-the-main)
### Accessing non-static member from static method
### Difference between interface & abstract class
### Difference between instance variables & local variables
### Object creation
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
### hashCode
### equals + hashCode
### final
### Exception handling
### System object
### Deep copy vs Shallow copy
### References

### Decompiling
## Serialization
## I/O
### Stream vs Reader
