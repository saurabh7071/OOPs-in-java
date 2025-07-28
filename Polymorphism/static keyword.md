# Static Keyword in Java

## ⭐ What is `static` in java?

- The `static` keyword means the member belongs to the class itself, not to any object of the class. 
- So when you make something `static`, you can access it without creating an object of the class. 

## ☑️ Use Cases of `static` in Java

- **`static variable`**: Shared among all objects. Memory efficient
- **`static method`**: Can be called without object. Used for uitlity/helper methods. 
- **`static block`**: Used for static initialization(runs once when class loads.)
- **`static import`**: Allows direct access to static memebers of another class. 

## 🔶 Example Codes

### Static Variable Example(Shared across objects)

```java
class Student{
    String name;
    static String collageName;
}

class Main{
    public static void main(String[] args){
        Student s1 = new Student();
        Student s2 = new Student();

        s1.name = "Saurabh";
        Student.collageName = "GCOEY";
        s2.name = "Raj";

        System.out.println(s1.name);
        System.out.println(s2.name);
        System.out.println(Student.collageName);
    }
}
```
### Output
```
Saurabh
Raj
GCOEY
```

### Static Method

```java
class Student{
    static void details(String collegeName){
        System.out.println(collegeName);
    }
}

class Main{
    public static void main(String[] args){
        Student.details("GCOEY");
    }
}
```


### Output
```
GCOEY
```

### Static Block 

```java
class Student{
    static{
        System.out.println("This is Stack Block");
    }
    
    public static void main(String[] args){
        System.out.println("This is Main method");
    }
}
```

### Output

```
This is Stack Block
This is Main method
```

## 🤔 Can Static Access to Non-Static?

❌ No - Static doesn't know which non-static members you mean

### Example Code

```java
class Exmaple{
    int nonStaticVar = 20;
    static int staticVar = 20;

    static void staticMethod(){
        System.out.println(staticVar);  // ✅ Allowed
        System.out.println(nonStaticVar); // ❌ Error
    }
}
```

## Can Non-Static Access to Static?

✅ Yes - Static is shared and global; all instance can access it 

### Example Code

```java
class Student{
    void check(){
      details();
    }
    
    static void details(){
      System.out.println("This is details method");
    }
}

class Main{
   public static void main(String[] args){
        Student s1 = new Student();
        s1.check();
    }
}
```

```
This is details method
```

## 🔷 Why is `main()` method always static?

```java
public static void main(String[] args)
```

- Java starts program execution from `main()` method.
- But no object is created before `main()` starts, so it must be static
- Otherwise, JVM won't be able to call `main()` without making an object.

✅ So we write `public static void main(...)`