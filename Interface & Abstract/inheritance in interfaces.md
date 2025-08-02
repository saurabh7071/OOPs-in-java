# Inheritance in Interface 

## What is Interface Inheritance?

- **Interfaces can inherit other interfaces** just like classes can inherit from other classes.
- This means an interface can **extend** one or more interfaces and **inherit their abstract methods**. 

## Syntax 

```java
interface A{
    void methodA();
}

interface B extends A{
    void methodB();
}
```
- Here, `interface B` inherits `methodA` from interface A.
- Any class that implements B must implement both `methodA()` and `methodB()`.

## Example Code 

```java
interface Animal{
  void eat();
}

interface Bird extends Animal{
  void fly();
}

class Sparrow implements Bird{
  public void eat(){
    System.out.println("Sparrow eating");
  }
  
  public void fly(){
    System.out.println("Sparrow flying");
  }
}

public class Main {
    public static void main(String[] args) {
      Sparrow s = new Sparrow();
      s.eat();
      s.fly();
  }
}
```

### Explanation:

- `Bird` extends `Animal`, so it inherits `eat()`.
- `Sparrow` implements `Bird`, so it must define both:
    - `eat()` (from `Animal`)
    - `fly()` (from `Bird`)


# Multiple Inheritance in Interface 

```java
interface Cat{
  void eat();
}

interface Bird{
  void fly();
}

interface check extends Cat, Bird{
  void check();
}

class Animal implements check{
  public void eat(){
    System.out.println("Cat can eat");
  }
  
  public void fly(){
    System.out.println("Bird can fly");
  }
  
  public void check(){
    System.out.println("It is true");
  }
}

public class Main {
    public static void main(String[] args) {
      Animal s = new Animal();
      s.eat();
      s.fly();
      s.check();
  }
}
```

### Output 

```
Cat can eat
Bird can fly
It is true
```

## Why Use Interface Inheritance?
- Promotes _code reusability_.
- Encourages _modular design_ 
- Enables _multiple inheritance_(which is not possible with classes in java)


## ❌ Why Multiple Inheritance is not Possible with classes? 

**Multiple Inheritance with classes means:** A class inherits from **more than one class** directly.  

**Problem:** It creates the **Diamond problem**. 

### Example 

```java
class A {
    void show() {
        System.out.println("A's show");
    }
}

class B extends A {
    void show() {
        System.out.println("B's show");
    }
}

class C extends A {
    void show() {
        System.out.println("C's show");
    }
}

// ❌ Now imagine this was allowed:
class D extends B, C {  // Not allowed in Java
    // Which show() should D inherit? From B or C?
}
```

**Java Says:** Too Confusing!
- Compiler won't know which show() to call.
- It creates **ambiguity** and **complex bugs**.

## ✅ Why Multiple Inheritance is Possible with Interfaces

Interface don't have concrete method bodies.
They only provide **method signatures** (like rules).

✨ **No Ambigity Because:**

- A class implementing multiple interfaces much **define the method itself**, so **no confusion**.

```java
interface A {
    void show();
}

interface B {
    void show();
}

class C implements A, B {
    public void show() {
        System.out.println("C's own show");
    }
}
```
- Even though both `A` and `B` declare `show()`, `c` provides the actual implementation.
- So there's **no conflict**.

## What if Interface has Default Methods?

From java 8 onward, interface can have `default` methods.

```java
interface A {
    default void show() {
        System.out.println("A show");
    }
}

interface B {
    default void show() {
        System.out.println("B show");
    }
}

class C implements A, B {
    // Must override to avoid conflict
    public void show() {
        System.out.println("C resolves conflict");
    }
}
```
✅ Java still allows it, but forces you to override the method to remove ambiguity. 

### So Overall,
✅ Interfaces give **flexibility with safety**, while multiple class inheritance may lead to **confusion and bugs**. 

--- 

# Summary
- ✅ Interfaces can extend other interfaces.
- ✅ A class implementing a child interface must implement all methods from all parent interfaces.
- ✅ Interfaces support multiple inheritance using the extends keyword.
