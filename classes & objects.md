# ⭐ Classes & Objects in Java

In Java, classes and objects are fundamental concepts of OOP, enabling us to model real-world entities.


## ⭐ Class

- A **class** serves as a blueprint or template for creating objects.
- It defines the structure and behaviour that objects of that class will possess.
- A class can contain: 
  - **Fields** (attributes/variables): Hold the data or state of an object.
  - **Methods**: Define the actions or behaviours an object can perform.
  - **Constructors**: Special methods used to initialize new objects when they are created.

### Example
```java
public class Car {
    // Fields
    String brand;
    String model;
    int year;

    // Constructor
    public Car(String brand, String model, int year){
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    // Method
    public void displayInfo(){
        System.out.println("Hello World!");
    }
}
```

## ⭐ Object

- An **object** is an instance of a class.
- It is the concrete realization of the blueprint defined by the class, representing a specific entity with its own unique state and behavior.
- Objects are created from classes using the `new` keyword.

### Example
```java
public class Main {
    public static void main(String args[]) {
        Car c1 = new Car("Toyota", "Camry", 2022); // object of the class Car

        c1.displayInfo(); // Accessing object methods
    }
}
```

---

## 📝 In Short

A class defines the general characteristics, while an object is a specific instance embodying those characteristics.  
You can create multiple distinct objects from a single class.

## 📌 Example

```java
class Student {
    int age;
    String name;

    public int check(){
      return age;
    }
}

class Main(){
  public static void main(String args[]){
    Student s1 = new Student();
    s1.age = 20;
    s1.name = "Saurabh";

    System.out.println(name+" "+age);
    System.out.println(s1.check());

    Student s2 = new Student();
    s2.age = 21;
    s2.name = "Sudesh";

    System.out.println(name+" "+age);
    System.out.println(s2.check());
}
}
```
