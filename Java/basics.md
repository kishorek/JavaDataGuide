- [What is Object Oriented](#what-is-object-oriented)
- [Why Java?](#why-java)
- [What is JRE, JDK & JVM?](#what-is-jre-jdk--jvm)
- [Battle of JDKs. OpenJDK vs Oracle JDK](#battle-of-jdks-openjdk-vs-oracle-jdk)
- [Datatypes](#datatypes)
  - [Details](#details)
  - [Character constant vs String Constant](#character-constant-vs-string-constant)
  - [Boxing & Unboxing](#boxing--unboxing)
  - [StingBuilder vs StringBuffer and immutability](#stingbuilder-vs-stringbuffer-and-immutability)
- [Language features](#language-features)
  - [Constructors](#constructors)
  - [Can the constructor be overridden?](#can-the-constructor-be-overridden)
  - [Difference between overloading and overriding?](#difference-between-overloading-and-overriding)
  - [Deconstructing the main](#deconstructing-the-main)](#deconstructing-the-maindeconstructing-the-main)
  - [Accessing non-static member from static method](#accessing-non-static-member-from-static-method)
  - [Difference between interface & abstract class](#difference-between-interface--abstract-class)
  - [Difference between instance variables & local variables](#difference-between-instance-variables--local-variables)
  - [Object creation](#object-creation)
  - [Static vs instance methods](#static-vs-instance-methods)
  - [equals](#equals)
  - [hashCode](#hashcode)
  - [equals + hashCode](#equals--hashcode)
  - [final](#final)
  - [Exception handling](#exception-handling)
  - [System object](#system-object)
  - [Deep copy vs Shallow copy](#deep-copy-vs-shallow-copy)
  - [References](#references)
  - [Access Modifiers](#access-modifiers)
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
JRE is an environment which is designed to run programs. It contains the class libraries, loader class, and JVM.

JVM - Java Virtual Machine  
JVM is an engine that provides a runtime environment to drive the Java Code or applications. It converts Java bytecode into machine language. JVM is a part of Java Run Environment (JRE). It cannot be separately downloaded and installed. To install JVM, you need to install JRE. The full form of JVM is Java Virtual Machine.

JDK - Java Developer Kit  
JDK is a software development environment used for making applets and Java applications


```
Tips:

rt.jar contains all the java runtime libraries.
rt - Run Time
```

## Battle of JDKs. OpenJDK vs Oracle JDK

## Datatypes
### Details
### Character constant vs String Constant
### Boxing & Unboxing
### StingBuilder vs StringBuffer and immutability
## Language features
### Constructors
### Can the constructor be overridden?
### Difference between overloading and overriding?
### Deconstructing the main](#deconstructing-the-main)
### Accessing non-static member from static method
### Difference between interface & abstract class
### Difference between instance variables & local variables
### Object creation
### Static vs instance methods
### equals
### hashCode
### equals + hashCode
### final
### Exception handling
### System object
### Deep copy vs Shallow copy
### References
### Access Modifiers
### Decompiling
## Serialization
## I/O
### Stream vs Reader
