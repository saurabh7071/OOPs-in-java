# Runtime Polymorphism 

## What I Understand 
> - For runtime polymorphism there is actually need of inheritance without inheritance the method overriding is not possible 

> - And method overriding is responsible for run time polymorphism, So inheritance means there is always a superclass and other their subclasses 

> - So what happens, The subclasses try to provide specific implementation for a method that is already defined at superclass. With that implementation it try provide a specialised or different behaviour in the contact of subclass. 

> - And it happens on runtime means after compiling the program that's why it called as run time polymorphism 

> - And it is a good practice to use @override annotation to verify that method is overriding a superclass method 

> - Overriding, as word meaning like a child class method implementation for method that already present at there parent class 

## 📌 What is Runtime Polymorphism ?
- Occurs when a subclass provides a specific implementation of a method that is already defined in its superclass, using the same method signature and its happens at runtime. 
- It is achived through **method overriding**.
- **Overriding** is when a child class has it's method implementation for the method already present in the parent class. 

## 🗝️ Key aspects of Method Overriding
- **Inheritance Requirement**: Method overriding can only occur within an inheritance hierarchy, where a subclass extends a superclass.
- **Same Signature**: The method in the subclass must have the exact same name, return type (or a covariant return type), and parameters (signature) as the method in the superclass it intends to override.
- **Specific Implementation**: The purpose of overriding is to provide a specialized or different behavior for an inherited method within the context of the subclass.
> - **`@Override` Annotation**:
> It is good practice to use the `@Override` annotation above an overridden method in the subclass. This annotation helps the compiler verify that the method is indeed overriding a superclass method, catching potential errors like typos in method signatures.

## 🤯 How it works? 
- Achieved using **method overriding** (a subclass provides a specific implementation of a method already defined in its parent class)
- The call to the overridden method is determined **at runtime**, depending on the type of the object. 
- It uses **dynamic method dispatch**

## 🛠️ Use Case
> Imagin you're building a system with multiple notifications types (e.g email, sms, push). You can define a common interface `sendNotification()` and override it in each class. The actual method that gets executed depends on the object type at runtime. 

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

### Code Explanation
- A reference variable a of type Animal is created.

- a is first assigned a new Dog() object.
    - Even though the reference type is Animal, the actual object is Dog, so the overridden Dog version of sound() runs → "Dog barks".

- Then a is assigned a new Cat() object.

    - Now the actual object is Cat, so the Cat version of sound() runs → "Cat meows".

## ⭕ What Are the Rules for Method Overriding in Java? 
### Laws of Method Overriding in JAVA: 

- The method name should be common and the same as it is in the parent class.
- The method signature (parameter list, return type) in the method must be the same as in the parent class.
- There must be an inheritance connection between classes.
- All the abstract methods in the parent class should be overridden in the child class.
- If it declared the methods as static or final, then those methods cannot be overridden.

# 🧾 Summary
- Runtime polymorphism provides flexibility and extensibility.

- It enables writing generic code that can adapt to different object types.

- Essential in frameworks, APIs, and design patterns like Strategy, State, etc.
