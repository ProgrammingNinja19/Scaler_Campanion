
# Comprehensive Revision Notes for Object-Oriented Programming (OOP)
## Introduction to Object-Oriented Programming
In this session, we explored key concepts in object-oriented programming (OOP) with a focus on Java. We'll cover what classes and objects are, the principles of encapsulation, constructors, and some tasks to solidify our understanding.

## Topics Covered:
1. Classes and Objects
2. Encapsulation
3. Hands-On Task: Bank Account Class
4. Constructors

## 1. Classes and Objects
### What is a Class?
A class in Java serves as a blueprint for creating objects. It defines the properties (data attributes) and behaviors (methods) for the objects.

- **Entities & Attributes:** For example, a Student entity might have attributes like ID, name, age, etc., and behaviors such as registering for a course.
* **Blueprint Analogy:** Like a building blueprint, defining a class doesn't construct objects; it merely sketches the potential for them 

### What is an Object?
An object is an instance of a class. Objects have their own state and behaviors.

+ **Creation**: To create an object, use the new keyword. For example: `Student student1 = new Student();`
- **Dot Operator**: Access object properties and methods using the dot operator: `student1.name = "John";`
### Example Code:
```
class Student {
    String name;
    int age;
    String course;

    void printDetails() {
        System.out.println("Name: " + name + ", Age: " + age + ", Course: " + course);
    }
}    

// Creating objects
Student student1 = new Student();
student1.name = "John Doe";
student1.age = 20;
student1.course = "Computer Science";
student1.printDetails();
```

## 2. Encapsulation
Definition:
Encapsulation refers to the bundling of data and methods that operate on that data into a single unit or class. It also restricts access to some of the object's components for better control and security.

Access Modifiers: Control access to class members using modifiers such as private, public, protected, and default.
Getters and Setters: These are methods used to access and update private data fields from outside the class【.
Example:
```
class BankAccount {
    private double balance;
    private String ownerName;

   // Getter
    public double getBalance() {
        return balance;
    }

    // Setter
    public void setBalance(double balance) {
        if (balance >= 0) {
            this.balance = balance;
        }
    }
}
```

## 3. Hands-On Task: Bank Account Class
Task Description:
Create a Java class named BankAccount with fields for balance (double) and ownerName (String). Implement deposit and withdraw methods with basic validation【6:12†transcript.txt】【6:18†handwritten.pdf】.

Deposit Method: Increase balance by the deposit amount, ensuring the amount is positive.
Withdraw Method: Decrease balance by the withdrawal amount, ensuring the balance does not become negative.
Example Code:
```
class BankAccount {
    private double balance;
    private String ownerName;

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }
}
```

## 4. Constructors
Definition:
A constructor is a special method in Java that is called when an object is instantiated. It initializes the new object.

Features:
Has the same name as the class.
No return type.
Initializes object attributes.
Constructor Overloading:
You can have multiple constructors with different parameters to initialize objects in different ways.

Example Code:
```
public class Student {
    String name;
    int age;

    // Default constructor
    public Student() {
        this.name = "Unknown";
        this.age = 0;
    }

    // Parameterized constructor
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```
By understanding these foundational concepts, you can effectively design and implement classes in Java, utilizing the powerful paradigm of object-oriented programming. Be sure to practice implementing these concepts in your development environment to deepen your understanding
