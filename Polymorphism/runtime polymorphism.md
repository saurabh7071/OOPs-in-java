# Runtime Polymorphism 

## 📌 What is Runtime Polymorphism ?
- Runtime Polymorphism (also known as **Dynamic Polymorphism**) occurs when a method call to an overridden method is resolved **at runtime** rather than at compile time.
- It is achived through **method overriding**.
- It enables **one interface with multiple implementations**, allowing code flexibility and dynamic behaviour based on the actual object type. 

## 🤯 How it works? 
- Achieved using **method overriding** (a subclass provides a specific implementation of a method already defined in its parent class)
- The call to the overridden method is determined **at runtime**, depending on the type of the object. 
- It uses **dynamic method dispatch**

## 🛠️ Use Case
> Imagin you're building a system with multiple notifications types (e.g email, sms, push). You can define a common interface `sendNotification()` and override it in each class. The actual method that gets executed depends on the object type at runtime. 

## 💻 Example Code

```java
# Runtime Polymorphism in Java

## 📌 What is Runtime Polymorphism?

Runtime Polymorphism (also known as **Dynamic Polymorphism**) occurs when a method call to an overridden method is resolved **at runtime** rather than at compile time. This is achieved through **method overriding**.

It enables **one interface with multiple implementations**, allowing code flexibility and dynamic behavior based on the actual object type.

---

## 🧠 How It Works

- Achieved using **method overriding** (a subclass provides a specific implementation of a method already defined in its parent class).
- The call to the overridden method is determined **at runtime**, depending on the type of the object.
- It uses **dynamic method dispatch**.

---

## 🛠️ Use Case

Imagine you’re building a system with multiple notification types (e.g., Email, SMS, Push). You can define a common interface `sendNotification()` and override it in each class. The actual method that gets executed depends on the object type at runtime.

---

## ✅ Real-Life Example

- A **remote control** (`Remote`) is the parent class.
- Different devices like `TVRemote`, `ACRemote` extend it and override the `pressPowerButton()` method.
- At runtime, depending on the object created, the behavior of the power button will differ.

---

## 💻 Example Code

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a;
        
        a = new Dog();  // object of Dog, reference of Animal
        a.sound();      // Output: Dog barks

        a = new Cat();  // object of Cat, reference of Animal
        a.sound();      // Output: Cat meows
    }
}
```

## ✅ Real-Life Example

- A **remote control** (`Remote`) is the parent class.
- Different devices like `TVRemote`, `ACRemote` extend it and override the `pressPowerButton()` method.
- At runtime, depending on the object created, the behavior of the power button will differ.

🧾 Summary
- Runtime polymorphism provides flexibility and extensibility.

- It enables writing generic code that can adapt to different object types.

- Essential in frameworks, APIs, and design patterns like Strategy, State, etc.