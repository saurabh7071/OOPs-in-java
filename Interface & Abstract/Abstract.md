# Abstract in Java

## What is `abstract` in Java?

In java, `abstract` is a **keyword** used for:
- _Abstract Classes_
- _Abstract Methods_

They are used to define **incomplete blueprints** - which must be completed by subclasses. 

## Abstract Class 

An **Abstract class** is a class that **cannot be instantiated directly**. It may have:
- Abstract methods (without body)
- Concrete methods (with body)
- Constructors
- Fields (variables)

### Syntax 

```java
abstract class Animal{
    abstract void sound(); // Abstract method

    void sleep(){
        System.out.println("Sleeping...");
    }
}
```


## Abstract Method 

An abstract method:
- Has **no body** (just declaration).
- Must be **overriden** in child class. 

```java
abstract void sound(); // No body
```

### Subclass Must Implement

```java
class Dog extends Animal{
    void sound(){
        System.out.println("Dog Barks");
    }
}
```

You must implement all abstract methods in no-abstract subclasses, otherwise the subclass must also be declared `abstract`.

### ❌ Cannot Create Object of Abstract Class 

```java
Animal a = new Animal(); //  ❌ Error!
```

But we can do:
```java
Dog d = new Dog();  // Object of subclass
d.sound();  // Dog Barks
```

## Key Points 

1. Object Creation ->  ❌ Not allowed 
2. Has constructor -> ✅ Yes
3. Can have body methods -> ✅ Yes
4. Can have variables -> ✅ Yes
5. Use with interfaces? -> ✅ Yes (implements)

## Example Code 

```java
abstract class Vehical{ // abstract class because method is abstract 
    void stop(){
        System.out.println("Vehical Stopped!");
    }

    abstract void start();  // method declaration - no method body
}

class Car extends Vehical{  // Child class 
    void start(){
        System.out.println("Car Started!");
    }
}

class Main{
    public static void main(String[] args){
        //Vehical v = new Vehical(); ❌ Error!

        Car c = new Car();  // object of child class 
        c.start();
        c.stop(); 
    }
}
```

### Output 

```
Car Started!
Vehical Stopped!
```

## Do you Know? 

1. Can we create object of abstract class?
    >     No

2. Can we have constructor in abstract class?
    >     Yes

3. Can we do multilevel inheritance?
    >     Yes 

4. Can we do mutiple inheritance?
    >     No

## When to Use?
- When you want to define a common base for multiple subclasses.
- When you want to force subclasses to implement some behavior, bu also allow shared code. 