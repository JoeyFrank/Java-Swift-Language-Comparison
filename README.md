# Java-Swift-Language-Comparison
A comparison between the Swift and Java object oriented programming languages by Joseph Frank, Mercy Housh, Austin Sizemore, and Ian Smith



##**Language purpose/genesis:**

Java:

Java is a general-purpose computer-programming language that is concurrent, class-based, object-oriented, and specifically designed to have as few implementation dependencies as possible -google language purpose

Swift:

Swift is a general-purpose, multi-paradigm, compiled programming languagedeveloped by Apple Inc. for iOS, macOS, watchOS, tvOS, and Linux. Swift is designed to work with Apple's Cocoa and Cocoa Touch frameworks and the large body of existing Objective-C (ObjC) code written for Apple products. -also same google


##**Unique features of the language:**

Java:

A Java virtual machine (JVM) is a virtual machine that enables a computer to run Java programs as well as programs written in other languages and compiled to Java bytecode.

Swift:

This language is heavily integrated with apple systems and is almost entirely exclusive. There also exists Optional Chaining which are used on values to determine if they can be nil or not. This can be checked by using a check statement such as an if or if let to determine if there is a value or not. An Optional is depicted with a question mark behind it. If a programmer knows for sure that a value will not be nil then an exclamation point can be used afterwards to force unwrap it.

```Swift

var stuff: String?

if stuff != nil {
    print(Success)
} else {
    print(Unsuccessful)
}

```


##**Name spaces:**

Java:

Java files are usually organized into packages that each have their own distinct name. Packages are a collection of classes. Classes can share the name of another class in another package as each one can be differentiated because of the separate packages they belongs to.
Each of these classes has a simple name such as:
•    class.java
But also has a full name that incorporates the name of the package it belongs in:
•    packageA.class.java.
If packages themselves did not have unique names then we would not be able to differentiate between classes of the same name
EX.)

```Java
packageA.class.java
package.class.java
```
Swift:

Swift does not actually support namespaces in modules. There are ways around this. Two ways to make namespaces in Swift include utilizing structs or enums. For Structs, we can define an example struct called API:

```Swift
struct API {
    static let baseURL = "https://www.google.com"
    static let token = "abcdefghijklmnopqrstuvwxyz"    
}
```

When using the API struct, we can simply make a reference to it like so:

```Swift
if let url = URL(string: API.baseURL)
```

But if we do not want people to be able to make an instance of our struct, we can include a private initializer or private init to keep the contents inaccessible from other parts of the project

```Swift

struct API {
    
    private init() {}
    
    static let baseURL = "https://www.google.com"
    static let token = "abcdefghijklmnopqrstuvwxyz"
}

```


##**Types:**

Java:

- Booleans
- Bytes
- Char
- Short
- Int
- Long
- Float
- Double


Swift:

- Int
- Double
- Float
- Bool
- Character
- String


##**Classes:**

Java:

Classes always have their first letter capitalized to show that they are a class. Classes can be have tha control access modifiers of public, private, protected, or default and are used to add different functionality to an overall program. Objects are also made within classes with objects having different methods on them potentially. Constructors are used to help make an object. If one is not defined for a class then one is made by default in Java.

EX.)

```Java
public class Dog
{ 
    public Dog(String name) {
    // This constructor has one parameter, name.
    }
    void barking() {
        System.out.println("Bark");
    }
    void whimper() {
        System.out.println("Whimper");
    }

public class Cat {
    void catcall() {
        System.out.println("Meow");
    }
    void purr() {
        System.out.println("Purr");
    }
}
```
with both of these classes existing in a Dog.java and Cat.java files respectively.

Swift:

Classes always have their first letter capitalized to show that they are a class. They can:
- Define properties to store values
- Define methods to provide functionality
- Define subscripts to provide access to their values using subscript syntax
- Define initializers to set up their initial state
- Be extended to expand their functionality beyond a default implementation
- Conform to protocols to provide standard functionality of a certain kind
- Inheritance enables one class to inherit the characteristics of another.
- Type casting enables you to check and interpret the type of a class instance at runtime.
- Deinitializers enable an instance of a class to free up any resources it has assigned.
- Reference counting allows more than one reference to a class instance.

Example of a class in swift:

```Swift

class VideoMode {
    var interlaced = false
    var frameRate = 0.0
    var name: String?
}

```


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



## Listeners and Event Handlers

<div>
<div >
<h3 style="text-align:center">Java</h3>

```Java

ChangeListener<Number> lambdaChangeListener = (ObservableValue<? extends Number> observable, Number oldValue, final Number newValue) -> {
    handler();
};

```
* This is an example of a change listener from JavaFX, that will call some defined block of code any time there is a change in a number
* handler() is some function defined elsewhere that will do something in reaction to this change occurring
* This can then be registered on an Object that takes a ChangeListener as a parameter

</div>

<div >
<h3 style="text-align:center">Swift</h3>

```Swift

var num: Int = 0 {
    didSet {
        handler()
    }
}

```
* Swift variables have the ability to utilize built in value change listeners
* Whenever the num variable is set to a new value, the block of code in didSet will execute

</div>
</div>
<br>

## Singeltons

<div>
<div >
<h3 style="text-align:center">Java</h3>

```Java

public class Singleton {
    private Singleton() {}

    private static class SingletonHolder {
        private static final Singleton INSTANCE = new Singleton();
    }

    public static Singleton getInstance() {
        return SingletonHolder.INSTANCE;
    }
}

```

* Using an inner class to create an instance of the Singleton class is a method for lazy instantiation, as the inner class is referenced no earlier than when getInstance() is called 
* This method is also guaranteed to be thread safe, as the inner class is only created once

<br>


</div>


<div >
<h3 style="text-align:center">Swift</h3>

```Swift

class Singleton {
    static let sharedInstance = Singleton()
    private init(){}
}

```

* The default behavior of the Swift compiler will cause this to be lazily instantiated
* The let keyword ensures that this shared instance is thread safe

</div>
</div>
<br>


## Procedural Programming


* Since procedural programming is defined as a language that specifies a series of well-structured steps and procedures within its programming context to compose a program, both Swift and Java have the ability to perform procedural programming
* The procedures here can be defined as functions, and operations within those functions


<div>
<div>
<h3 style="text-align:center">Java</h3>

```Java

public int add() {
    int a = 1;
    a = a + 1;
    
    return a;
}

```
</div>


<div >
<h3 style="text-align:center">Swift</h3>

```Swift

func add() -> Int {
    var a = 1;
    a = a + 1;

    return a;
}

```
</div>
</div>
<br>


## Functional Programming

<div>
<div >
<h3 style="text-align:center">Java</h3>

```Java

@FunctionalInterface
interface MyString {
	String myStringFunction(String str);
}

public class functionalExample{

	public static String reverseStr(MyString reverse, String str){
  		return reverse.myStringFunction(str);
	}

	public static void main (String args[]) {
		MyString reverse = (str) -> {
			String result = "";
		
			for(int i = str.length()-1; i >= 0; i--){
				result += str.charAt(i);
			}
		
			return result;
		};

		System.out.println(reverseStr(reverse, "Functional Demo")); 
	}
}

```

* Here we define a lambda in Java through a Functional Interface that takes a string, and returns the reverse of that string
* Lambdas in Java could be considered a form of functional programming, because it allows you to define a block of code that can be passed around and reused
* Unlike traditional closures however, the only variables that can be included in this scope are final variables
* Functional languages such as Clojure or Scala can be implemented on top of a Java application to extend its functional programming capabilities

</div>


<div >
<h3 style="text-align:center">Swift</h3>

```Swift

let numbers = [1, 2, 3, 4, 5]
let evenNumbers = numbers.filter { $0 % 2 == 0 }

```

* This is a functional approach in that it takes a function as a parameter, or here a closure, and returns the result of applying that function to an immutable set of data
</div>
</div>
<br>


## Multithreading

<div>
<div >
<h3 style="text-align:center">Java</h3>

```Java

Thread counterThread = new Thread(() -> {
    int i = 0;
    
    while(true){
        System.out.println(i);
        i++;
    }
});
counterThread.start();

```

* This is an example of using a Thread lambda to start an infinite counter in a new thread
* Multiple instances or subclasses of Thread can be created and run from the main thread, allowing multiple tasks to be performed simultaneously

</div>


<div >
<h3 style="text-align:center">Swift</h3>

```Swift

DispatchQueue.main.async {
    var i = 0
    
    while(true){
        print(i)
        i += 1
    }
}

```

* In Swift, thread handling can be done by the system, so code to be executed in its own thread is run as a closure to DispatchQueue.main.async
* This can be done multiple times, allowing multiple tasks to run simultaneously

</div>
</div> 
