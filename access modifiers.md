# Java Access Modifiers

Java provides several keywords to control the **visibility** or **accessibility** of classes, variables, methods, and constructors. These are known as **Access Modifiers**.

## 🔑 Keywords Used

- `private`
- `default` (no modifier)
- `public`
- `protected` (not discussed here)

![]()


## 🔐 `private` Access Modifier

- A `private` member is **accessible only within the same class**.
- It is used to restrict access and encapsulate data.
- Ideal for internal logic, helper methods, or sensitive data.

### ✅ Use Case:
Suppose you're creating a bank account class. You want the user to see the loan interest but not change it directly. This can be handled with a private method or field.

### ✅ Example: Within the Same Class

```java
public class Dog {
    private String name;
    private int age;

    private int getAge() {
        return age;
    }

    public void showDetails() {
        System.out.println("Name: " + name);
        System.out.println("Age (via private method): " + getAge());
    }
}
```
### ❌ Example: Accessing private outside the class (Not Allowed)

```java
  public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        // d.age;          // ❌ Error: age has private access in Dog
        // d.getAge();     // ❌ Error: getAge() has private access in Dog
    }
}
```
## 🌐 default Access Modifier (Package-private)
- If no modifier is specified, the default access level is used.
- Members are accessible only within the same package.
- Cannot be accessed from a different package.

### ✅ Example: Within the Same Package
```java
  class Animal {
    String type = "Dog"; // default access

    void speak() {       // default access
        System.out.println("Animal speaks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Animal();
        System.out.println(a.type); // ✅ allowed
        a.speak();                  // ✅ allowed
    }
}
```
### ❌ Example: From Another Package (Not Allowed)
```java
  // In another package
import animals.Animal;

public class Zoo {
    public static void main(String[] args) {
        Animal a = new Animal();
        // a.type;     // ❌ Error: not public in Animal
        // a.speak();  // ❌ Error: not public in Animal
    }
}

```
## 🌍 public Access Modifier
- A public member is accessible from any other class across packages.
- Used when you want to expose the method or field universally.

### ✅ Example: Across Packages
```java
  package animals;

  public class Bird {
    public String name = "Parrot";

    public void fly() {
        System.out.println("Bird is flying");
    }
  }
```
```java
// In another package
import animals.Bird;

public class Main {
    public static void main(String[] args) {
        Bird b = new Bird();
        System.out.println(b.name); // ✅ allowed
        b.fly();                    // ✅ allowed
    }
}
```
## ✅ Best Practices
- Use private for internal logic and encapsulated data.
- Use default if the class is package-specific.
- Use public for APIs or utilities intended for external use.
