# Constructor
- A constructor is a special type of method used to initialize objects when they are created.
- It has the same name as the class it belongs to and does not have a return type, not even void.

## Key Characteristics
same name as the class: The constuctor's name must exactly match the class name 
No Return type: Constructors do not return any value and thus no return type (like void) is specified in their declaration 
Automatically Invoked: When an object of a class is created using the new keyword, the corresponding constructor is automatically called to initialize the object 
Purpose: The primary purpose of a constructor is to set the initial state of an object by assigning values to its instance variables or performing other setup procedures. 

## Types of constructos
1. Default Constructor
- If no constructor is explicitly defined in a class, java provides a default constructor.
- This constructor is parameterless and initializes instance variables with their default values(e.g 0 for numeric types, false for booleans and null for object references)
```java
  public class MyClass{
    int myInt;
    String myString;

    // No constructor explicitly defined so java provides a default constructor 
    public static void main(String[] args){
      MyClass obj = new MyClass();  // Default constructor is implicitly called 
      
      System.out.println(obj.myInt); // output: 0
      System.out.println(obj.myString); // output: null
    }
}

```
- No-Argument Constructor (User-Defined):
This is a constructor explicitly defined by the programmer that takes no arguments. It can be used to set specific default values or perform initializations that differ from the Java default.
```java
  
public class Dog{
    String name;
    int age;

    // No-argument constructor
    public Dog(){
      this.name = "Buddy";
      this.age = 5;
    }
    
    public void display(){
        System.out.println(name+" "+age);
    }
    
    public static void main(String[] args) {
        Dog obj = new Dog();
        obj.display();
    }
}

```
Parameterized Constructor:
This type of constructor accepts one or more parameters. It allows for initializing object attributes with specific values provided at the time of object creation, enabling more flexible object instantiation.
```java
  class Car {
    String name;
    int year;
    
    // Parameterized constructor
    Car(String name, int year){
        this.name = name;
        this.year = year;
    }
    
    public void display(){
        System.out.println(name+" "+year);
    }
    
    public static void main(String[] args) {
        Car obj = new Car("Tata", 2023);    // Parameterized constructor is called 
        obj.display();
        
        Car obj1 = new Car("Honda", 2012);
        obj1.display();
    }
}
```
Copy Constructor (User-Implemented):
While Java does not provide a built-in copy constructor like C++, you can implement a similar functionality by creating a constructor that takes an object of the same class as an argument and copies its state to the new object.
```java
  public class Person {
    String name;
    int age;
    
    // Parameterized constructor
    public Person(String name, int age){
        this.name = name;
        this.age = age;
    }
    
    // Copy Constructor 
    public Person(Person other){
        this.name = other.name;
        this.age = other.age;
    }
    
    public void display(){
        System.out.println(name);
        System.out.println(age);
    }
    
    public static void main(String[] args) {
        Person person1 = new Person("Saurabh", 20);
        Person person2 = new Person(person1); // Copy constructor is used 
        
        System.out.println("Original Person: ");
        person1.display();
        
        System.out.println("Copied Person: ");
        person2.display();
    }
}
```
