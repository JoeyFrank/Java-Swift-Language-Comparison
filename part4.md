

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

public static String reverseStr(MyString reverse, String str){
  return reverse.myStringFunction(str);
}

public static void main (String args[]) {

	MyString reverse = (str) -> {
		String result = "";
		
		for(int i = str.length()-1; i >= 0; i--)
			result += str.charAt(i);
		
		return result;
	};

	System.out.println(reverseStr(reverse, "Lambda Demo")); 
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