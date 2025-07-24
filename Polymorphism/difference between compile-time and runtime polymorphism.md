# 💔 Difference Between Compile-Time and Runtime Polymorphism in Java

| Feature                         | Compile-Time Polymorphism                      | Runtime Polymorphism                      |
|---------------------------------|------------------------------------------------|-------------------------------------------|
| **Also Known As**              | Static Polymorphism / Method Overloading       | Dynamic Polymorphism / Method Overriding  |
| **Method Resolution**          | At **compile time**                            | At **runtime**                            |
| **Based On**                   | Method signature (method name + parameters)    | Object type and overridden method         |
| **Inheritance Required**       | ❌ Not required                                 | ✅ Required                                |
| **Flexibility**                | Less flexible                                  | More flexible                             |
| **Performance**                | Faster (no overhead at runtime)                | Slightly slower (requires dynamic dispatch) |
| **Use Case**                   | Code clarity and reuse through overloading     | Achieving behavior based on object type   |
| **Example**                    | `add(int a, int b)` vs `add(double a, double b)` | `Animal.sound()` overridden by `Dog.sound()` |

