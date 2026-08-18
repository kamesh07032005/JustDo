Day -1
Chapter 1
	Introduction to Java, Data Types and Variables
	History & Features of Java:
	 OOP, platform independence, JVM, JDK, JRE
	Data Types:
	 Primitive and non-primitive types, Variable declaration, Type casting
Chapter 2
	OOP Basics
	Object-Oriented Principles:
	Encapsulation, Inheritance, Polymorphism, Abstraction
	Classes and Objects:
	Class structure, Object creation, Instance variables
	Constructors: Default constructor, Parameterized constructor,
	Constructor overloading
Chapter 3
	Inheritance, Abstraction & Encapsulation
o	Inheritance: 
	Single inheritance, Multilevel inheritance, super keyword
o	Polymorphism: 
	Method overloading, Method overriding
o	Abstraction: 
	Abstract classes, Interfaces
o	Encapsulation: 
	Access modifiers (public, private, protected), Encapsulating data









1. What is Java?
Java is a high-level, object-oriented programming language developed by Sun Microsystems (now Oracle).
2. History & Features of Java
OOP (Object-Oriented Programming)
Java organizes programs using objects and classes.
Example:
•	Customer
•	Account
•	Transaction
Each can be represented as an object

3. Why Platform Independence?
Write Once, Run Anywhere (WORA)
Write code once and run it on Windows, Linux, Mac
Java code → Bytecode → JVM executes it.
4. JVM (Java Virtual Machine)
Runs Java bytecode.
Think of JVM as a translator.
Java Code
    ↓
Compiler
    ↓
Bytecode
    ↓
JVM
    ↓
Machine Code
JRE (Java Runtime Environment)
Contains JVM, required libraries Used only to run Java programs.
JDK (Java Development Kit)
Contains JRE, Compiler (javac), Development tools, used to develop Java applications.
5. Primitive Data Types: byte, short, int, long, float, double, char, Boolean .
     Non-Primitive Data Types: String, Arrays, Class, Interface, Enum, Object, Wrapper Classes (Integer, Double, Boolean, Character, etc.)
6.Type casting : Converting one data type into another.
Implicit casting/widening
•	Conversion of Small datatype to Large datatype
•	No data loss
byte → short → int → long → float → double
 int num = 100;
 double d = num; // int to double (automatic)
Explicit Casting/Narrowing
•	Converts a larger data type to a smaller data type.
•	May cause data loss
•	Must be done manually using (type) syntax.
double d = 99.99;
 int num = (int) d;

Chapter 2: OOP Basics
7. What is OOP?
OOP means organizing code using objects that contain data and method(behaviour) . It is a real world entity
Benefits-Reusability, Security, Maintainability, Scalability
Four pillars : Encapsulation, Polymorphism , Inheritance, Abstraction
Class : Class is the template or blueprint defining the structure and behaviour of objects.
Object: An Object in Java is an instance of a class that represents a real-world entity. It is used to access the variables and methods defined inside a class.
 
8. Encapsulation
	Wrapping data and methods together.
	Steps 1: Declare variables as private.
	Steps 2: Provide the public getter and setter .
class Employee {
private int salary;
public void setSalary(int salary) {
this.salary = salary;
}
public int getSalary () {
return salary;
}
}
9.Inheritance
Inheritance allows one class to acquire properties and methods of another class.
	
Real Project
E-commerce Application
Parent: 
	All products have some common properties:
Product Name
Price
Brand
Display Details()

Without inheritance:
Mobile -> productName, price, brand
Laptop -> productName, price, brand
TV -> productName, price, brand



// Parent Class
class Product {
    String productName;
    double price;
    String brand;
    Product(String productName, double price, String brand) {
        this.productName = productName;
        this.price = price;
        this.brand = brand;
    }
    void displayDetails() {
        System.out.println("Product Name : " + productName);
        System.out.println("Price        : " + price);
        System.out.println("Brand        : " + brand);
    }
}
// Child Class - Mobile
class Mobile extends Product {
    int ram;
    int storage;
    Mobile(String productName, double price, String brand,
        int ram, int storage) {

        super(productName, price, brand);

        this.ram = ram;
        this.storage = storage;
    }

    void displayMobileDetails() {
        displayDetails();
        System.out.println("RAM          : " + ram + " GB");
        System.out.println("Storage      : " + storage + " GB");
    }
}

// Child Class - Laptop
class Laptop extends Product {
    String processor;
    int ram;
    Laptop(String productName, double price, String brand,
        String processor, int ram) {
        super(productName, price, brand);
        this.processor = processor;
        this.ram = ram;
    }
    void displayLaptopDetails() {
        displayDetails();
        System.out.println("Processor    : " + processor);
        System.out.println("RAM          : " + ram + " GB");
    }
}
// Child Class - TV
class TV extends Product {
    int screenSize;
    String resolution;

    TV(String productName, double price, String brand,
        int screenSize, String resolution) {
        super(productName, price, brand);
        this.screenSize = screenSize;
        this.resolution = resolution;
    }

    void displayTVDetails() {
        displayDetails();
        System.out.println("Screen Size  : " + screenSize + " Inches");
        System.out.println("Resolution   : " + resolution);
    }
}
// Main Class
public class EcommerceApp {
    public static void main(String[] args) {
        Mobile mobile =
            new Mobile("iPhone 16", 85000,
                "Apple", 8, 256);
        Laptop laptop =
            new Laptop("ThinkPad", 75000,
                "Lenovo", "Intel i7", 16);
        TV tv =
            new TV("Bravia", 65000,
                "Sony", 55, "4K");
        System.out.println("=== MOBILE DETAILS ===");
        mobile.displayMobileDetails();
        System.out.println("\n=== LAPTOP DETAILS ===");
        laptop.displayLaptopDetails();

        System.out.println("\n=== TV DETAILS ===");
        tv.displayTVDetails();
    }
}



10.Instance Variables
•	An instance variable is a non-static variable defined within a class but outside any method
class Employee {
int empId;
String empName;
}

Constructors
Special method called automatically during object creation.
Types
Default constructor
class Employee {
Employee () {
System.out.println("Employee Created");
}
}
Parameterized Constructor
class Employee {
Employee(int id) {
System.out.println(id);
}
}	
Constructor Overloading
class Employee {
Employee () {
}
Employee (int id) {
}
Employee (int id, String name) {
}
}
Employee e1 = new Employee();
Employee e2 = new Employee(101);
Employee e3 = new Employee(101,"Kamesh");
Chapter 3
What is Inheritance?
Inheritance allows one class to acquire properties and methods of another class.
Single , Multiple , Hybrid, Multilevel, Hierarchical.
A. Single Inheritance
One child inherits from one parent.
class Employee {
    void login() {
        System.out.println("Login");
    }
}
class Developer extends Employee {
    void writeCode() {
        System.out.println("Writing Code");
    }
}
B. Multilevel Inheritance
   
class Employee {
}
class Developer extends Employee {
}
class JavaDeveloper extends Developer {
}
class Vehicle {
    Vehicle() {
        System.out.println("This is a Vehicle");
    }
}
class FourWheeler extends Vehicle {
    FourWheeler() {
        System.out.println("4 Wheeler Vehicles");
    }
}
class Car extends FourWheeler {
    Car() {
        System.out.println("This 4 Wheeler Vehicle is a Car");
    }
}
public class Geeks {
    public static void main(String[] args) {
        Car obj = new Car(); // Triggers all constructors in order
    }
}
OUTPUT
This is a Vehicle
4 Wheeler Vehicles
This 4 Wheeler Vehicle is a Car
3. Hierarchical Inheritance
 
class Vehicle {
    Vehicle () {
        System.out.println("This is a Vehicle");
    }
}
class Car extends Vehicle {
    Car () {
        System.out.println("This Vehicle is Car");
    }
}
class Bus extends Vehicle {
    Bus () {
        System.out.println("This Vehicle is Bus");
    }
}
public class Test {
    public static void main (String[] args) {
        Car obj1 = new Car (); 
        Bus obj2 = new Bus (); 
    }
}
4. Multiple Inheritance
 Note: that Java does not support multiple inheritances with classes. In Java, we can achieve multiple inheritances only through Interfaces.
interface LandVehicle {
    default void landInfo() {
        System.out.println("This is a LandVehicle");
    }
}
interface WaterVehicle {
    default void waterInfo() {
        System.out.println("This is a WaterVehicle");
    }
}
// Subclass implementing both interfaces
class AmphibiousVehicle implements LandVehicle, WaterVehicle {
    AmphibiousVehicle() {
        System.out.println("This is an AmphibiousVehicle");
    }
}
public class Test {
    public static void main(String[] args) {
        AmphibiousVehicle obj = new AmphibiousVehicle();
        obj.waterInfo();
        obj.landInfo();
    }
}

5. Hybrid Inheritance
 
// Superclass
class Vehicle {
    void vehicleType() {
        System.out.println("This is a Vehicle");
    }
}

// Interface for fare
interface Fare {
    default void fareInfo() {
        System.out.println("Fare information");
    }
}

// Subclass 1: Single inheritance + multilevel
class Car extends Vehicle {
    void carType() {
        System.out.println("This is a Car");
    }
}

// Subclass 2: Hybrid inheritance (extends class + implements interface)
class Bus extends Vehicle implements Fare {
    void busType() {
        System.out.println("This is a Bus");
    }
}

public class GFG{
    public static void main(String[] args) {
        Car car = new Car();
        car.vehicleType(); // inherited from Vehicle
        car.carType();     // specific to Car

        Bus bus = new Bus();
        bus.vehicleType(); // inherited from Vehicle
        bus.busType();     // specific to Bus
        bus.fareInfo();    // from Fare interface
    }
}

2. Polymorphism
 	->It allows single entity to take multiple forms.
->Polymorphism means "many forms".

Method Overloading / Compile-Time Polymorphism / Static polymorphism
Same method name, different parameters.
class Calculator {
void add (int a, int b) {
System.out.println(a + b);
}
void add (int a, int b, int c) {
System.out.println(a + b + c);
}
}
Method Overriding / Run-Time Polymorphism/ Dynamic Polymorphism
Different class, same method name , same parameter.
class Parent {
	void Print() {
		System.out.println("parent class");
	}
}
class Subclass1 extends Parent {
	void Print() {
		System.out.println("subclass1");
	}
}

class Subclass2 extends Parent {
	void Print() {
		System.out.println("subclass2");
	}
}

class Main {
	public static void main(String[] args)
	{
		Parent a;
		a = new Subclass1();
		a.Print(); //OUTPUT:subclass1
		a = new Subclass2();//OUTPUT:subclass1
		a.Print();
	}
}
4.Abstraction
Hiding implementation and providing only essential details. 
Abstract class
•	Cannot able to create the object
•	Contain methods without body (abstract method )and with body(concrete method)
•	Must Override all the parent abstract method in the child class 
 
•	Abstract Classes (Partial Abstraction)
•	Interface (Full Abstraction)
abstract class TV {
	abstract void turnOn();
	abstract void turnOff();
}
class TVRemote extends TV {
	@Override
	void turnOn() {
		System.out.println("TV is turned ON.");
	}
	@Override
	void turnOff() {
		System.out.println("TV is turned OFF.");
	}
}
public class Geeks {
	public static void main(String[] args) {
		TV remote = new TVRemote();
		remote.turnOn();
		remote.turnOff();
	}
}

Interface
•	An interface is a blueprint for a class that defines a set of methods a class must implement
•	It helps to achieve 100% abstraction
interface Shape{
    double calculateArea(); 
}
class Circle implements Shape{
    private double r;
    public Circle(double r){ 
      this.r = r; 
    }
    public double calculateArea()
    {
        return Math.PI * r * r;
    }
}
class Rectangle implements Shape{
    private double length;
    private double width;
    public Rectangle(double length, double width){
        this.length = length;
        this.width = width;
    }
    public double calculateArea() { 
      return length * width; 
    }
}
public class Main {
    public static void main(String[] args) {
        Shape cir = new Circle(5.0);
        Shape rect = new Rectangle(4.0, 6.0);
        System.out.println("Area of Circle: " + cir.calculateArea());
        System.out.println("Area of Rectangle: " + rect.calculateArea());
    }
}
Output
Area of Circle: 78.53981633974483
Area of Rectangle: 24.0
5,Encapsulation
It means wrapping data (fields) and methods (functions) into a single unit (class).
•	Declare variables as the private.
•	Provide Public getter and setter methods to access the variables.
class Programmer {
    private String name;
    public String getName() { return name; }
    public void setName(String name) {
        this.name = name;
    }
}

public class Geeks {
    public static void main(String[] args){
        Programmer p = new Programmer();
        p.setName("Geek");
        System.out.println("Name=> " + p.getName());
    }
}
ACCESS MODIFIER
Access Modifier	Same Class	Same Package	Subclass	Other Packages
public	Yes	Yes	Yes	Yes
protected	Yes	Yes	Yes	No*
private	Yes	No	No	No












Day -2
Chapter 4
	Keywords
	this and super: 
	Referring current object, Accessing parent class methods.
	Static Members:
	 Static variables, Static methods, Static blocks
	final Keyword:
	 Final variables, Final methods, Final classes
	Arrays,Strings,StringBuffer& StringBuilder
	Arrays
	One-dimensional array, Multidimensional array, Array traversal and operations
	Strings
	String class, Immutability, String methods: length, substring,equals, etc.
1.this
this refers to the current object of the class.
1. Differentiate Instance Variables and Local Variables
class Student {
String name;
Student(String name) {
this.name = name; // instance variable = local variable
}
}
2. Call Another Constructor in the Same Class
class Student {
String name;
int age;
Student () {
this ("John", 20);
}
Student (String name, int age) {
this.name = name;
this.age = age;
}
}
this() must be the first statement in the constructor.
super Keyword
super refers to the immediate parent class object.
class Parent {
int value = 10;
}

class Child extends Parent {
int value = 20;

void display() {
System.out.println(value); // 20
System.out.println(super.value); // 10
}
}
2. Call Parent Class Method
class Parent {
    void show() {
        System.out.println("Parent Method");
    }
}
class Child extends Parent {
    void show() {
        System.out.println("Child Method");
    }
    void display() {
        super.show();
    }
}

3. Call Parent Class Constructor
class Parent {
Parent() {
System.out.println("Parent Constructor");
}
}
class Child extends Parent {
Child() {
super();
System.out.println("Child Constructor");
}
}
Can we use both this() and super() in the same constructor?
We cannot have them together in the same constructor as both need to be the first statement in the block for proper execution.

2.Static members
1. Static Variables
A static variable is shared among all objects of a class. Only one copy of the variable exists in memory, regardless of how many objects are created.
class Employee {
    int empId;
    String name;
    static String company = "Cognizant";
    Employee(int empId, String name) {
        this.empId = empId;
        this.name = name;
    }
    void display() {
        System.out.println(empId + " " + name + " " + company);
    }
    public static void main(String[] args) {
        Employee e1 = new Employee(101, "John");
        Employee e2 = new Employee(102, "David");
        e1.display();
        e2.display();
    }
}

Employee Class
--------------------------------
company = "Cognizant" <-- One copy
Object e1
----------
empId = 101
name = John
Object e2
----------
empId = 102
name = David
2. Static Methods
A static method belongs to the class rather than an object.
class Calculation {
	static int cube(int x) {
		return x * x * x;
	}
	public static void main(String[] args) {
		int result = Calculation.cube(5);
		System.out.println(result);
	}
}


1. Can Access Static Members Directly
class Test {
    static int x = 10;
    static void display() {
        System.out.println(x);
    }
}
2. Cannot Access Non-Static Members Directly
class Test {
    int y = 20;
    static void display() {
        // System.out.println(y); // Error
    }
}
3. Cannot Use this Keyword
static void display() {
// System.out.println(this); // Error
}
4.No need to create a object.
3. Static Blocks
A static block is used to initialize static variables.
It executes only once, when the class is loaded into memory.
class Demo {
    static {
        System.out.println("Static Block 1");
    }
    static {
        System.out.println("Static Block 2");
    }
    public static void main(String[] args) {
        System.out.println("Main Method");
    }
}
Static Block 1
Static Block 2
Main Method

1. Final Variables
A final variable cannot be reassigned once a value is assigned to it.
2. Final class
A final class cannot be inherited.
3. Final Method.
can be inherited but cannot be overridden by subclasses.
public class FinalExample {
    public static final double PI = 3.14159;
    public final void displayMessage() {
        System.out.println("This is a final method.");
    }
    public static void main(String[] args) {
        System.out.println("Value of PI: " + PI);
        FinalExample obj = new FinalExample();
        obj.displayMessage();
    }
}
// A class that tries to extend FinalExample
class ChildClass extends FinalExample {
    // ❌ This will cause a compile-time error because displayMessage() is final
    /*
    @Override
    public void displayMessage() {
        System.out.println("Trying to override final method.");
    }
    */
}
 

Topic	String	StringBuffer	StringBuilder
Meaning	Represents a fixed sequence of characters	Represents a changeable sequence of characters	Represents a changeable sequence of characters
Mutability	Immutable	Mutable	Mutable
After modification	Creates a new String object	Modifies the same object	Modifies the same object
Thread safety	Safe to share because its content cannot change	Thread-safe for individual operations	Not inherently thread-safe
Synchronization	Not required due to immutability	Methods are synchronized	Methods are not synchronized
Performance for repeated changes	Usually slower because many temporary objects may be created	Faster than repeated String modification, but synchronization adds overhead	Usually fastest for repeated text modification
Memory use during repeated modification	May use more memory due to temporary objects	Reuses an internal character sequence	Reuses an internal character sequence
Introduced in	Java 1.0	Java 1.0	Java 5
Creation example	String text = "Java";	StringBuffer text = new StringBuffer("Java");	StringBuilder text = new StringBuilder("Java");
append(value)	Not available. Use concatenation or concat()	Adds a value to the end of the same object	Adds a value to the end of the same object
Append example result	"Java" + " Programming" produces "Java Programming" as a new String	Appending " Programming" changes the content to "Java Programming"	Appending " Programming" changes the content to "Java Programming"
insert(index, value)	Not available	Inserts content before the specified index	Inserts content before the specified index
Insert example result	A new string must be constructed manually	Inserting "Core " at index 5 in "Java Programming" produces "Java Core Programming"	Inserting "Core " at index 5 in "Java Programming" produces "Java Core Programming"
Valid index for insert()	Not applicable	From 0 through length()	From 0 through length()
delete(start, end)	Not available	Deletes a range from the same object	Deletes a range from the same object
Delete index rule	Not applicable	Start index included, end index excluded	Start index included, end index excluded
Delete example result	A new string must be constructed manually	Deleting indexes 5 through 9 from "Java Core Programming" produces "Java Programming"	Deleting indexes 5 through 9 from "Java Core Programming" produces "Java Programming"
deleteCharAt(index)	Not available	Deletes one character at the specified index	Deletes one character at the specified index
replace(start, end, value)	replace() returns a new String	Replaces a range in the same object	Replaces a range in the same object
reverse()	Not available	Reverses the same character sequence	Reverses the same character sequence
charAt(index)	Returns the character at an index	Returns the character at an index	Returns the character at an index
setCharAt(index, char)	Not available	Changes one character in the same object	Changes one character in the same object
length()	Returns the number of characters	Returns the number of characters	Returns the number of characters
capacity()	Not available	Returns current internal storage capacity	Returns current internal storage capacity
substring()	Returns a new String	Returns part of the content as a String	Returns part of the content as a String
toString()	Returns the string itself	Converts the final content into a String	Converts the final content into a String
Method chaining	Limited because modification methods return new strings	Supported for methods such as append(), insert(), and delete()	Supported for methods such as append(), insert(), and delete()
Content comparison	Use equals()	Convert to String and use equals(), or use compareTo() where supported	Convert to String and use equals(), or use compareTo()
Best use	Fixed or rarely changing text	Mutable text shared and modified by multiple threads	Repeated text construction in ordinary or single-threaded code
Common example	Names, messages, constants, map keys	Shared log or text buffer requiring synchronized operations	Building reports, SQL, CSV data, or text inside loops
Recommended choice	Use when text does not require repeated modification	Use only when synchronized mutable text is genuinely required	Preferred for most repeated string-modification operations






Checked Exceptions
It is verified by the compiler at the compile time.
eg:IOException, FileNotFoundException.
Unchecked Exceptions
It occurs during the program execution and not checked by the compiler
eg: ArithmeticException, NullPointerException.
Throw
it manually creates and throws an exception.
Throws 
it telling method it may pass this error
Exception Propagation
It means passing an exception from one method to the method .
 
 
 
CUSTOM exception
Custom exception is the user defined exception created by extending Exception or runtime Exception class to represent the particular application specific error condition.




Class InvalidAge extends Exception {
    public InvalidAge(String msg) {
        super(msg);
    }
}
 
class Custom {
    static void register(int age) throws InvalidAge {
        if (age < 18) {
            throw new InvalidAge("Minimum age required is 18");
        } else {
            System.out.println("Registered");
        }
    }
}
 
public class Main {
    public static void main(String[] args) {
        try {
            Custom.register(16);
        } catch (InvalidAge e) {
            System.out.println(e.getMessage());
        }
    }
}
Introduction to collection
 
Java Collections
Java Collections Framework is available in the java.util package. It provides interfaces and classes for storing, accessing, searching, sorting, and removing groups of objects.
import java.util.*;
1. Collection Interface
Collection is the main interface for List, Set, and Queue.
Syntax:
Collection<DataType> collection = new ArrayList<>();
Example:
Collection<String> names = new ArrayList<>();

names.add("Rahul");
names.add("Priya");
names.add("Amit");

System.out.println(names);
Output:
[Rahul, Priya, Amit]
Common methods:
add()
remove()
contains()
size()
clear()
isEmpty()
________________________________________
2. Iterator
Iterator traverses collection elements one by one in the forward direction.
Syntax:
Iterator<DataType> iterator = collection.iterator();
Example:
List<String> names = new ArrayList<>();
names.add("Rahul");
names.add("Priya");

Iterator<String> iterator = names.iterator();

while (iterator.hasNext()) {
System.out.println(iterator.next());
}
________________________________________
3. List Interface
A List maintains insertion order, allows duplicates, and supports index-based access.
Implementations: ArrayList, LinkedList, Vector, Stack
Syntax:
List<DataType> list = new ArrayList<>();
Example:
List<String> names = new ArrayList<>();

names.add("Rahul");
names.add("Priya");
names.add("Rahul");

System.out.println(names);
System.out.println(names.get(1));
Output:
[Rahul, Priya, Rahul]
Priya
``
________________________________________
4. ArrayList
ArrayList uses a dynamic array. It provides fast index-based access and allows duplicates.
Syntax:
ArrayList<DataType> list = new ArrayList<>();
Example:
ArrayList<String> list = new ArrayList<>();

list.add("Java");
list.add("Python");
list.add("C++");

System.out.println(list.get(0));
Output:
Java
________________________________________
5. LinkedList
LinkedList uses a doubly linked list. It is useful for adding or removing elements from the beginning and end.
Syntax:
LinkedList<DataType> list = new LinkedList<>();
Example:
LinkedList<String> list = new LinkedList<>();

list.add("Java");
list.addFirst("Python");
list.addLast("C++");

System.out.println(list);
Output:
[Python, Java, C++]
________________________________________
6. Vector
Vector is similar to ArrayList, but its methods are synchronized. It is a legacy collection class.
Syntax:
Vector<DataType> vector = new Vector<>();
Example:
Vector<String> vector = new Vector<>();

vector.add("Apple");
vector.add("Banana");

System.out.println(vector);
________________________________________
7. Stack
Stack follows LIFO, which means Last In, First Out.
Important methods: push(), pop(), peek()
Syntax:
Stack<DataType> stack = new Stack<>();
Example:
Stack<String> stack = new Stack<>();

stack.push("CPU");
stack.push("Monitor");
stack.push("Keyboard");

System.out.println(stack.pop());
System.out.println(stack);
Output:
Keyboard
[CPU, Monitor]
For modern Java code, ArrayDeque is generally preferred over Stack.
________________________________________
8. Queue Interface
A Queue usually follows FIFO, which means First In, First Out.
Important methods: offer(), poll(), peek()
Syntax:
Queue<DataType> queue = new LinkedList<>();
Example:
Queue<String> queue = new LinkedList<>();

queue.offer("Rahul");
queue.offer("Priya");
queue.offer("Amit");

System.out.println(queue.poll());
System.out.println(queue);
Output:
Rahul
[Priya, Amit]
________________________________________
9. PriorityQueue
PriorityQueue processes elements according to their natural order or a custom priority.
Syntax:
PriorityQueue<DataType> queue = new PriorityQueue<>();
Example:
PriorityQueue<Integer> queue = new PriorityQueue<>();

queue.offer(30);
queue.offer(10);
queue.offer(20);

while (!queue.isEmpty()) {
System.out.println(queue.poll());
}
Output:
10
20
30
________________________________________
10. Deque Interface
Deque means Double-Ended Queue. Elements can be added or removed from both ends.
Syntax:
Deque<DataType> deque = new ArrayDeque<>();
Example:
Deque<String> deque = new ArrayDeque<>();

deque.addFirst("Rahul");
deque.addLast("Priya");

System.out.println(deque);
Output:
[Rahul, Priya]
``
________________________________________
11. Set Interface
A Set stores unique elements and does not allow duplicates.
Implementations: HashSet, LinkedHashSet, TreeSet
Syntax:
Set<DataType> set = new HashSet<>();
``
Example:
Set<String> set = new HashSet<>();

set.add("Rahul");
set.add("Priya");
set.add("Rahul");

System.out.println(set);
The duplicate "Rahul" is ignored.
________________________________________
12. HashSet
HashSet stores unique elements but does not guarantee insertion order.
Syntax:
HashSet<DataType> set = new HashSet<>();
``
Example:
HashSet<String> set = new HashSet<>();

set.add("Java");
set.add("Python");
set.add("Java");

System.out.println(set.size());
Output:
2
________________________________________
13. LinkedHashSet
LinkedHashSet stores unique elements and maintains insertion order.
Syntax:
LinkedHashSet<DataType> set = new LinkedHashSet<>();
Example:
LinkedHashSet<String> set = new LinkedHashSet<>();

set.add("Peter");
set.add("Jack");
set.add("Peter");
set.add("Johnson");

System.out.println(set);
Output:
[Peter, Jack, Johnson]
``
________________________________________
14. TreeSet
TreeSet stores unique elements in sorted order.
Syntax:
TreeSet<DataType> set = new TreeSet<>();
``
Example:
TreeSet<String> set = new TreeSet<>();

set.add("Rahul");
set.add("Priya");
set.add("Amit");

System.out.println(set);
Output:
[Amit, Priya, Rahul]
________________________________________
15. Map Interface
A Map stores data as key-value pairs. Keys must be unique, but values can be duplicated.
Map is part of the Collections Framework, but it does not extend the Collection interface.
Syntax:
Map<KeyType, ValueType> map = new HashMap<>();
Example:
Map<Integer, String> map = new HashMap<>();

map.put(101, "Rahul");
map.put(102, "Priya");
map.put(103, "Amit");

System.out.println(map.get(102));
Output:
Priya
________________________________________
16. HashMap
HashMap provides fast key-based access and does not guarantee insertion order.
Syntax:
HashMap<KeyType, ValueType> map = new HashMap<>();
Example:
HashMap<String, Integer> marks = new HashMap<>();

marks.put("Alice", 80);
marks.put("Bob", 90);
marks.put("Charlie", 85);

for (Map.Entry<String, Integer> entry : marks.entrySet()) {
System.out.println(entry.getKey() + ": " + entry.getValue());
}
________________________________________
Quick Comparison
Type	Main feature
ArrayList	Ordered, duplicates, fast index access
LinkedList	Fast operations at both ends
HashSet	Unique, no guaranteed order
LinkedHashSet	Unique, insertion order
TreeSet	Unique, sorted
Queue	FIFO processing
PriorityQueue	Priority-based processing
ArrayDeque	Operations at both ends
HashMap	Key-value pairs, unique keys
Easy Memory Tip
•	List = Ordered and duplicates
•	Set = Unique elements
•	Queue = FIFO
•	Deque = Both ends
•	Map = Key-value pairs
 
Chapter 7: Java Collections
The topics shown are Set Interface, Map Interface, and Iterator/ListIterator. Below are short explanations, syntax, important methods, and simple code examples.
________________________________________
1. Set Interface
A Set stores unique elements. Duplicate values are ignored.
Implementations
•	HashSet: No guaranteed order
•	LinkedHashSet: Maintains insertion order
•	TreeSet: Maintains sorted order
Syntax
Set<DataType> set = new HashSet<>();
Important Methods
add(element) // Adds an element
remove(element) // Removes an element
contains(element) // Checks whether element exists
size() // Returns number of elements
isEmpty() // Checks whether Set is empty
clear() // Removes all elements
HashSet
Stores unique elements without maintaining order.
import java.util.*;

public class HashSetExample {
public static void main(String[] args) {
Set<String> set = new HashSet<>();

set.add("Java");
set.add("Python");
set.add("Java"); // Duplicate ignored

System.out.println(set);
System.out.println(set.contains("Java"));
System.out.println(set.size());
}
}
Possible output:
[Java, Python]
true
2
________________________________________
LinkedHashSet
Stores unique elements and maintains insertion order.
Set<String> set = new LinkedHashSet<>();

set.add("Java");
set.add("Python");
set.add("C++");
set.add("Java");

System.out.println(set);
Output:
[Java, Python, C++]
________________________________________
TreeSet
Stores unique elements in sorted order.
Set<Integer> set = new TreeSet<>();

set.add(30);
set.add(10);
set.add(20);
set.add(10);

System.out.println(set);
Output:
[10, 20, 30]
Set Comparison
Implementation	Duplicate	Order	null
HashSet	Not allowed	No guaranteed order	One allowed
LinkedHashSet	Not allowed	Insertion order	One allowed
TreeSet	Not allowed	Sorted order	Usually not allowed
________________________________________
2. Map Interface
A Map stores data as key-value pairs.
•	Keys must be unique
•	Values can be duplicated
•	An existing key's value is replaced when the key is inserted again
Implementations
•	HashMap: No guaranteed order
•	LinkedHashMap: Maintains insertion order
•	TreeMap: Sorts entries by keys
•	Hashtable: Synchronized legacy class
Syntax
Map<KeyType, ValueType> map = new HashMap<>();
Important Methods
put(key, value) // Adds or updates an entry
get(key) // Returns value for key
getOrDefault(key, value) // Returns value or default
remove(key) // Removes an entry
containsKey(key) // Checks whether key exists
containsValue(value) // Checks whether value exists
keySet() // Returns all keys
values() // Returns all values
entrySet() // Returns key-value entries
size() // Returns number of entries
clear() // Removes all entries
________________________________________
HashMap
Provides fast key-based access without maintaining order.
import java.util.*;

public class HashMapExample {
public static void main(String[] args) {
Map<Integer, String> map = new HashMap<>();

map.put(101, "Kamesh");
map.put(102, "Ravi");
map.put(103, "Priya");

System.out.println(map.get(102));
System.out.println(map.containsKey(101));

map.remove(103);

System.out.println(map);
}
}
Possible output:
Ravi
true
{101=Kamesh, 102=Ravi}
________________________________________
LinkedHashMap
Maintains the insertion order of entries.
Map<Integer, String> map = new LinkedHashMap<>();

map.put(3, "C");
map.put(1, "A");
map.put(2, "B");

System.out.println(map);
Output:
{3=C, 1=A, 2=B}
________________________________________
TreeMap
Stores entries in ascending order of keys.
Map<Integer, String> map = new TreeMap<>();

map.put(3, "C");
map.put(1, "A");
map.put(2, "B");

System.out.println(map);
Output:
{1=A, 2=B, 3=C}
________________________________________
Hashtable
A synchronized legacy Map implementation. It does not permit null keys or values.
Map<Integer, String> table = new Hashtable<>();

table.put(101, "Java");
table.put(102, "Python");

System.out.println(table.get(101));
Output:
Java
Map Comparison
Implementation	Order	null key	Synchronized
HashMap	No guaranteed order	One allowed	No
LinkedHashMap	Insertion order	One allowed	No
TreeMap	Sorted by keys	Usually not allowed	No
Hashtable	No guaranteed order	Not allowed	Yes
________________________________________
3. Iterator
Iterator traverses collection elements one by one in the forward direction.
It works with collections such as List, Set, and Queue.
Syntax
Iterator<DataType> iterator = collection.iterator();
Important Methods
hasNext() // Checks whether another element exists
next() // Returns the next element
remove() // Removes the current element safely
Code
import java.util.*;

public class IteratorExample {
public static void main(String[] args) {
List<String> languages = new ArrayList<>();

languages.add("Java");
languages.add("Python");
languages.add("C++");

Iterator<String> iterator = languages.iterator();

while (iterator.hasNext()) {
System.out.println(iterator.next());
}
}
}
Output:
Java
Python
C++
Removing with Iterator
Iterator<String> iterator = languages.iterator();

while (iterator.hasNext()) {
String language = iterator.next();

if (language.equals("Python")) {
iterator.remove();
}
}

System.out.println(languages);
Output:
[Java, C++]
________________________________________
4. ListIterator
ListIterator traverses a List in both forward and backward directions.
It works only with List implementations such as ArrayList and LinkedList.
Syntax
ListIterator<DataType> iterator = list.listIterator();
Important Methods
hasNext() // Checks for next element
next() // Returns next element
hasPrevious() // Checks for previous element
previous() // Returns previous element
add(element) // Adds an element
set(element) // Replaces the current element
remove() // Removes the current element
nextIndex() // Returns next element's index
previousIndex() // Returns previous element's index
Code
import java.util.*;

public class ListIteratorExample {
public static void main(String[] args) {
List<String> languages = new ArrayList<>();

languages.add("Java");
languages.add("Python");
languages.add("C++");

ListIterator<String> iterator = languages.listIterator();

System.out.println("Forward:");

while (iterator.hasNext()) {
System.out.println(iterator.next());
}

System.out.println("Backward:");

while (iterator.hasPrevious()) {
System.out.println(iterator.previous());
}
}
}
Output:
Forward:
Java
Python
C++

Backward:
C++
Python
Java
________________________________________
Iterator vs ListIterator
Feature	Iterator	ListIterator
Direction	Forward only	Forward and backward
Works with	Most collections	Only List
Add element	No	Yes
Replace element	No	Yes
Remove element	Yes	Yes
Access indexes	No	Yes
Quick Memory Notes
•	HashSet = Unique, no order
•	LinkedHashSet = Unique, insertion order
•	TreeSet = Unique, sorted
•	HashMap = Key-value, no order
•	LinkedHashMap = Key-value, insertion order
•	TreeMap = Key-value, sorted by keys
•	Hashtable = Synchronized, no null
•	Iterator = Forward traversal
•	ListIterator = Forward and backward traversal









 
Comparable and Comparator in Java
Both Comparable and Comparator are interfaces used to sort Java objects. The main difference is that Comparable defines the default sorting order inside the class, while Comparator defines separate, customizable sorting orders outside the class.
________________________________________
1. Why Are Comparable and Comparator Needed?
Predefined types such as Integer and String can be sorted directly:
List<Integer> numbers = new ArrayList<>();
numbers.add(40);
numbers.add(10);
numbers.add(30);
Collections.sort(numbers);
System.out.println(numbers);
Output:
[10, 30, 40]
However, Java does not automatically know how to sort custom objects:
class Student {
    int id;
    String name;
    double marks;
}
Should students be sorted by:
•	ID?
•	Name?
•	Marks?
We must define the sorting logic using:
•	Comparable
•	Comparator
________________________________________
2. Sorting with Comparable
Comparable<T> defines the natural or default ordering of objects.
The class being sorted must implement the Comparable interface and override:
compareTo(T other)
Basic Syntax
class ClassName implements Comparable<ClassName> {
    @Override
    public int compareTo(ClassName other) {
        // Comparison logic
    }
}
 
________________________________________
Example: Sort Students by ID
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

class Student implements Comparable<Student> {
    private int id;
    private String name;
    private double marks;

    public Student(int id, String name, double marks) {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    @Override
    public int compareTo(Student other) {
        return Integer.compare(this.id, other.id);
    }

    @Override
    public String toString() {
        return id + " - " + name + " - " + marks;
    }
}

public class ComparableDemo {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();

        students.add(new Student(103, "Arun", 82.5));
        students.add(new Student(101, "Kamesh", 91.0));
        students.add(new Student(102, "Divya", 87.5));

        Collections.sort(students);

        for (Student student : students) {
            System.out.println(student);
        }
    }
}
Output:
101 - Kamesh - 91.0
102 - Divya - 87.5
103 - Arun - 82.5
The default ordering is based on ID because compareTo() compares the student IDs:
return Integer.compare(this.id, other.id);
________________________________________
How compareTo() Works
this.compareTo(other)
The method returns:
Return value	Meaning
Negative value	this object comes before other
Zero	Both objects have equal sorting position
Positive value	this object comes after other
For example:
Integer.compare(101, 103)
returns a negative value, so 101 comes before 103.
________________________________________
Sorting by Name with Comparable
If the natural order should be based on the student's name:
@Override
public int compareTo(Student other) {
    return this.name.compareTo(other.name);
}
String already implements Comparable<String>, so names can be compared using String.compareTo().
For case-insensitive ordering:
@Override
public int compareTo(Student other) {
    return this.name.compareToIgnoreCase(other.name);
}
________________________________________
Descending Order with Comparable
To sort IDs in descending order, reverse the comparison:
@Override
public int compareTo(Student other) {
    return Integer.compare(other.id, this.id);
} 
Notice the reversed argument order:
Integer.compare(other.id, this.id);
________________________________________
3. Sorting with Comparator
Comparator<T> defines a custom or alternative sorting order.
The original class does not need to implement Comparator. The comparison logic is usually written in a separate class, anonymous class, or lambda expression.
The method to override is:
compare(T first, T second)
Basic Syntax 
class MyComparator implements Comparator<ClassName> {
    @Override
    public int compare(ClassName first, ClassName second) {
        // Comparison logic
    }
}
 
________________________________________
Student Class
The following Student class does not implement Comparable: 
class Student {
    private int id;
    private String name;
    private double marks;

    public Student(int id, String name, double marks) {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public double getMarks() {
        return marks;
    }

    @Override
    public String toString() {
        return id + " - " + name + " - " + marks;
    }
}
 
________________________________________
Comparator to Sort by Name
import java.util.Comparator;

class NameComparator implements Comparator<Student> {
    @Override
    public int compare(Student first, Student second) {
        return first.getName().compareToIgnoreCase(second.getName());
    }
}
Comparator to Sort by Marks
import java.util.Comparator;

class MarksComparator implements Comparator<Student> {
    @Override
    public int compare(Student first, Student second) {
        return Double.compare(first.getMarks(), second.getMarks());
    }
}
 
Using the Comparators
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class ComparatorDemo {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();

        students.add(new Student(103, "Arun", 82.5));
        students.add(new Student(101, "Kamesh", 91.0));
        students.add(new Student(102, "Divya", 87.5));

        Collections.sort(students, new NameComparator());

        System.out.println("Sorted by name:");

        for (Student student : students) {
            System.out.println(student);
        }

        Collections.sort(students, new MarksComparator());

        System.out.println("\nSorted by marks:");

        for (Student student : students) {
            System.out.println(student);
        }
    }
}
 
Output:
Sorted by name:
103 - Arun - 82.5
102 - Divya - 87.5
101 - Kamesh - 91.0

Sorted by marks:
103 - Arun - 82.5
102 - Divya - 87.5
101 - Kamesh - 91.0
________________________________________
4. Comparator Using Lambda Expression
Because Comparator is a functional interface, it can be implemented using a lambda expression.
Sort by ID
students.sort(
    (first, second) ->
        Integer.compare(first.getId(), second.getId())
);
Sort by Name
students.sort(
    (first, second) ->
        first.getName().compareToIgnoreCase(second.getName())
);
 
Sort by Marks
students.sort(
    (first, second) ->
        Double.compare(first.getMarks(), second.getMarks())
);
This is shorter than creating a separate comparator class.
________________________________________
5. Comparator Factory Methods
Modern Java provides convenient factory methods for constructing comparators.
Sort by ID
students.sort(
    Comparator.comparingInt(Student::getId)
);
Sort by Name
students.sort(
    Comparator.comparing(Student::getName)
);
Case-insensitive name sorting
students.sort(
    Comparator.comparing(
        Student::getName,
        String.CASE_INSENSITIVE_ORDER
    )
);
 
Sort by marks
students.sort(
    Comparator.comparingDouble(Student::getMarks)
);
Common methods include:
Comparator.comparing(...)
Comparator.comparingInt(...)
Comparator.comparingLong(...)
Comparator.comparingDouble(...)
 
The primitive-specific methods help avoid unnecessary boxing.
________________________________________
6. Ascending and Descending Sorting
Marks in ascending order
students.sort(
    Comparator.comparingDouble(Student::getMarks)
);
Output order:
82.5
87.5
91.0
Marks in descending order
students.sort(
    Comparator.comparingDouble(Student::getMarks)
              .reversed()
);
 
Output order:
91.0
87.5
82.5
The reversed() method reverses the complete comparator.
________________________________________
7. Sorting by Multiple Fields
Suppose students must be sorted by marks. If two students have the same marks, they should be sorted by name.
Use thenComparing():
Comparator<Student> comparator =
        Comparator.comparingDouble(Student::getMarks)
                  .thenComparing(Student::getName);

students.sort(comparator);
 
The sorting process works as follows:
1.	Compare students by marks.
2.	If marks are equal, compare their names.
Marks descending, then name ascending
Comparator<Student> comparator =
        Comparator.comparingDouble(Student::getMarks)
                  .reversed()
                  .thenComparing(Student::getName);

students.sort(comparator);
 
________________________________________
8. Comparable vs Comparator
Feature	Comparable	Comparator
Package	java.lang	java.util
Main method	compareTo(T other)	compare(T first, T second)
Objects compared	Current object and another object	Two supplied objects
Sorting type	Natural or default sorting	Custom sorting
Logic location	Inside the model class	Usually outside the model class
Number of orders	Normally one natural order	Multiple custom orders
Changes original class	Yes	Not required
Best for	One obvious default order	Different sorting requirements
________________________________________
9. Collections.sort() vs List.sort()
Using Collections.sort()
Natural ordering through Comparable:
Collections.sort(students);
Custom ordering through Comparator:
Collections.sort(
    students,
    Comparator.comparing(Student::getName)
);
Using List.sort()
students.sort(
    Comparator.comparing(Student::getName)
);
 
List.sort() modifies the existing list, just like Collections.sort().
________________________________________
10. Avoid Subtraction in Comparison Logic
You may see code like this:
 
 
return this.id - other.id;
 
It appears to work, but it can produce incorrect results because of integer overflow.
Prefer:
 
 
return Integer.compare(this.id, other.id);
 
For double, do not write:
 
 
return (int) (this.marks - other.marks);
 
This can incorrectly treat values such as 90.1 and 90.9 as equal after conversion to int.
Use:
 
 
return Double.compare(this.marks, other.marks);
 
Recommended methods:
 
 
Integer.compare(first, second)
Long.compare(first, second)
Double.compare(first, second)
 
________________________________________
11. Complete Example Using Both
import java.util.ArrayList;
import java.util.Comparator;
import java.util.List;

class Employee implements Comparable<Employee> {
    private int id;
    private String name;
    private double salary;

    public Employee(int id, String name, double salary) {
        this.id = id;
        this.name = name;
        this.salary = salary;
    }

    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public double getSalary() {
        return salary;
    }

    // Natural order: employee ID
    @Override
    public int compareTo(Employee other) {
        return Integer.compare(this.id, other.id);
    }

    @Override
    public String toString() {
        return id + " - " + name + " - " + salary;
    }
}

public class SortingDemo {
    public static void main(String[] args) {
        List<Employee> employees = new ArrayList<>();

        employees.add(new Employee(103, "Arun", 45000));
        employees.add(new Employee(101, "Kamesh", 60000));
        employees.add(new Employee(102, "Divya", 55000));

        // Comparable: natural order by ID
        employees.sort(null);

        System.out.println("Sorted by ID:");
        employees.forEach(System.out::println);

        // Comparator: custom order by name
        employees.sort(
            Comparator.comparing(Employee::getName)
        );

        System.out.println("\nSorted by name:");
        employees.forEach(System.out::println);

        // Comparator: custom order by salary, descending
        employees.sort(
            Comparator.comparingDouble(Employee::getSalary)
                      .reversed()
        );

        System.out.println("\nSorted by salary, descending:");
        employees.forEach(System.out::println);
    }
}
Output:
Sorted by ID:
101 - Kamesh - 60000.0
102 - Divya - 55000.0
103 - Arun - 45000.0

Sorted by name:
103 - Arun - 45000.0
102 - Divya - 55000.0
101 - Kamesh - 60000.0

Sorted by salary, descending:
101 - Kamesh - 60000.0
102 - Divya - 55000.0
103 - Arun - 45000.0
Easy Way to Remember
Comparable → The object compares itself with another object.
Comparator → A separate object compares two objects.
Comparable → compareTo()
Comparator → compare()
Interview Answer
Comparable is used to define the natural or default ordering of objects by implementing compareTo() inside the class. Comparator is used to define one or more custom sorting orders through compare(), usually outside the class. Use Comparable when a class has one obvious default order, and use Comparator when objects must be sorted in different ways, such as by name, marks, salary, or date.
both Comparable and Comparator are the interface in java used to sort the objects.
Comparable defines default sorting order inside the class
Comparator defines separate,customizable sorting orders outside the class.
Threading
When you start out programming it executes sequentially . this type of program run in a defined order with the beginning and end Simulantiously to achieve concurrency we use threading .Threading is the process of creating and managing multiple threads within a single process so that different tasks can execute concurrently.
Thread is the smallest unit of the execution within program enables concurrent execution of task
example youtube where video is one thread and audio is one thread runs simutiously
Thread is a smallest unit of execution within a process. It enables a program to perform multiple tasks concurrently while sharing the same memory and resource.

Thread vs Process
 
Feature	Process	Thread
Definition	An independent program in execution	A lightweight unit of execution within a process
Memory	Has its own separate memory space	Shares memory with other threads in the same process
Resource Sharing	Does not share resources with other processes by default	Shares code, data, and resources with sibling threads
Creation Time	Slower to create	Faster to create
Context Switching	More resources	Less resources
Communication	Uses Inter-Process Communication (IPC) mechanisms	Communicates easily through shared memory
Failure	Failure of one process usually does not affect others	Failure of one thread can affect the entire process
Example	Running a browser and a music player simultaneously	Multiple tabs or tasks running inside the same browser
Thread lifecycle 
1. New
Thread object is created.
start () has not been called.
2.Runnable 
start () is called.
thread is ready to run and waits for cpu
3.running
Thread is executing its run () method
4.Blocked/waiting
Thread is waiting for another thread or resource.
example sleep () ,join().
5.Dead
run() ends means it is completed.
CODE
class Mythread extends Thread{
    public void run(){
        System.out.println("Running");
        try{
            Thread.sleep(3000);
            System.out.println("i slept well");
        }
        catch(InterruptedException e){
            System.out.println("sleep error");
        }


    }
}
class Main {
    public static void main(String[] args) {
        Mythread t= new Mythread();
        t.start();

        try{
            t.join();
        }
        catch(InterruptedException e){
            System.out.println("sleep error");
        }
        System.out.println("Iam the last one");
    }
}

class Mythread implements Runnable{
    public void run(){
        System.out.println("Running");
        try{
            Thread.sleep(3000);
            System.out.println("i slept well");
        }
        catch(InterruptedException e){
            System.out.println("sleep error");
        }
    }
}
class Main {
    public static void main(String[] args) {
        Mythread mt= new Mythread();
        Thread t=new Thread(mt);
        t.start();

        try{
            t.join();
        }
        catch(InterruptedException e){
            System.out.println("sleep error");
        }


        System.out.println("Iam the last one");
    }
}
 Character stream
Character stream are used to read and write the text based data
They work with characters and are suitable for files such as .txt, .java, .csv, and .xml.
 All character-stream classes belong to the java.io package.
 

import java.io.*;
The main classes are:
•	FileReader
•	FileWriter
•	BufferedReader
•	BufferedWriter
•	import java.io.*;
class Main {
    public static void main(String[] args) {
      try{
          FileWriter w = new FileWriter("output.txt");
          w.write("hi");
          w.write("\nDone writing");
          w.close();
          System.out.println("finished writing");
      } 
      catch(IOException e){
          System.out.println(e.getMessage());
      }
      try{
          FileReader r= new FileReader("output.txt");
          int ch;
          while ((ch=r.read())!=-1){
              System.out.println((char) ch);
          }
      }
      catch(IOException e){
          System.out.println(e.getMessage());
      }
    }
}








BufferedWriter
•	BufferedWriter improves writing performance by storing characters temporarily in a buffer before writing them to the file.
 import java.io.*;
class Main {
    public static void main(String[] args) {
        try{
            BufferedWriter w= new BufferedWriter(new FileWriter("Output.txt"));
            w.write("Hello");
            w.newLine();
            w.write("Kamesh");
            w.close();
            System.out.println("write completed");
        }
        catch(IOException e){
            System.out.println(e.getMessage());
        }
        try{
            BufferedReader r= new BufferedReader(new FileReader("Output.txt"));
            String line;
            while((line=r.readLine())!=null){
                System.out.println(line);
            }
        }
        catch(IOException e){
            System.out.println(e.getMessage());
        }
    }
}








Files in java
import java.io.*;
class Main {
    public static void main(String[] args) {
        File f= new File("sample.txt");
        try{
            if(f.createNewFile()){
                System.out.println("Created file successfully");
                System.out.println(f.exists());//file exists or not
                System.out.println(f.getName());//get file name
                System.out.println(f.getPath());
                System.out.println(f.getAbsolutePath());
                System.out.println(f.isFile());
                System.out.println(f.isDirectory());
                System.out.println(f.canRead());
                System.out.println(f.canWrite());
                System.out.println(f.length());

                if (f.delete()) {
                     System.out.println("File deleted.");
                } else {
                    System.out.println("File could not be deleted.");
                }
                File directory = new File("documents");
 
               if (directory.mkdir()) {
                     System.out.println("Directory created.");
                    }
                     File nesteddirectory = new File("files/java/examples");
 
                    if (nesteddirectory.mkdirs()) {
                        System.out.println("Nested Directories created.");
                    }
 
            }
            else{
                System.out.println("Already file exists");
            }
        }
        catch(IOException e){
            System.out.println("erro:"+e.getMessage());
        }
    }
}
FileOutputStream writes a data to the file with sequence of bytes.
It is suitable for 
Binary data
Images
Audio files
PDF files
FileInputStream - Instead of reading one byte per operation, it reads up to 1,024 bytes at a time and prints exactly the bytes that were read.
import java.io.*;
import java.nio.charset.StandardCharsets;
class Main {
    public static void main(String[] args) {
        String s="Welcome Home";
        try{
            FileOutputStream out= new FileOutputStream("sample.txt");
            byte[] data= s.getBytes(StandardCharsets.UTF_8);
            out.write(data);
            System.out.println("written");
        }
        catch(IOException e){
            System.out.println(e.getMessage());
        }

        try{
            FileInputStream in= new FileInputStream("sample.txt");
            byte[] buffer= new byte[1024];
            int byteRead;
            while((byteRead=in.read(buffer))!=-1){
                System.out.write(buffer,0,byteRead);
            }
        }
        catch(IOException e){
            System.out.println(e.getMessage());
        }
    }
}

Class
File	Represents a file or directory path	Metadata	Creating, deleting, checking, or listing files
FileReader	Reads text from a file	Characters	Simple text reading
FileWriter	Writes text to a file	Characters	Simple text writing
BufferedReader	Efficiently reads text	Characters	Large text files and line-by-line reading
BufferedWriter	Efficiently writes text	Characters	Large or repeated text writing
FileInputStream	Reads raw file data	Bytes	Images, PDFs, audio, video, binary files
FileOutputStream	Writes raw file data	Bytes	Images, PDFs, audio, video, binary files
Character streams	Byte streams
Process characters	Process raw bytes
Designed for text	Designed for binary data
Reader and Writer classes	InputStream and OutputStream classes
Easier text processing	Preserves exact binary content
Encoding is handled at the character boundary	Encoding must be handled explicitly for text
 
JDBC (Java Database connectivity) is the java api is used to connect java application to the relational database such MySQL,postgre Sql, JDBC interface and classes are avaliable in java.sql package.
 
Java Application
       |
       v
    JDBC API
       |
       v
DriverManager
       |
       v
  JDBC Driver
       |
       v
    Database
JDBC API:
It allows java program to excute sql queries and get results from the database .
DriverManager:
Manages JDBC drivers and establishes database connections.
JDBC Drivers:
JDBC drivers are the adapters that convert requests from the java programs translate it so that database can understand .
1. Two-Tier Architecture
A Java Application communicates directly with the database using a JDBC driver. It sends queries to the database and then the result is sent back to the application.
  For example, in a client/server setup, the user's system acts as a client that communicates with a remote database server.
 
Structure:
 
Client Application (Java) -> JDBC Driver -> Database
 
2. Three-Tier Architecture
In this, user queries are sent to a middle-tier services, which interacts with the database. The database results are processed by the middle tier and then sent back to the user.
 
Structure:
 
Client Application -> Application Server -> JDBC Driver -> Database
Class/Interfaces	Description
DriverManager	Manages JDBC drivers and establishes database connections.
Connection	Represents a session with a specific database.
Statement	Used to execute static SQL queries.
PreparedStatement	Precompiled SQL statement, used for dynamic queries with parameters.
CallableStatement	Used to execute stored procedures in the database.
ResultSet	Represents the result set of a query, allowing navigation through the rows.
SQLException	Handles SQL-related exceptions during database operations.
 
Feature	Statement	PreparedStatement
Definition	Used to execute simple SQL queries.	Used to execute parameterized SQL queries.
Query Creation	SQL query is written directly in the code.	SQL query contains placeholders (?) for values.
Compilation	Query is compiled every time it is executed.	Query is compiled once and reused.
Performance	Slower for repeated executions.	Faster for repeated executions.
Parameters	Does not support parameters.	Supports parameters using setInt(), setString(), etc.
Security	Vulnerable to SQL Injection.	Prevents SQL Injection attacks.
Reusability	Less reusable.	Highly reusable.
Execution Speed	Lower for multiple executions.	Higher for multiple executions.
Suitable For	Static SQL queries.	Dynamic and frequently executed queries.
Example Query	SELECT * FROM Student	SELECT * FROM S
a JDBC connection must be established. It acts as a communication link between the application and the database to send queries and receive results.
•	Load the appropriate database driver
•	Specify the database URL
•	Provide username and password for authentication
JDBC is a middleman that builds communication between a Java application and a database.

 




import java.sql.*;
class Geeks {
    public static void main(String[] args) throws Exception {
        String url = "jdbc:mysql://localhost:3306/database_name"; // Database details
        String username = "rootgfg"; // MySQL credentials
        String password = "gfg123";
        String query = "select * from students"; // Query to be run
        // Load and register the driver
        Class.forName("com.mysql.cj.jdbc.Driver");
        // Establish connection
        Connection con = DriverManager.getConnection(url, username, password);
        System.out.println("Connection Established successfully");
        // Create a statement
        Statement st = con.createStatement();
        // Execute the query
        ResultSet rs = st.executeQuery(query);
        // Process the results
        while (rs.next()) {
            String name = rs.getString("name"); // Retrieve name from db
            System.out.println(name); // Print result on console
        }
        // Close the statement and connection
        st.close();
        con.close();
        System.out.println("Connection Closed....");
    }
}

















 
A Lambda expression is an anonymous function (a function without a name) that can be used to implement a method of a functional interface.
(parameters) ->expression
or
(parameters) -> {
  //statement
}
public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> n= new ArrayList<Integer>();
    n.add(5);
    n.add(2);
    n.forEach((i)->{System.out.println(i*i);});
  }
}
A Functional Interface is an interface that contains exactly one abstract method.
It can have:
One abstract method
Multiple default methods
Multiple static methods

import java.util.ArrayList; 
@FunctionalInterface
interface Calculator {
   int calculate(int a, int b);
   // Default method
   default int multiply(int a, int b) {
       return a * b;
   }
}
public class Main {
   public static void main(String[] args) {
       // Using lambda to implement the abstract method
       Calculator addition = (a, b) -> a + b;
       // Calling the abstract method
       System.out.println("Sum: " + addition.calculate(5, 3));
       // Using default method via object reference
       System.out.println("Product: " + addition.multiply(5, 3));
   }
}
 
The stream api provides the functional way to process the collection of data.
filter() ->  select
reduce() ->  combine
map() -> modify
eg:
import java.util.List;
public class FilterExample {
    public static void main(String[] args) {
        List<Integer> numbers = List.of(1, 2, 3, 4, 5, 6);
        numbers.stream()
               .filter(n -> n % 2 == 0)
               .forEach(System.out::println);
    }
}
 
import java.util.List;
public class StreamExample {
    public static void main(String[] args) {
        List<Integer> numbers = List.of(1, 2, 3, 4, 5);
        int result = numbers.stream()
                            .filter(n -> n % 2 == 0) // 2,4
                            .map(n -> n * n)         // 4,16
                            .reduce(0, Integer::sum);// 20
        System.out.println(result);
    }
}
Generics allow you to write type-safe and reusable code . Instead writing code for every different datatype . We can define the datatype as parameter.
class Box<T> {
    private T value;
    public void set(T value) {
        this.value = value;
    }
    public T get() {
        return value;
    }
}
Box<String> stringBox = new Box<>();
stringBox.set("Hello");
String s = stringBox.get();
Box<Integer> intBox = new Box<>();
intBox.set(100);
Integer i = intBox.get();
 
Generic Method 
Generic method is method that works with different datatypes without rewriting the same code for each datatype.
public class GenericMethodExample {
    // Generic method to print any type of array
    public static <T> void printArray(T[] array) {
        for (T element : array) {
            System.out.print(element + " ");
        }
        System.out.println();
    }
    public static void main(String[] args) {
        Integer[] intArray = {1, 2, 3};
        String[] strArray = {"Hello", "World"};
        // Works for Integer array
        printArray(intArray);
        // Works for String array
        printArray(strArray);
    }
}
Wildcard
Wildcard is represented by the ? and that means unknown datatype
That works with the different generic types(datatypes) without knowing exact datatype.
Unbounded Wildcard 
It means any type is allowed 
It doesn't care about the type parameter
void printList(List<?> list) {
    for (Object obj : list) {
        System.out.println(obj);
    }
}
Upper bounded wildcard
<? extends Type>
Useful when you read data from collection
void processNumbers(List<? extends Number> list) {
    for (Number num : list) {
        System.out.println(num.doubleValue());
    }
}
Lower bounded wildcard
<? super Type>
Useful when you write data into a collection.
void addIntegers(List<? super Integer> list) {
    list.add(10);
    list.add(20);
}
 
Annotation are metadata added to java code to give extra information to java compiler
@Override is used in the child class to override the method in the parent class or interface .
@Deprecated is used when a class, method , variable is old and should not used anymore.
This tells the developer , the method still works but avoid using it . user better method instead.
Custom Annotation
Simple custom annotation.
@interface MyAnnotation {
}
we can use it like this:
@MyAnnotation
class Student {
}
Example:
@interface CourseInfo {
    String courseName();
    int duration();
}
@CourseInfo(courseName = "Java", duration = 30)
class JavaCourse {
    void display() {
        System.out.println("Java course details");
    }
}

Design patterns
  Design Patterns are reusable solution for commonly occurring problems
They act as the templates for solving issues related to object creation, structure, behaviours.
1. Singleton Pattern
It ensures that only one object exists throughtout the application (provides a global point of access to it)
Example:
Database Connections : Manage a single point of database access.
eg:
class Singleton {
    private static Singleton instance;
    private Singleton() {}
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
How It Works
✅ Constructor is private (cannot create objects directly)
✅ getInstance() returns the same object every time

Singleton s1 = Singleton.getInstance(
Singleton s2 = Singleton.getInstance();
System.out.println(s1 == s2); // true
2. Factory Pattern
Create a object without exposing the object creation logic.
Real life example :
Car Factory
You ask the factory for a car. 
The factory decides whether to create:
Sedan
SUV
Hatchback 
You don't need to know the creation detail.
eg:
interface Vehicle {
    void drive();
}
class Car implements Vehicle {
    public void drive() {
        System.out.println("Driving Car");
    }
}
class Bike implements Vehicle {
    public void drive() {
        System.out.println("Driving Bike");
    }
}
Factory class:
class VehicleFactory {
    public static Vehicle createVehicle(String type) {
        if(type.equals("car"))
            return new Car();
        else
            return new Bike();
    }
}
 
Vehicle vehicle = VehicleFactory.createVehicle("car");
vehicle.drive();
 
3.Observer pattern
Allow multiple objects to automatically notified when another object changes state.
Real-Life Example
YouTube Subscribers
You subscribe to a channel.
Creator uploads a video.
All subscribers get notified.
 
Subject
  |
  |-- notify()
  |
Observers
 
The channel = Subject
Subscribers = Observers
Observer Interface:
interface Observer {
    void update(String message);
}
 
Subscriber: 
class Subscriber implements Observer {
    public void update(String message) {
        System.out.println("Received: " + message);
    }
}
 
YouTube Channel:
class Channel {
    List<Observer> observers = new ArrayList<>();
    void subscribe(Observer o) {
        observers.add(o);
    }
    void notifySubscribers(String msg) {
        for (Observer o : observers) {
            o.update(msg);
        }
    }
}
Usage:
Channel channel = new Channel();
Subscriber s1 = new Subscriber();
Subscriber s2 = new Subscriber(); 
channel.subscribe(s1);
channel.subscribe(s2); 
channel.notifySubscribers("New Video Uploaded!");
4. Strategy Pattern
Defines multiple algorithms and switch between them at runtime 
real-Life Example
🗺️ Google Maps Navigation
You can choose:
Car Route
Bike Route
Walking Route
The destination is the same, but the route calculation strategy changes.
Strategy Interface:
interface PaymentStrategy {
    void pay(int amount);
}
Concrete Strategies:
class CreditCardPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid using Credit Card");
    }
}
 
class UpiPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid using UPI");
    }
}
Context:
class PaymentContext {
    private PaymentStrategy strategy;
    public PaymentContext(PaymentStrategy strategy) {
        this.strategy = strategy;
    } 
    public void pay(int amount) {
        strategy.pay(amount);
    }
}
Usage:
PaymentContext payment = new PaymentContext(new UpiPayment());
payment.pay(1000);



