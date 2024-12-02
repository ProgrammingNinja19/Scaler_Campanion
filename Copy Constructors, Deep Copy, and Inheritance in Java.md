# Revision Notes on Copy Constructors, Deep Copy, and Inheritance in Java
## Introduction
In this session, we discussed several key concepts in object-oriented programming (OOP) with a focus on Java, including copy constructors, deep versus shallow copying, and inheritance. These concepts are crucial for effective memory management and code reusability in software engineering.

## Copy Constructor
### Definition
A copy constructor is a special type of constructor that creates a new object as a copy of an existing object. It is primarily used to duplicate objects where the values need to be copied rather than references.

### Implementation in Java
Instead of manually copying each field, a copy constructor simplifies this process. Here’s a basic structure:
```
public class Student {
    String name;
    int age;

    // Copy constructor
    public Student(Student other) {
        this.name = other.name;
        this.age = other.age;
    }
}
```
This constructor copies the name and age fields from the other student object to the new object. When you create a student using new Student(existingStudent), the existingStudent is passed to the copy constructor to populate the attributes.

### Usage
The copy constructor is used when a new object must be initialized to the same state as an existing object without affecting the original object by modification.

## Deep vs. Shallow Copy

### Shallow Copy
A shallow copy creates a new object, but instead of copying the elements, it only copies references to the objects. This means changes to the data in one object will reflect in another because they share the same memory references.

### Deep Copy
A deep copy involves creating a new instance of an object, including any objects referenced by the fields of the original object. The new copy is completely independent of the original. Here’s how a deep copy may look in implementation:

```
public class Student {
    String name;
    Exam enrollmentExam; // Suppose this is another class

    // Deep copy constructor
    public Student(Student other) {
        this.name = other.name;
        this.enrollmentExam = new Exam(other.enrollmentExam); // Assuming Exam also has a copy constructor
    }
}
```
Here, `other.enrollmentExam` is also deep copied, creating a completely independent `Exam` object.

#### When to Use Each
* **Shallow Copy**: Suitable when the objects being referenced do not need to change independently. For example, a batch of students in the same class can share the same batch details.
- **Deep Copy**: Required when the objects must change independently after duplication. This ensures no unintended side effects caused by shared references.

## Inheritance
### Definition
Inheritance allows classes to inherit properties and behaviors (methods) from another class. It is a cornerstone of OOP enabling code reusability and polymorphism.

### Usage
Inheritance is depicted by the keyword extends in Java:
```
public class Student extends User {
    // Student-specific fields and methods
}
```
Here, `Student` inherits from `User`, gaining access to `User’s` methods and properties.

### Constructor Calls in Inheritance
When a subclass is instantiated, constructors of its parent class(es) are invoked automatically to ensure proper initialization:

If the subclass constructor does not explicitly invoke a parent constructor, the default (no-argument) constructor of the parent is called.
### Private Members
Although private members are inherited, they are not accessible directly in the derived class. They require getters and setters for access.

## Conclusion
Understanding these concepts is fundamental to managing object life cycles and improving software architecture in Java. Proper use of copy constructors helps in precise memory management, while leveraging deep and shallow copies appropriately prevents potential bugs. Inheritance facilitates code reuse, making your codebase easier to maintain and extend.

These fundamental concepts, when used proficiently, enhance the robustness and efficiency of software engineering. Remember, the key choice between shallow and deep copy depends largely on whether independent object states are required post-copy.
