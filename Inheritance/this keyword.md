# `this` Keyword in Java

## What is `this`?
- `this` is a reference variable in java that refers to the **current object**.
- It is used to eliminate ambiguity between class attributes and parameters.
- and to call other constructors or methods from the same class. 

## Comoon Uses of `this`
- To refer to current class instance variable. 
- To invoke current class methods.
- To invoke current class constructor (constructor chaining). 
- To pass the current object as a parameter. 

## Example Code 

### Example 1
```java
class Student{
  private String name;
  private int age;
  
  public Student(String name, int age){
    this.name = name; // 'this' differentiates instance variable from constructor parameter.
    this.age = age;
  }
  
  public void display(){
    System.out.println("Name :"+ this.name); // referring to current object's 'name'
    System.out.println("Age :"+ this.age);  // referring to current object's 'age'
  }
}

class Main{
  public static void main(String[] args){
    Student s1 = new Student("Saurabh", 21);
    s1.display();
  }
}
```

### Output
```npgix
    Name: Saurabh
    Age: 21
```

### Explanation
- The constructor has parameters `name` and `age` that shadow the instance variables.
- Using `this.name` and `this.age` clarifies that we are assigning values to the instance variables, not just the parameters.
- Inside the `display()` method, `this` is used again for clarity and to refer to the current object's fields.

### Example 2
```java
class Student{
  private String name;
  private int age;
  
  public Student(String name, int age){
    this.name = name; // 'this' differentiates instance variable from constructor parameter.
    this.age = age;
  }
  
  public void display1(){
    System.out.println("This is display1 method");
    System.out.println("Name :"+ name); // referring to current object's 'name'
    this.display2();
  }
  
  public void display2(){
    System.out.println("This is display2 method");
    System.out.println("Age :"+ age);  // referring to current object's 'age'
  }
}

class Main{
  public static void main(String[] args){
    Student s1 = new Student("Saurabh", 21);
    s1.display1();
  }
}
```

### Output
```npgix
This is display1 method
Name :Saurabh
This is display2 method
Age :21
```

### Explanation 
- The constructor initializes the instance variables using `this` to avoid confusion with parameter names.
- `display1()` prints the name and then calls `display2()` using `this`, showing that one method can invoke another within the same object.
- `display2()` then prints the age of the student.
- This showcases the use of `this` both to differentiate variables and to invoke methods.

### 🧠 Summary
- `this` helps avoid naming conflicts.
- It is used to call instance methods and constructors from other constructors.
- Improves code clarity and represents the current object context.
