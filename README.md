# Java-Swift-Language-Comparison
A comparison between the Swift and Java object oriented programming languages


Language purpose/genesis  
Unique features of the language  
Name spaces  
Types  
Classes  

Instance reference name in data type (class)  
Properties  
Interfaces / protocols  
Inheritance / extension  
Reflection  

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
a.equals(b) will return true;<br />
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

Lambda expressions, closures, or functions as types  

Implementation of listeners and event handlers  
Singleton  
Procedural programming  
Functional programming  
Multithreading  
