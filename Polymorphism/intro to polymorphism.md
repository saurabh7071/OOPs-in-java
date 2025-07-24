# 📘 Polymorphism in Java 

> "Poly" means many and "morph" means forms 

- Polymorphism is on of the four fundamental OOP concepts 
- It allows some code/method to take multiple forms. 
- Polymorphism means that a single action can behave differently based on the object that is invoking it. 

## Types of Polymorphism

1. _Compile-time Polymorphism (Method Overloading)_

2. _Runtime Polymorphism (Method Overriding)_

## 🌟 Use Case:

> Suppose you are developing a payment sysem that allows users to pay via credit card, debit card or UPI. The common method is `makePayment()`, but its implementation differs based on the payment method. Polymorphism allows you to define this behavior efficiently. 

## 🔶 Real-life Example 

> Consider a "Remote Control" as the base class. Different brands (Sumsung, Sony, LG) act as subclasses and override the `pressPowerButton()` method differently depending on the brand's behavior. Yet, all can be controllerd through a common reference type. 

## ✅ Advantages of Polymorphism

- Code Reusability
- Reduces complexity
- Supports Scalability 
- Helps achieve loose coupling 