# Object Oriented Programming

Object-oriented programming aims to implement real-world entities like inheritance, hiding, polymorphism, etc. in programming.

It is a programming paradigm in which software design involves around data, or objects, rather than functions and logic.

Main aim of OOP is to bind together the data and the functions that operate on them so that no other part of the code can access this data except that function.

OOPs focuses on the objects that developer want to manipulate rather than logic required to manipulate them.

Some of the advantages of OOPs are:

-   Code Maintainability
-   Reusability
-   Security
-   Data Redundancy
-   Easy Troubleshooting
-   Polymorphism Flexibility

## Table of Content

-   [Class](#class)
-   [Object](#object)
-   [Encapsulation](#encapsulation)
-   [Abstraction](#abstraction)
-   [Polymorphism](#polymorphism)
-   [Inheritance](#inheritance)
-   [Static Functions And Virtual Functions](#static-functions-and-virtual-functions)
-   [Constructor and Destructor](#constructor-and-destructor)

## Class

It is user defined Data Type, which holds its own data members and member functions, which can be accessed and used by creating an instance of that class.

A class is like blueprint of the object, used as a template for creating objects of the identical type.

Data members are the data variables and member functions are the functions used to manipulate these variables together.

These data members and member functions define the properties and behavior of the objects in a Class.

Class do not take space in the memory.

Syntax:

```cpp
class className
{
    [access modifier]:
       [field declaration]
       [method declaration]
};
```

### Class VS Structure

| Class                                | Structure                                        |
| :----------------------------------- | :----------------------------------------------- |
| Collection of Objects.               | Collection of Variables of different Data Types. |
| Combine Data and Methods together.   | Used to Grouping Data.                           |
| Objects are created on Heap Memory   | Objects are created on Stack Memory.             |
| Inheritance Possible.                | Inheritance Not Possible.                        |
| Ideal for Larger or Complex Objects. | Ideal for Smaller and Isolated Model Objects.    |

## Object

Object is Real-World entity which have properties and functionality.

An object is the instance of the class, and memory is allocated corresponding to that object.

When a program executes, object interact by sending messages to other objects.

While communicating, object does not need to know the behavior of other objects, it is sufficient to know the type of message accepted and the type of response returned by the objects.

```cpp
className obj_reference; // Object Declaration
obj_reference = new className(); // Object Initialization
```

## Encapsulation

In normal terms, Encapsulation is defined as wrapping up data and information under a single unit.

In Object-Oriented Programming, Encapsulation is defined as binding together the data and the functions that manipulate them into the single place i.e. class.

Main Advantage of Encapsulation is that data is hidden and protected from access by outside non-member methods of a class.

Encapsulation also leads to data abstraction or data hiding. Using encapsulation also hides the data.

In encapsulation, data(variables) are declared as private and methods are declared as public.

### Access Specifiers

Allows us to restrict the scope or visibility of the characteristics and behavior of a class.

Three Type of Access Specifiers:

-   [Private](#private-modifier)
-   [Public](#public-modifier)
-   [Protected](#protected-modifier)

---

#### Public Modifier

-   Means that the class, variable, or method is accessible throughout from within or outside the class or package.

-   Provides Highest Level of Accessibility.

#### Private Modifier

-   Means that the class, variable, or method is accessible from within the class or package but not accessible from outside the class or package.

-   Provides Lowest Level of Accessibility.

#### Protected Modifier

-   Means that the class, variable, or method is accessible from within the class or package and also within sub-classes in the same package, but not from outside the package.

---

#### _Summarize Modifiers_

| Accessibility                              | Public | Private |            Protected             |
| :----------------------------------------- | :----: | :-----: | :------------------------------: |
| Accessible by classes in Same Package      |  Yes   |   No    |               Yes                |
| Accessible by classes in Other Package     |  Yes   |   No    |                No                |
| Accessible by sub-classes in Same Package  |  Yes   |   No    | Yes (But depends on Inheritance) |
| Accessible by sub-classes in Other Package |  Yes   |   No    | Yes(But depends on Inheritance)  |

## Abstraction

Abstraction means displaying only essential information and hiding the details.

It means providing only essential information about the data to the outside world, hiding the background details or implementation.

Data abstraction in programming language, the code implementation is hidden from the user and only the necessary functionality is shown or provided
to the user.

### Abstraction Using Classes

-   The class helps us to group data members and member functions using available access specifiers.
-   A Class can decide which data member will be visible to the outside world and which is not.

To achieve Data Abstraction using:

-   **Abstract Class**

    -   Abstract Class contain abstract methods
    -   Abstract Methods can only be declared not implemented.
    -   An abstract class is a class that either defines or inherits at least one function for which the final override is a [_pure virtual function_](#pure-virtual-function).
    -   Declared with abstract keyword.
    -   Can also have non-abstract methods.
    -   Cannot create Instance of Abstract Class.

-   **Interface**

    -   Collection of Abstract Method(Methods without definition).
    -   Cant Instantiate an interface.
    -   Abstract Method of Interface needs to be overridden in its child classes
    -   Supports multiple inheritance.
    -   Cant be Extended by class, it can only be implemented by class.
    -   Syntax:

        ```cpp
        // Interface(Abstract class
        // with pure virtual function)
        class Atom
        {
        public:
            virtual string returnString() = 0;
        };

        // Interface needs to be implemented
        class Atharva : public Atom
        {
        public:
            string returnString()
            {
            return "Atharva is Atom";
            }
        };
        ```

### Data Abstraction VS Encapsulation

| Data Abstraction                                                               | Encapsulation                                             |
| :----------------------------------------------------------------------------- | :-------------------------------------------------------- |
| Hide unnecessary information from user and only show the necessary information | Combine Data and Function inside single unit, i.e. CLASS. |
| Implemented using abstract class and interfaces                                | Implemented using access modifiers.                       |
| Implemented at Design or Interface Level.                                      | Implemented at Implementation Level.                      |

## Polymorphism

The word polymorphism means having many forms of single entity.

In simple words, we can define polymorphism as the ability of a message to be displayed in more than one form. A person at the same time can have different characteristics.

A man at the same time is a father, a husband, and an employee. So the same person possesses different behavior in different situations.

It is a process of performing a single task in different ways. One Method have different forms based on the type of parameter, order of parameters, and number of parameters.

In simple words, polymorphism is the ability of an object to take many forms.

### Two Type of Polymorphism

-   [Compile Time Polymorphism](#compile-time-polymorphism)
-   [Run Time Polymorphism](#run-time-polymorphism)

#### Compile Time Polymorphism

-   Takes place during Compile Time.
-   Called Static Polymorphism or Early Binding.
-   Class contain multiple methods having same name but different signature.
-   Example : [Method Overloading](#method-overloading), [Operator Overloading](#operator-overloading).

#### Run Time Polymorphism

-   Takes place during Run Time.
-   Called Dynamic Polymorphism or Late Binding.
-   Refers to a process when a call to an overridden process is resolved at run time.
-   Sub class and Base class both contain methods having same name but different functionalities.
-   Example: [Method Overriding](#method-overriding)

#### Method Overloading

-   Class Contain multiple method having same name but different signature.
-   Multiple methods of same names performs different tasks within same class.
-   Depends upon number and type of arguments.
-   Does not depends on return type of the method.
-   Example of Compile Time Polymorphism.
-   Ex:

```cpp
#include <iostream>
using namespace std;

void add(int a, int b)
{
  cout << "sum = " << (a + b);
}

void add(double a, double b)
{
    cout << "fraction sum = " << (a + b);
}
```

#### Method Overriding

-   Base Class contains a method and Sub Class also contains the same name and same signature method of its parent class.
-   Used to provide specific implementation of the method which is already provided by its Super Class.
-   Example of Run Time Polymorphism.

```cpp
// C++ Program to illustrate how to implement runtime
// function overriding using virtual function
#include <iostream>
using namespace std;

class Base {
public:
    // Declare the function as virtual to allow overriding
    // in derived classes
    virtual void display()
    {
        cout << "Atom Displaying method of Base class" << endl;
    }

    // Virtual destructor to ensure proper cleanup of
    // derived class objects
    virtual ~Base() {}
};

class Derived : public Base {
public:
    // Override the display method
    void display() override
    {
        cout << "Atom Displaying method of Derived class" << endl;
    }
};

int main()
{
    Base* basePtr;
    Derived derivedObj;

    // Point base class pointer to derived class object
    basePtr = &derivedObj;

    // Call the display function
    // This will call the display method of the Derived
    // class due to the virtual function mechanism
    basePtr->display();

    return 0;
}
```

```
Output:
Atom Displaying method of Derived class
```

#### Operator Overloading

-   Operator is overloaded to provide the special meaning of user-defined data type.
-   Example of Compile Time Polymorphism.

```cpp
// C++ Program to Demonstrate
// Operator Overloading
#include <iostream>
using namespace std;

class Complex {
private:
    int real, imag;

public:
    Complex(int r = 0, int i = 0)
    {
        real = r;
        imag = i;
    }

    // This is automatically called when '+' is used with
    // between two Complex objects
    Complex operator+(Complex const& obj)
    {
        Complex res;
        res.real = real + obj.real;
        res.imag = imag + obj.imag;
        return res;
    }
    void print() { cout << real << " + i" << imag << '\n'; }
};

int main()
{
    Complex c1(10, 5), c2(2, 4);
    Complex c3 = c1 + c2;
    c3.print();
}
```

```
Output:
12 + i9
```

## Inheritance

Capability of a class to derive properties and characteristics from another class is called Inheritance.

In other words, A class inherits data fields or methods from another class.

Helps to write redundant free code and also reduces code length.

**For eg.** Animal is a class and other classes like Dog, cat etc. can inherit the common properties of animal class.

Reduces development and maintenance cost of code.

### Sub-Class

-   Class which inherits other class.
-   Sub Class is a class which inherits the properties and behavior of super class.
-   Also known as Child class or Derived class.

### Super-Class

-   Class which is inherited by other class.
-   Super Class is a class from which Sub Class inherits the properties and behaviors.
-   Also called Base class or Parent Class.

### Types of Inheritance

-   [Single Inheritance](#single-inheritance)
-   [Multiple Inheritance](#multiple-inheritance)
-   [Multilevel Inheritance](#multilevel-inheritance)
-   [Hierarchical Inheritance](#hierarchical-inheritance)
-   [Hybrid Inheritance](#hybrid-inheritance)

---

#### Single Inheritance

-   Class inherits properties and behavior of only one class.

-   In other worlds, there is only one base class and only one sub class.

-   Example : `A --> B`

#### Multiple Inheritance

-   Class inherits properties and behavior of more than one class.

-   Only one Sub class but more than one Super class.

-   Java doesn't support multiple inheritance. [Why?](#java-and-multiple-inheritance)

-   Example : `A --> D, B --> D, C --> D`

#### Multilevel Inheritance

-   Class inherits other class and then that inherited class further inherited by other class.

-   Sub class contains properties of base class as well as properties of base class of its base class

-   Example : `A --> B --> C`

#### Hierarchical Inheritance

-   More than one class inherits the properties and behavior of One Class.

-   Only one Parent Class but many Child Classes.

-   Example : `A --> B, A --> C`

#### Hybrid Inheritance

-   Combination of more than one type of inheritance.

---

#### _Java and Multiple Inheritance_

-   Ambiguity around the [diamond problem](https://www.youtube.com/watch?v=mEF_vVNTPUY).

-   Complicates the design and creates problem during casting, constructor chaining, etc.

-   So to simplify the language and reduce code complexity, java doest support multiple inheritance.

## Static Functions And Virtual Functions

Some Special type of functions in OOPs:

### Static Function

-   Those Functions that can be called without creating the object of the class.
-   Do not use any instance variable of the object of the class they are defined in.
-   Cannot be overridden.
-   Stored inside Heap Space of Memory.

### Virtual Function

-   Function or Method used to override the behavior of the function in an inherited class with the same signature to achieve polymorphism.
-   These Functions are defined in base class and overridden in the inherited class.
-   Cannot be private, as they need to be overridden.
-   Achieve [Run Time Polymorphism](#run-time-polymorphism).

### Pure Virtual Function

-   Function which have no definition. This means, virtual function that doesn't need implementation.

-   Have not definition but we must override that function in the derived class, otherwise the derived class become [abstract class](#abstraction).

## Constructor and Destructor

### Constructor

-   Special type of Member function, used to initialize the object.

-   Have same name as class name and must have no explicit return type.

-   Called when object is created, and at that time, memory is allocated for the object.

-   Constructor is used to assign values to the class variables at time of object creation.

### Type of Constructors

-   [Default Constructor](#default-constructor)
-   [Parameterized Constructor](#parameterized-constructor)
-   [Copy Constructor](#copy-constructor)
-   [Static Constructor](#static-constructor)
-   [Private Constructor](#private-constructor)

---

#### Default Constructor

-   Constructor with 0 Parameter.

#### Parameterized Constructor

-   Constructor having argument list or parameter list
-   Used to initialize the data variables.

#### Copy Constructor

-   Constructor which use existing object to create new object of same class.
-   Copies the values of variables from one object to another.

#### Static Constructor

-   Automatically called when first instance is generated, or any static member is referenced.
-   Explicitly declared using static keyword.
-   Not Supported in JAVA.

#### Private Constructor (NOT IMP)

-   JAVA enables us to declare Constructor private using private access modifier.
-   Cannot create an object of the class.
-   Use this private constructor in Singleton Design Pattern.

---

### Destructor

-   Member Function which is used to destroy an object.
-   Called automatically when object goes out of scope, or its explicitly called to delete.
-   Have Same name as class with preceded by **Tilde(~)**.

### Constructor Overloading

-   Constructor may or may not have arguments and it does not have a return type.

-   Thus is eligible for [method overloading](#method-overloading)

-   Here constructor method is overloaded based on arguments having different functionality.

---

&copy; Atharva Sugandhi 2024
