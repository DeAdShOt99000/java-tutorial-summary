# Java

Every line of code that runs in Java must be inside a class.

The name of the java file must match the class name.

remember that every Java program has a class name which must match the filename, and that every program must contain the main() method.

note that each code statement must end with a semicolon (;).

There is also a print() method, which is similar to println(),
The only difference is that it does not insert a new line at the end of the output.

You can also declare a variable without assigning the value, and assign the value later.

To declare more than one variable of the same type, you can use a comma-separated list:
```java
int x = 5, y = 6, z = 50;
```

You can also assign the same value to multiple variables in one line:
```java
int x, y, z;
x = y = z = 50;
```

---

**Data** types are divided into two groups:

**_Primitive data types_** - includes byte, short, int, long, float, double, boolean and char.

**_Non-primitive data types_** - such as String, Arrays and Classes.

**Long** number ends with *L*, **flaot** ends with *f* and **double** ends with *d*.

A floating point number can also be a scientific number with an **_e_** or **_E_** to indicate the power of **10**.

The **_char_** data type is used to store a single character. The character must be surrounded by **single** quotes.

Alternatively, if you are familiar with ASCII values, you can use those to display certain characters:
```java
char myVar1 = 65, myVar2 = 66, myVar3 = 67; // A, B, C
```

**_Non-primitive_** data types are called **_reference types_** because they *refer* to objects.

The main difference between **_primitive_** and **_non-primitive_** data types are:

- Primitive types are predefined (already defined) in Java. Non-primitive types are created by the programmer and is not defined by Java (except for String).
- Non-primitive types can be used to call methods to perform certain operations, while primitive types cannot.
- A primitive type has always a value, while non-primitive types can be null.
- A primitive type starts with a lowercase letter, while non-primitive types starts with an uppercase letter.

---

**_Type casting_** is when you assign a value of one primitive data type to another type.

In Java, there are two types of casting:

- **Widening Casting** (automatically) - converting a *smaller* type to a *larger* type size
  - `byte` -> `short` -> `char` -> `int` -> `long` -> `float` -> `double`

- **Narrowing Casting** (manually) - converting a *larger* type to a *smaller* size type
  - `double` -> `float` -> `long` -> `int` -> `char` -> `short` -> `byte`

**_Widening casting_** is done automatically when passing a smaller size type to a larger size type:
```java
public class Main {
  public static void main(String[] args) {
    int myInt = 9;
    double myDouble = myInt; // Automatic casting: int to double

    System.out.println(myInt);      // Outputs 9
    System.out.println(myDouble);   // Outputs 9.0
  }
}
```

**_Narrowing casting_** must be done manually by placing the type in parentheses in front of the value:
```java
public class Main {
  public static void main(String[] args) {
    double myDouble = 9.78d;
    int myInt = (int) myDouble; // Manual casting: double to int

    System.out.println(myDouble);   // Outputs 9.78
    System.out.println(myInt);      // Outputs 9
  }
}
```

---

A **_String_** in Java is actually an object, which contain *methods* that can perform certain operations on strings. For example, the length of a string can be found with the length() method. There are many string methods available, for example toUpperCase(), toLowerCase(), concat() and indexOf().

If you add a number and a string, the result will be a string concatenation.

W3Schools complete reference of String methods - [Java String Methods Reference](https://www.w3schools.com/java/java_ref_string.asp).

---

The Java **_Math_** class has many methods that allows you to perform mathematical tasks on numbers.

Some Math methods are: Math.max(x,y), Math.min(x,y), Math.sqrt(x), Math.abs(x), Math.random().

Math.random() returns a random number between 0.0 (inclusive), and 1.0 (exclusive).

To get more control over the random number, for example, if you only want a random number between 0 and 100, you can use the following formula:
```java
int randomNum = (int)(Math.random() * 101);  // 0 to 100
```
---

There is a "for-each" loop, which is used exclusively to loop through elements in an array:
```java
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
for (String i : cars) {
  System.out.println(i);
}
```

A **_multidimensional_** array is an array of arrays.

**_Multidimensional_** arrays are useful when you want to store data as a tabular form, like a table with rows and columns.

To create a two-dimensional array, add each array within its own set of curly braces:
```java
int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
```

We can also use a for loop inside another for loop to get the elements of a two-dimensional array (we still have to point to the two indexes):
```java
int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
for (int i = 0; i < myNumbers.length; ++i) {
    for(int j = 0; j < myNumbers[i].length; ++j) {
    System.out.println(myNumbers[i][j]);
    }
}
```
---

A **_method_** must be declared within a class. It is defined with the name of the method, followed by parentheses (). Java provides some pre-defined methods, such as System.out.println(), but you can also create your own methods to perform certain

The **_void_** keyword, used in the examples above, indicates that the method should not return a value. If you want the method to return a value, you can use a data type (such as int, char, String etc.) instead of void, and use the return keyword inside the method

With **_Method overloading_**, multiple methods can have the same name with different parameters.

In the example below, we overload the plusMethod method to work for both int and double:
```java
static int plusMethod(int x, int y) {
  return x + y;
}

static double plusMethod(double x, double y) {
  return x + y;
}

public static void main(String[] args) {
  int myNum1 = plusMethod(8, 5);
  double myNum2 = plusMethod(4.3, 6.26);
  System.out.println("int: " + myNum1);
  System.out.println("double: " + myNum2);
}
```

Multiple methods can have the same name as long as the number and/or type of parameters are different.

---

**_Procedural programming_** is about writing *procedures* or *methods* that perform operations on the *data*, while **_Object-oriented programming_** is about creating objects that contain both *data* and *methods*.

Everything in Java is associated with classes and objects.

You can also create an object of a class and access it in another class. This is often used for better organization of classes (one class has all the attributes and methods, while the other class holds the `main()` method (code to be executed))

class attributes(fields) are variables within a class

The `final` keyword is useful when you want a variable to always store the same value

`static` methods means that it can be accessed without creating an object of the class, unlike `public`, which can only be accessed by objects:
```java
public class Main {
  // Static method
  static void myStaticMethod() {
    System.out.println("Static methods can be called without creating objects");
  }

  // Public method
  public void myPublicMethod() {
    System.out.println("Public methods must be called by creating objects");
  }

  // Main method
  public static void main(String[] args) {
    myStaticMethod(); // Call the static method
    // myPublicMethod(); This would compile an error

    Main myObj = new Main(); // Create an object of Main
    myObj.myPublicMethod(); // Call the public method on the object
  }
}
```

--- 

The **constructor** name must match the class name, and it cannot have a return type (like void).

the **constructor** is called when the object is created.

All classes have constructors by default: if you do not create a class constructor yourself, Java creates one for you. However, then you are not able to set initial values for object attributes.

Constructors can also take parameters, which is used to initialize attributes.

```java
// Create a Main class
public class Main {
  int x;  // Create a class attribute

  // Create a class constructor for the Main class
  public Main() {
    x = 5;  // Set the initial value for the class attribute x
  }

  public static void main(String[] args) {
    Main myObj = new Main(); // Create an object of class Main (This will call the constructor)
    System.out.println(myObj.x); // Print the value of x
  }
}

// Outputs 5
```

---

We divide modifiers into two groups:

- **Access Modifiers** - controls the access level
- **Non-Access Modifiers** - do not control access level, but provides other functionality

**Access Modifiers**

For *classes*, you can use either `public` or default:

| Modifier | Description |
|:--------:|:-----------:|
| `public` | The class is accessible by any other class. |
| *default* | The class is only accessible by classes in the same package. This is used when you don't specify a modifier. |
  
For *attributes*, *methods* and *constructors*, you can use the one of the following:

| Modifier | Description |
|:--------:|:-----------:|
| `public` | The code is accessible for all classes. |
| `private` | The code is only accessible within the declared class. |
| `protected` |	The code is accessible in the same package and subclasses. |
| *default*	| The code is only accessible in the same package. This is used when you don't specify a modifier. |

**Non-Access Modifiers**

For *classes*, you can use either `final` or `abstract`:

| Modifier | Description |
|:--------:|:-----------:|
| `final` | The class cannot be inherited by other classes. |
| `abstract` | The class cannot be used to create objects (To access an abstract class, it must be inherited from another class).	|

For *attributes* and *methods*, you can use the one of the following:

| Modifier | Description |
|:--------:|:-----------:|
| `final` | Attributes and methods cannot be overridden/modified |
| `static` | Attributes and methods belongs to the class, rather than an object. A static method can be accessed without creating an object of the class. |
| `abstract` | Can only be used in an abstract class, and can only be used on methods. The method does not have a body, for example abstract void run();. The body is provided by the subclass (inherited from). |
| `transient` |	Attributes and methods are skipped when serializing the object containing them |
| `synchronized` | Methods can only be accessed by one thread at a time |
| `volatile` | The value of an attribute is not cached thread-locally, and is always read from the "main memory" |

---

The meaning of **Encapsulation**, is to make sure that "sensitive" data is hidden from users. To achieve this, you must:

- declare class variables/attributes as `private`
- provide public *get* and *set* methods to access and update the value of a private variable

Syntax for both is that they start with either **get** or **set**, followed by the name of the variable, with the first letter in upper case:
```java
public class Person {
  private String name; // private = restricted access

  // Getter
  public String getName() {
    return name;
  }

  // Setter
  public void setName(String newName) {
    this.name = newName;
  }
}
```
Class attributes can be made **read-only** (if you only use the get method), or **write-only** (if you only use the set method)

----

A **package** in Java is used to group related *classes*. Think of it as a folder in a file directory. We use packages to avoid name conflicts, and to write a better maintainable code. Packages are divided into two categories:
- **Built-in** Packages (packages from the Java API)
- **User-defined** Packages (create your own packages)

## Built-in Packages
The Java API is a library of prewritten classes, that are free to use, included in the Java Development Environment.

The library contains components for managing input, database programming, and much much more. The complete list can be found at [Oracles website](https://docs.oracle.com/javase/8/docs/api/).

The library is divided into *packages* and *classes*. Meaning you can either import a single class (along with its methods and attributes), or a whole package that contain all the classes that belong to the specified package.

To use a class or a package from the library, you need to use the import keyword:
```java
import package.name.Class;   // Import a single class
import package.name.*;   // Import the whole package
```

To create a package, use the package keyword:
```java
package mypack;

class MyPackageClass {
  public static void main(String[] args) {
    System.out.println("This is my package!");
  }
}
```
---

To inherit from a class, use the `extends` keyword.

In the example below, the `Car` class (subclass) inherits the *attributes* and *methods* from the `Vehicle` class (superclass):
```java
class Vehicle {
  protected String brand = "Ford";        // Vehicle attribute
  public void honk() {                    // Vehicle method
    System.out.println("Tuut, tuut!");
  }
}

class Car extends Vehicle {
  private String modelName = "Mustang";    // Car attribute
  public static void main(String[] args) {

    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (from the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand attribute (from the Vehicle class) and the value of the modelName from the Car class
    System.out.println(myCar.brand + " " + myCar.modelName);
  }
}
```

We set the `brand` attribute in `Vehicle` to a `protected` access modifier. If it was set to `private`, the `Car` class would not be able to access it.

---

**Polymorphism** means "many forms", and it occurs when we have many classes that are related to each other by **inheritance**.

**Inheritance** lets us *inherit* attributes and methods from another class. **Polymorphism** uses those methods to perform different tasks. This allows us to perform a single action in different ways.

For example, think of a superclass called `Animal` that has a method called `animalSound()`. Subclasses of Animals could be `Pigs`, `Cats`, `Dogs`, `Birds` - And they also have their own implementation of an animal sound (the pig oinks, and the cat meows, etc.):
```java
// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Pig extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
}

class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig(); // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}
```

----

In Java, it is also possible to **nest classes** (a class within a class). The purpose of nested classes is to group classes that belong together, which makes your code more readable and maintainable.

To access the inner class, create an object of the outer class, and then create an object of the inner class:
```java
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
Unlike a "regular" class, an inner class can be `private` or `protected`. If you don't want outside objects to access the inner class, declare the class as private:
```java
class OuterClass {
  int x = 10;

  private class InnerClass {
    int y = 5;
  }
}

public class Main {
  public static void main(String[] args) {
    OuterClass myOuter = new OuterClass();
    OuterClass.InnerClass myInner = myOuter.new InnerClass(); // error
    System.out.println(myInner.y + myOuter.x);
  }
}
```

An inner class can also be `static`, which means that you can access it without creating an object of the outer class.

just like `static` attributes and methods, a `static` inner class does not have access to members of the outer class.

One advantage of inner classes, is that they can access attributes and methods of the outer class.

---

**Data abstraction** is the process of hiding certain details and showing only essential information to the user.
Abstraction can be achieved with either **abstract classes** or **interfaces**.

The `abstract` keyword is a non-access modifier, used for classes and methods:

- **Abstract class**: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).

- **Abstract method**: can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from).

An abstract class can have both abstract and regular methods.

---

Another way to achieve abstraction in Java, is with **interfaces**.

An **interface** is a completely "abstract class" that is used to group related *methods* with empty bodies:
```java
// interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void run(); // interface method (does not have a body)
}
```

To access the interface methods, the interface must be "**implemented**" (kinda like inherited) by another class with the implements keyword (instead of extends). The body of the interface method is provided by the "**implement**" class:
```java
// Interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}

// Pig "implements" the Animal interface
class Pig implements Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}

class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig();  // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}
```

- Like abstract classes, interfaces cannot be used to create objects (in the example above, it is not possible to create an "Animal" object in the MyMainClass)
- Interface methods do not have a body - the body is provided by the "**implement**" class
- On implementation of an interface, you must override all of its methods.
- Interface methods are by default `abstract` and `public`.
- Interface attributes are by default `public`, `static` and `final`.
- An interface cannot contain a *constructor* (as it cannot be used to create objects).
- Java does not support "**multiple inheritance**" (a class can only inherit from one superclass). However, it can be achieved with interfaces, because the class can implement multiple interfaces. Note: To implement multiple interfaces, separate them with a comma.

To implement multiple interfaces, separate them with a comma:
```java
interface FirstInterface {
  public void myMethod(); // interface method
}

interface SecondInterface {
  public void myOtherMethod(); // interface method
}

class DemoClass implements FirstInterface, SecondInterface {
  public void myMethod() {
    System.out.println("Some text..");
  }
  public void myOtherMethod() {
    System.out.println("Some other text...");
  }
}

class Main {
  public static void main(String[] args) {
    DemoClass myObj = new DemoClass();
    myObj.myMethod();
    myObj.myOtherMethod();
  }
}
```
---

**Enum** is short for "enumerations", which means "specifically listed".

An **enum** is a special "class" that represents a group of constants (unchangeable variables, like `final` variables).

To create an enum, use the enum keyword (instead of class or interface), and separate the constants with a comma. Note that they should be in uppercase letters:
```java
enum Level {
  LOW,
  MEDIUM,
  HIGH
}
```

You can also have an enum inside a class:
```java
public class Main {
  enum Level {
    LOW,
    MEDIUM,
    HIGH
  }

  public static void main(String[] args) {
    Level myVar = Level.MEDIUM; 
    System.out.println(myVar);
  }
}
```

Enums are often used in switch statements to check for corresponding values:
```java
enum Level {
  LOW,
  MEDIUM,
  HIGH
}

public class Main {
  public static void main(String[] args) {
    Level myVar = Level.MEDIUM;

    switch(myVar) {
      case LOW:
        System.out.println("Low level");
        break;
      case MEDIUM:
         System.out.println("Medium level");
        break;
      case HIGH:
        System.out.println("High level");
        break;
    }
  }
}
```

The enum type has a `values()` method, which returns an array of all enum constants. This method is useful when you want to loop through the constants of an enum:
```java
for (Level myVar : Level.values()) {
  System.out.println(myVar);
}
```

An `enum` can, just like a `class`, have attributes and methods. The only difference is that enum constants are `public`, `static` and `final` (unchangeable - cannot be overridden).

An `enum` cannot be used to create objects, and it cannot extend other classes (but it can implement interfaces).

Use enums when you have values that you know aren't going to change, like month days, days, colors, deck of cards, etc.

---

The `Scanner` class is used to get user input, and it is found in the `java.util` package.

To use the `Scanner` class, create an object of the class and use any of the available methods found in the `Scanner` class documentation. In our example, we will use the `nextLine()` method (for reading strings), which is used to read Strings:
```java
import java.util.Scanner;  // Import the Scanner class

class Main {
  public static void main(String[] args) {
    Scanner myObj = new Scanner(System.in);  // Create a Scanner object
    System.out.println("Enter username");

    String userName = myObj.nextLine();  // Read user input
    System.out.println("Username is: " + userName);  // Output user input
  }
}
```

To read other types, look at the table below:
| Method | Description |
| ------ | ----------- |
| `nextBoolean()` |	Reads a `boolean` value from the user |
| `nextByte()` | Reads a `byte` value from the user |
| `nextDouble()` | Reads a `double` value from the user |
| `nextFloat()` | Reads a `float` value from the user |
| `nextInt()` | Reads a `int` value from the user |
| `nextLine()` | Reads a `String` value from the user |
| `nextLong()` | Reads a `long` value from the user |
| `nextShort()` |	Reads a `short` value from the user |

If you enter wrong input (e.g. text in a numerical input), you will get an exception/error message (like "InputMismatchException").

---

Java does not have a built-in Date class, but we can import the `java.time` package to work with the date and time API. The package includes many date and time classes. For example:

| Class |	Description |
| ----- | ----------- |
| `LocalDate` |	Represents a date (year, month, day (yyyy-MM-dd)) |
| `LocalTime` |	Represents a time (hour, minute, second and nanoseconds (HH-mm-ss-ns)) |
| `LocalDateTime` |	Represents both a date and a time (yyyy-MM-dd-HH-mm-ss-ns) |
| `DateTimeFormatter` |	Formatter for displaying and parsing date-time objects |

```java
import java.time.LocalDateTime; // Import the LocalDateTime class
import java.time.format.DateTimeFormatter; // Import the DateTimeFormatter class

public class Main {
  public static void main(String[] args) {
    LocalDateTime myDateObj = LocalDateTime.now();
    System.out.println("Before formatting: " + myDateObj);
    DateTimeFormatter myFormatObj = DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");

    String formattedDate = myDateObj.format(myFormatObj);
    System.out.println("After formatting: " + formattedDate);
  }
}
```

The `ofPattern()` method accepts all sorts of values, if you want to display the date and time in a different format. For example:
| Value |	Example|
| ----- | ------ |
| `yyyy-MM-dd` | "1988-09-29"	|
| `dd/MM/yyyy` | "29/09/1988"	|
| `dd-MMM-yyyy` |	"29-Sep-1988"	|
| `E, MMM dd yyyy` | "Thu, Sep 29 1988" |

---

The `ArrayList` class is a resizable array, which can be found in the `java.util` package.

The difference between a built-in array and an `ArrayList` in Java, is that the size of an array cannot be modified (if you want to add or remove elements to/from an array, you have to create a new one). While elements can be added and removed from an `ArrayList` whenever you want. The syntax is also slightly different:
```java
import java.util.ArrayList; // import the ArrayList class

ArrayList<String> cars = new ArrayList<String>(); // Create an ArrayList object
```

Some of `ArrayList` methods are: `add()`, `get()`, `set()`, `remove()`, `clear()`, `size()`

Elements in an ArrayList are actually objects. In the examples above, we created elements (objects) of type "String". Remember that a String in Java is an object (not a primitive type). To use other types, such as int, you must specify an equivalent wrapper class: `Integer`. For other primitive types, use: `Boolean` for boolean, `Character` for char, `Double` for double, etc:
```java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> myNumbers = new ArrayList<Integer>();
    myNumbers.add(10);
    myNumbers.add(15);
    myNumbers.add(20);
    myNumbers.add(25);
    for (int i : myNumbers) {
      System.out.println(i);
    }
  }
}
```

Another useful class in the `java.util` package is the `Collections` class, which include the `sort()` method for sorting lists alphabetically or numerically:
```java
import java.util.ArrayList;
import java.util.Collections;  // Import the Collections class

public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    Collections.sort(cars);  // Sort cars
    for (String i : cars) {
      System.out.println(i);
    }
  }
}
```

---

The `LinkedList` class is a collection which can contain many objects of the same type, just like the `ArrayList`.

The `LinkedList` class has all of the same methods as the `ArrayList` class because they both implement the `List` interface. This means that you can add items, change items, remove items and clear the list in the same way.

However, while the `ArrayList` class and the `LinkedList` class can be used in the same way, they are built very differently.

The `ArrayList` class has a regular *array* inside it. When an element is added, it is placed into the array. If the array is not big enough, a new, larger array is created to replace the old one and the old one is removed.

The `LinkedList` stores its items in "**containers**". The list has a *link* to the first container and each container has a *link* to the next container in the list. To add an element to the list, the element is placed into a new container and that container is linked to one of the other containers in the list.

Use an `ArrayList` for storing and accessing data, and `LinkedList` to manipulate data.

For many cases, the `ArrayList` is more efficient as it is common to need access to random items in the list, but the `LinkedList` provides several methods to do certain operations more efficiently:

| Method | Description |
| ------ | ----------- |
| `addFirst()` |	Adds an item to the beginning of the list. |
| `addLast()` |	Add an item to the end of the list. |
| `removeFirst()` |	Remove an item from the beginning of the list. |
| `removeLast()` |	Remove an item from the end of the list. |
| `getFirst()` |	Get the item at the beginning of the list. |
| `getLast()` |	Get the item at the end of the list. |

---

A `HashMap` store items in "**key/value**" pairs, and you can access them by an index of another type (e.g. a String).

One object is used as a key (index) to another object (value). It can store different types: `String` keys and `Integer` values, or the same type, like: `String` keys and `String` values:
```java
import java.util.HashMap; // import the HashMap class

HashMap<String, String> capitalCities = new HashMap<String, String>();
```

Some of `HashMap` methods are: `put()`, `get()`, `remove()`, `clear()`, `size()`.

Loop through the items of a `HashMap` with a for-each loop.

Use the `keySet()` method if you only want the keys, and use the `values()` method if you only want the values:
```java
// Print keys
for (String i : capitalCities.keySet()) {
  System.out.println(i);
}
```

Keys and values in a `HashMap` are actually `objects`. In the examples above, we used objects of type `String`. Remember that a `String` in Java is an object (not a primitive type). To use other types, such as int, you must specify an equivalent wrapper class: `Integer`. For other primitive types, use: `Boolean` for boolean, `Character` for char, `Double` for double, etc.

---

A `HashSet` is a collection of items where every item is unique, and it is found in the `java.util` package:
```java
import java.util.HashSet; // Import the HashSet class

HashSet<String> cars = new HashSet<String>();
```

Some of `HashSet` methods are: `add()`, `contains()`, `remove()`, `clear()`, `size()`

Items in an `HashSet` are actually objects. In the examples above, we created items (objects) of type "String". Remember that a String in Java is an object (not a primitive type). To use other types, such as int, you must specify an equivalent wrapper class: `Integer`. For other primitive types, use: `Boolean` for boolean, `Character` for char, `Double` for double, etc:

---

An `Iterator` is an object that can be used to loop through **collections**, like `ArrayList` and `HashSet`. It is called an "iterator" because "iterating" is the technical term for looping.

To use an `Iterator`, you must import it from the `java.util` package.

The `iterator()` method can be used to get an `Iterator` for any collection:
```java
// Import the ArrayList class and the Iterator class
import java.util.ArrayList;
import java.util.Iterator;

public class Main {
  public static void main(String[] args) {

    // Make a collection
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");

    // Get the iterator
    Iterator<String> it = cars.iterator();

    // Print the first item
    System.out.println(it.next());
  }
}
```

To loop through a collection, use the `hasNext()` and `next()` methods of the `Iterator`.

`Iterators` are designed to easily change the collections that they loop through. The `remove()` method can remove items from a collection while looping:
```java
import java.util.ArrayList;
import java.util.Iterator;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(12);
    numbers.add(8);
    numbers.add(2);
    numbers.add(23);
    Iterator<Integer> it = numbers.iterator();
    while(it.hasNext()) {
      Integer i = it.next();
      if(i < 10) {
        it.remove(); // remove numbers less than 10 from a collection
      }
    }
    System.out.println(numbers);
  }
}
```

Trying to remove items using a **for** loop or a **for-each** loop would not work correctly because the collection is changing size at the same time that the code is trying to loop.

---

**Wrapper classes** provide a way to use primitive data types (`int`, `boolean`, etc..) as objects.
| Primitive Data Type |	Wrapper Class |
| ------------------- | ------------- |
| `byte` |	`Byte` |
| `short` |	`Short` |
| `int` |	`Integer` |
| `long` |	`Long` |
| `float` |	`Float` |
| `double` |	`Double` |
| `boolean` |	`Boolean` |
| `char` |	`Character` |

Since you're now working with objects, you can use certain methods to get information about the specific object.

For example, the following methods are used to get the value associated with the corresponding wrapper object: `intValue()`, `byteValue()`, `shortValue()`, `longValue()`, `floatValue()`, `doubleValue()`, `charValue()`, `booleanValue()`.

Another useful method is the `toString()` method, which is used to convert wrapper objects to strings.

In the following example, we convert an `Integer` to a `String`, and use the `length()` method of the `String` class to output the length of the "string":
```java
public class Main {
  public static void main(String[] args) {
    Integer myInt = 100;
    String myString = myInt.toString();
    System.out.println(myString.length());
  }
}
```

---

The `try` statement allows you to define a block of code to be tested for errors while it is being executed.

The `catch` statement allows you to define a block of code to be executed, if an error occurs in the `try` block.

The `try` and `catch` keywords come in pairs.

The `finally` statement lets you execute code, after `try...catch`, regardless of the result:
```java
public class Main {
  public static void main(String[] args) {
    try {
      int[] myNumbers = {1, 2, 3};
      System.out.println(myNumbers[10]);
    } catch (Exception e) {
      System.out.println("Something went wrong.");
    } finally {
      System.out.println("The 'try catch' is finished.");
    }
  }
}
```

The `throw` statement allows you to create a custom error.
The `throw` statement is used together with an exception type. There are many exception types available in Java: `ArithmeticException`, `FileNotFoundException`, `ArrayIndexOutOfBoundsException`, `SecurityException`, etc:
```java
public class Main {
  static void checkAge(int age) {
    if (age < 18) { // throw an exception if age is below 18
      throw new ArithmeticException("Access denied - You must be at least 18 years old.");
    }
    else {
      System.out.println("Access granted - You are old enough!");
    }
  }

  public static void main(String[] args) {
    checkAge(15); // Set age to 15 (which is below 18...)
  }
}
```

---

Java does not have a built-in Regular Expression class, but we can import the `java.util.regex` package to work with regular expressions. The package includes the following classes:
- `Pattern` Class - Defines a pattern (to be used in a search)
- `Matcher` Class - Used to search for the pattern
- `PatternSyntaxException` Class - Indicates syntax error in a regular expression pattern

---

There are two ways to create a thread.
- By extending the `Thread` class and overriding its `run()` method.
- By implementing the `Runnable` interface.

The major difference is that when a class extends the Thread class, you cannot extend any other class, but by implementing the Runnable interface, it is possible to extend from another class as well, like: `class MyClass extends OtherClass implements Runnable`.

Because threads run at the same time as other parts of the program, there is no way to know in which order the code will run. When the threads and main program are reading and writing the same variables, the values are unpredictable. The problems that result from this are called concurrency problems.

To avoid concurrency problems, it is best to share as few attributes between threads as possible. If attributes need to be shared, one possible solution is to use the `isAlive()` method of the thread to check whether the thread has finished running before using any attributes that the thread can change.

---

**Lambda Expressions** were added in Java 8.

A **lambda expression** is a short block of code which takes in parameters and returns a value. Lambda expressions are similar to *methods*, but they do not need a name and they can be implemented right in the body of a method.

The simplest lambda expression contains a single parameter and an expression, to use more than one parameter, wrap them in parentheses.

Expressions are limited. They have to immediately return a value, and they cannot contain variables, assignments or statements such as `if` or `for`. In order to do more complex operations, a code block can be used with curly braces. If the lambda expression needs to return a value, then the code block should have a `return` statement:
```java
parameter -> expression

(parameter1, parameter2) -> expression

(parameter1, parameter2) -> { code block }
```

Lambda expressions are usually passed as parameters to a function:
```java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(5);
    numbers.add(9);
    numbers.add(8);
    numbers.add(1);
    numbers.forEach( (n) -> { System.out.println(n); } );
  }
}
```

Lambda expressions can be stored in variables if the variable's type is an interface which has only one method. The lambda expression should have the same number of parameters and the same return type as that method. Java has many of these kinds of interfaces built in, such as the `Consumer` interface (found in the `java.util package`) used by lists.
```java
import java.util.ArrayList;
import java.util.function.Consumer;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(5);
    numbers.add(9);
    numbers.add(8);
    numbers.add(1);
    Consumer<Integer> method = (n) -> { System.out.println(n); };
    numbers.forEach( method );
  }
}
```

To use a lambda expression in a method, the method should have a parameter with a single-method interface as its type. Calling the interface's method will run the lambda expression:
```java
interface StringFunction {
  String run(String str);
}

public class Main {
  public static void main(String[] args) {
    StringFunction exclaim = (s) -> s + "!";
    StringFunction ask = (s) -> s + "?";
    printFormatted("Hello", exclaim);
    printFormatted("Hello", ask);
  }
  public static void printFormatted(String str, StringFunction format) {
    String result = format.run(str);
    System.out.println(result);
  }
}
```

---