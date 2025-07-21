# Inheritance in Java

## What is Inheritance?
- Inheritance is one of the four key principles of OOP.
- It allows a **child class** to acquire the **properties(fields) and behaviour (method)** of a **parent class**.
- This helps in reusing existing code and building a hierarchical classification. 
- Relationship in hierarchy 

## Keyword: `extends`
- Java uses the `extends` keyword to define inheritance between two classes. 

## Syntax and Example Code 

### 🟩 Parent Class (Base/Superclass)
```java
public class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}
```

}
### 🟦 Child Class (Derived/Subclass)
```java
Copy code
public class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}
```

### 🟨 Main Class
```java
Copy code
public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat();   // inherited from Animal class
        myDog.bark();  // defined in Dog class
    }
}
``` 

### Output 
```nginx
This animal eats food.
The dog barks.
```

## 🔄 Types of Inheritance in Java
1. **Single Inheritance**: One child class inherits from one parent class.

2. **Multilevel Inheritance**: A child inherits from a parent, and another child inherits from the first child.

3. **Hierarchical Inheritance**: Multiple classes inherit from a single parent class.

---
⚠️ Note: Java doesn't support multiple inheritance with classes (to avoid ambiguity), but it supports multiple inheritance through interfaces.

## 🧠 Benefits of Inheritance
- Promotes code reuse.
- Enhances readability and maintainability.
- Reduces redundancy.
- Encourages polymorphism.

## Another Example 
```java
class Main{
  public static void main(String[] args){
    Dad d = new Dad();
    d.dadName = "Dany";
    System.out.println(d.dadName);
    d.dadProperty();

    Child c = new Child();
    c.childName = "Alen";
    c.childMoney = 20000;
    System.out.println(c.childName+" "+c.childMoney);
    c.childProperty();
  
    c.dadName = "Alex";  
    System.out.println(c.dadName);
    c.dadProperty();
    
    GrandChild gc = new GrandChild();
    gc.childProperty();
    gc.dadProperty();
  }
}

class Dad{
  String dadName;
  int dadMoney;
  
  void dadProperty(){
    System.out.println("This is the dad's property");
  }
}

class Child extends Dad{
  String childName;
  int childMoney;
  
  void childProperty(){
    System.out.println("This is the child's property");
  }
}

class GrandChild extends Child{
  String grandChildName;
  int grandChildMoney;
  
  void grandChildProperty(){
    System.out.println("This is the grandChild's property");
  }
}
```


### Output 
```nginx
Dany
This is the dad's property
Alen 20000
This is the child's property
Alex
This is the dad's property
This is the child's property
This is the dad's property

```