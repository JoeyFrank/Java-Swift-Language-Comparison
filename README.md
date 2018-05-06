# Java-Swift-Language-Comparison
A comparison between the Swift and Java object oriented programming languages


Language purpose/genesis  
Unique features of the language  
Name spaces  
Types  
Classes  

### Instance reference name in data type (class)

  * Java | Swift
    ---- | -----
    This | self

### Properties

* Getters and setters

  * Java | Swift
    ---- | -----
    You have to create your own getters and setters | Getters and setters for constants, variables, and subscripts automatically receive the same access level as the constant, variable, property, or subscript they belong to. You can give a setter a lower access level than its corresponding getter, to restrict the read-write scope of that variable, property or subscript.
* Backing variables

  * Java | Swift
    ---- | -----
    Java does not have backing fields. | Swift unifies Objective-C's ways to store variables into a single property declaration. Swift doesn't have a corresponding instance variable, and the backing variable for a property is not accessed directly. All the information about a property is stored in a single location. 
    
* Computed properties

  * Java | Swift
    ---- | -----
     As soon as you use a custom getter and/or setter method with a variable, it is a computed property | Calculate a value rather than storing the value by providing a getter and an optional setter to retrieve and set other properties and values indirectly
    
### Interfaces / protocols
* What does the language support

  * Java | Swift
    ---- | -----
    Interfaces|Protocols
    
* What abilities does it have?

  * Java | Swift
    ---- | -----
    You are able to implement as many interfaces as needed. The interface will also force you to include all methods defined within it in every class that implements it. | The protocol can be adopted by a class, structure, or enumeration to provide an actual implementation of those requirements. Any type that satisfies the requirements of a protocol is said to conform to that protocol. In addition to specifying requirements that conforming types must implement, you can extend a protocol to implement some of these requirements or to implement additional functionality that conforming types can take advantage of.

* How is it used?

  * Java | Swift
    ---- | -----
    Unless the class that implements the interface is abstract, all the methods of the interface need to be defined in the class. The interface keyword is used to declare an interface. A class uses the implements keyword to implement an interface. The implements keyword appears in the class declaration following the extends portion of the declaration. |  The protocol specifies whether each property must be gettable or gettable and settable. They can also require specific instance methods and type methods to be implemented by conforming types, which are written as part of the protocol's definition without curly braces or a method body.
    
### Inheritance / extension

* Inheritance

  * Java | Swift
    ---- | -----
    Multiple inheritance is not allowed (A class extending multiple classes). You can have superclass = new subclass(), but you cannot have subclass = new superclass(). It's used to gain access to another class' members, including methods and fields. | Only classes can inherit from another class. In other words, structures and enumerations don't support inheritance. Multiple inheritance is also not allowed. It's used to gain access to another class' members, including methods and fields.
  
* Extension

  * Java | Swift
    ---- | -----
    Does not support extension | Extensions add new functionality to an existing class, structure, enumeration, or protocol type. This includes the ability to extend types for which you do not have access to the original source code (known as retroactive modeling). Four uses include protocol conformance, preserving initializers, code separation, and nested types.


### Reflection

* What reflection abilities are supported?

  * Java | Swift
    ---- | -----
    Makes it possible to inspect classes, interfaces, fields and methods at runtime, without knowing the names of the classes, methods etc. at compile time. It is also possible to instantiate new objects, invoke methods and get/set field values using reflection. | Swift's reflection capabilities are based around a struct called Mirror. You create a mirror for a particular subject and the mirror will then let you query it.

* How is reflection used?

  * Java | Swift
    ---- | -----
    Java Reflection can be used to map properties in JSON files to getter / setter methods in Java objects, like Jackson, GSON, Boon etc. does. Or, Reflection can be used to map the column names of a JDBC ResultSet to getter / setter methods in a Java object. | Its current functionality allows us to look at the objects’ properties without modifying them, which is represented by Mirror structure 

### Memory management 
#### In Java
One of the immediate things that one will understand about memory management in Java is its garbage collector, which automatically handles closing and freeing of allocated memory. Besides that though, java has a Java Memory Model, often referred to as JVM. The JVM creates a heap to store memory, and when the heap is filled, garbage is collected. The heap is often split into two nodes; a young generation and an old generation. The young generation is used primarily for allocation of objects, while the old generation holds long-lived objects. The young generation exists because most objects are short lived, which helps speed up the process of allocation and deallocation.
#### In Swift
Much memory allocation in Swift is handled through Allocation Reference Counting, or ARC. ARC is used to be predictable and efficient in resource scarce environments, such as iOS. Although automatic, relationships between objects do need to be considered in order to avoid memory leaks. Situations such as reference cycles can throw a wrench in the ARC, so while it typically works very well, it's important to keep good code.
### Comparisons of references and values
#### In Java
== and != are comparison operators used to compare memory locations of objects. == and != are not used to compare the contents of objects.  For instance, <br />
int a = 5<br />
int b = a<br />
a == b returns true<br />
.equals is a method that all objects have that is used to compare the contents of objects, not their locations. For instance,<br />
String a = "bee"<br />
String b = "bee"<br />
a.equals(b) will return true, though a == b will return false<br />
#### In Swift
To compare references in swift, a === operator is used. The == is used to compare contents of objects. For instance,<br />
let a = IntegerRef(10)<br />
let b = a<br />
let c = IntegerRef(10)<br />
a == b  -----> returns true, because their contents are the same<br />
a === b -----> returns true, because a and b reference the same address<br />
a === c -----> returns false, because although they both equal 10, they reference different addresses<br />
### Null/nil references
#### In Java
In Java, null can be assigned to any variable of reference (non-primitive) type. Used to signify "no object," "unknown," or "unavailable." 
#### In Swift
In Swift, null is handled by optionals, which can signify the absence of a value (nil). Optionals work for any type, not just non-primitive types. In Swift, non-optional values can not be null. The presence of optionals is thought to be very safe, and removes much fear of error due to he strict rules revolving around null/nil.
### Errors and exception handling 
#### In Java
An error in Java is a serious problem that an application should not or could not try to catch, whereas an exception is a condition that an application should try to catch. Errors, such as OutOfMemory, can't be handled in the same way that exceptions can. With exceptions, an opportunity is given to try to do something else with it.
#### In Swift
In swift, errors conform to the error protocol, and the programmer can throw an error to indicate failure, instead of absolute failure like in Java. One of the notable things in error catching for swift is guard statements. Guard allows for optional unwrapping, giving the programmer more flexibility in preparing for potential errors.
### Lambda expressions, closures, or functions as types  
#### In Java
Anonymous classes are used to implement a method that has been defined by a funtional interface. Using an arrow like so: <br />(n)—>n+n<br />The left side specifies the parameters, and the right side is the lambda body. These lambda expressions allow the programmer to define a method without necessarily having to name it. One common use of lambda expressions is to use them as arguments, treating them almost as if they were n actual data type. While functions can't explicitly be data types in Java, lambda expressions are close to treating them as such.
#### In Swift
Unlike in Java, functions in Swift are actual data types, and can be treated as such. The type of function consists of its parameter types and return type. Because of this, functions in swift can be assigned to variables, like so... <br />
var mathFunction: (Int, Int) -> Int = addTwoInts<br />
Not only can functions in swift be variables, but can be parameters and return types for other functions

Implementation of listeners and event handlers  
Singleton  
Procedural programming  
Functional programming  
Multithreading  
