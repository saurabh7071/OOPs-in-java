# Interface in Java

## What is an Interface?

- An **interface** in java is like a contract. 
- It defines **What a class should do**, but **not how it does it**.
- It contains **method declarations** (without body).
- The class that implements the interface must **provide the code** (method body).

Think of it like a **remote control** - it has buttons (methods), but the real work is done by the TV (class that implements it).

## Why use Interfaces?

- To **achieve abstraction** (hide implementation).
- To **support multiple inheritance** in java.
- To make code **flexible** and **loosely coupled**.
- To define a **common behavior** for unrelated classes.

## Key Points
- Use `interface` keyword
- A class uses `implements` keyword to use an interface.
- A class can implement multiple interfaces. 

## Example Code 

```java
import java.util.*;

interface Flyable{
  void fly(); // Method declaration
}

interface Swimmable{
  void swim();  // Method declaration
}

class Duck implements Flyable, Swimmable{
  // method body
  public void fly(){
    System.out.println("Duck Flying");
  }
  
  // method body
  public void swim(){
    System.out.println("Duck swimming");
  }
}

public class Main {
    public static void main(String[] args) {
      Duck d = new Duck();
      d.fly();
      d.swim();
  }
}
```

### 🔍 Breakdown:
1. Interfaces Defined:

    - `Flyable` has a method `fly()`.

    - `Swimmable` has a method `swim()`.

    👉 These are just method declarations (no body).

2. Class Duck Implements Both Interfaces:

    - `Duck` provides method bodies for both `fly()` and `swim()`.

    - This is required because the interface only defines _what_ needs to be done, not _how_.

3. Main Class:

    - In the `main()` method, a `Duck` object `d` is created.
    - Then it calls `d.fly()` and `d.swim()`, which prints:

    ```
    Duck Flying
    Duck swimming
    ```
## When to Use?

- When you want to define a common behavior (e.g, Drivable, Flyable, Payable) that can be used across different classes. 
- To provide flexibility and plug-and-play behavior to your design.


## In short

- Interfaces are a powerful tool in java that help you build scalable, flexible, and loosely coupled systems.
- Use them when you need to enforce **what a class must do**, but **not how it does it**. 