- [What is Object Oriented](#what-is-object-oriented)
- [Why Java?](#why-java)
- [What is the difference between JDK & JVM?](#what-is-the-difference-between-jdk--jvm)
- [Battle of JDKs. OpenJDK vs Oracle JDK](#battle-of-jdks-openjdk-vs-oracle-jdk)
- [Datatypes](#datatypes)
  - [Details](#details)
  - [Character constant vs String Constant](#character-constant-vs-string-constant)](#character-constant-vs-string-constantcharacter-constant-vs-string-constant)
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
- [Serialization](#serialization)
- [I/O](#io)
  - [Stream vs Reader](#stream-vs-reader)

## What is Object Oriented

Object-oriented is a programming paradigm that relates the programming to logical objects. Like real life objects, programming objects will have their characteristics(state) & functionalities(methods). Some other features like inheritance, abstraction (), polymorphism, encapsulation (hiding the data implementation) will be applied to programming too.

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


## What is the difference between JDK & JVM?
## Battle of JDKs. OpenJDK vs Oracle JDK
## Datatypes
### Details
### Character constant vs String Constant](#character-constant-vs-string-constant)
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
## Serialization
## I/O
### Stream vs Reader
