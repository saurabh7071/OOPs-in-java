# 🧩 Constructor Chaining with Inheritance

## ✅ What is Constructor Chaining?
- **Constructor Chaining** means calling one constructor from another constructor.  
- In **Inheritance**, constructor chaining ensures that when a child class object is created, the **parent class constructor is executed first**, followed by the child class constructor.

## 🧠 Why It Matters?

When a class inherits another class:

- The **child class constructor** automatically calls the **parent class constructor** to make sure the parent’s part of the object is initialized.
- This is done using the `super()` keyword.
- Helps maintain **clean and reusable code** by centralizing initialization logic.

---

## 🔧 Syntax of `super()`

```java
super(); // This calls the no-argument constructor of the parent class

super(any value) // This will call to any parametric constructor of the parent class
```

> ✅ Note: 
> - `super()` must be the **first line** in the constructor.
> - Only one `super()` should be in the constructor. 
> - If you do not explicitly write `super()` in the constructor of a subclass, Java automatically inserts a call to the no-argument constructor of the parent class as the first statement.

---

## 📌 Simple Example: Constructor Chaining with Inheritance

```java
class Animal {
    Animal() {
        System.out.println("Animal constructor called");
    }

    Animal(int val){
        System.out.println("Animal Parameterized contructor called");
    }
}

class Dog extends Animal {
    Dog() {
        super();  // Calls Animal constructor
        // super(10);  --> it will call parameterized constructor
        System.out.println("Dog constructor called");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
    }
}
```

### ✅ Output:
```
Animal constructor called
Dog constructor called
```

---

## 🧪 What Happens Here?

1. When `new Dog()` is executed, the `Dog` class constructor runs.
2. Inside it, `super()` is called **implicitly or explicitly**, which calls the parent class `Animal()` constructor.
3. This ensures the `Animal` (parent) part of the object is initialized before the `Dog` (child) part.


## 🎯 Use of `super()` in Constructor Chaining

- `super()` is used to **call the parent class constructor** from the child class.
- It is necessary when the parent class has some important initialization logic that needs to be executed before the child class constructor.
- If not specified, Java automatically inserts `super()` in the child constructor.


## 🌍 Real-life Analogy

Imagine building a **Smartphone**:

- First, the **basic phone parts (battery, screen)** are assembled (`super()` → Parent class).
- Then, the **smart features (OS, apps)** are added (`this` constructor → Child class).

So, the parent constructor lays the foundation, and the child constructor adds advanced features — both are important and happen in a chained manner.

---
