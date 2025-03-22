
# Object-Oriented Programming (OOP) in C++

**Object-Oriented Programming (OOP)** in C++ is a way of writing programs by modeling real-world things as **objects**. These objects come from **classes**, which act like templates. OOP helps us organize code better, reuse it, and make it easier to understand and fix.

---

## Table of Contents

1. [Introduction to OOP](#1-introduction-to-oop)
2. [Core Concepts of OOP](#2-core-concepts-of-oop)
   - [Classes and Objects](#21-classes-and-objects)
   - [Encapsulation](#22-encapsulation)
   - [Inheritance](#23-inheritance)
   - [Polymorphism](#24-polymorphism)
   - [Abstraction](#25-abstraction)
3. [Syntax of a Class](#3-syntax-of-a-class)
4. [Constructors and Destructors](#4-constructors-and-destructors)
5. [Setters and Getters](#5-setters-and-getters)
6. [Access Specifiers](#6-access-specifiers)
7. [Types of Inheritance](#7-types-of-inheritance)
8. [Function Overriding and Virtual Functions](#8-function-overriding-and-virtual-functions)
9. [Problems and Practice](#9-problems-and-practice)
10. [Summary](#10-summary)

---

## 1. Introduction to OOP

Imagine you’re building a game with characters like warriors, wizards, and dragons. Instead of writing separate code for each, OOP lets you create a "template" (class) for a character and then make specific versions (objects) with their own traits. This makes your code organized, reusable, and easier to update.

### Why Use OOP?
- **Real-World Modeling**: Code mimics how things work in life (e.g., a "Car" class for cars).
- **Reusability**: Write once, use many times.
- **Easier Debugging**: Problems are isolated to specific objects or classes.
- **Teamwork**: Different people can work on different classes.

---

## 2. Core Concepts of OOP

Let’s break down the five big ideas of OOP with examples students can relate to.

---

### 2.1 Classes and Objects

- **Class**: A blueprint or plan (e.g., a recipe for a cake).
- **Object**: The actual thing made from the blueprint (e.g., a baked cake).

#### Detailed Explanation:
Think of a class as a form you fill out for a student: it has fields like "name," "age," and "grade." An object is a specific student filling out that form, like "Alex, 15, A."

#### Example 1: Simple Student Class
```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    int age;

    void introduce() {
        cout << "Hi, I’m " << name << " and I’m " << age << " years old!" << endl;
    }
};

int main() {
    Student student1;  // Object 1
    student1.name = "Alex";
    student1.age = 15;
    student1.introduce();  // Output: Hi, I’m Alex and I’m 15 years old!

    Student student2;  // Object 2
    student2.name = "Maya";
    student2.age = 16;
    student2.introduce();  // Output: Hi, I’m Maya and I’m 16 years old!
    return 0;
}
```

#### Example 2: Pet Class
```cpp
#include <iostream>
using namespace std;

class Pet {
public:
    string type;
    string sound;

    void makeSound() {
        cout << "The " << type << " says " << sound << "!" << endl;
    }
};

int main() {
    Pet dog;
    dog.type = "Dog";
    dog.sound = "Woof";
    dog.makeSound();  // Output: The Dog says Woof!

    Pet cat;
    cat.type = "Cat";
    cat.sound = "Meow";
    cat.makeSound();  // Output: The Cat says Meow!
    return 0;
}
```

---

### 2.2 Encapsulation

- **Encapsulation**: Keeping data safe by hiding it and controlling access through methods (like locking a diary and giving a key only to trusted people).

#### Detailed Explanation:
Imagine a bank account. You don’t want anyone changing your balance directly—they should use a "deposit" or "withdraw" method. Encapsulation uses **private** data and **public** methods to enforce this.

#### Example 1: Bank Account
```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    double balance;  // Hidden from outside
public:
    BankAccount() { balance = 0; }  // Start with zero
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            cout << "Deposited $" << amount << endl;
        }
    }
    double getBalance() {
        return balance;  // Safe way to see balance
    }
};

int main() {
    BankAccount account;
    account.deposit(100.50);
    cout << "Current balance: $" << account.getBalance() << endl;  // Output: Deposited $100.5, Current balance: $100.5
    // account.balance = 1000;  // Error! balance is private
    return 0;
}
```

#### Example 2: Phone Battery
```cpp
#include <iostream>
using namespace std;

class Phone {
private:
    int battery;  // Hidden
public:
    Phone() { battery = 100; }  // Full battery at start
    void usePhone(int percent) {
        if (percent > 0 && battery >= percent) {
            battery -= percent;
            cout << "Used " << percent << "% battery." << endl;
        }
    }
    int checkBattery() {
        return battery;
    }
};

int main() {
    Phone myPhone;
    myPhone.usePhone(30);
    cout << "Battery left: " << myPhone.checkBattery() << "%" << endl;  // Output: Used 30% battery, Battery left: 70%
    return 0;
}
```

---

### 2.3 Inheritance

- **Inheritance**: A class "borrows" features from another class (like a child inheriting traits from a parent).

#### Detailed Explanation:
Think of a "Vehicle" class with basic features like "move." A "Car" class can inherit "move" and add its own feature, like "honk." This saves time and keeps code connected.

#### Example 1: Animals
```cpp
#include <iostream>
using namespace std;

class Animal {  // Parent class
public:
    void eat() {
        cout << "I can eat!" << endl;
    }
};

class Bird : public Animal {  // Child class
public:
    void fly() {
        cout << "I can fly!" << endl;
    }
};

int main() {
    Bird sparrow;
    sparrow.eat();  // From Animal
    sparrow.fly();  // From Bird
    // Output: I can eat!, I can fly!
    return 0;
}
```

#### Example 2: School Roles
```cpp
#include <iostream>
using namespace std;

class Person {
public:
    string name;
    void introduce() {
        cout << "I am " << name << "." << endl;
    }
};

class Teacher : public Person {
public:
    void teach() {
        cout << name << " is teaching!" << endl;
    }
};

int main() {
    Teacher t;
    t.name = "Mrs. Smith";
    t.introduce();  // Output: I am Mrs. Smith.
    t.teach();      // Output: Mrs. Smith is teaching!
    return 0;
}
```

---

### 2.4 Polymorphism

- **Polymorphism**: One name, many forms—like a "play" button working differently for music or a game.

#### Detailed Explanation:
Polymorphism can happen in two ways:
1. **Overloading**: Same method name, different inputs (e.g., `add(2, 3)` vs. `add(2.5, 3.5)`).
2. **Overriding**: A child class changes a parent’s method.

#### Example 1: Overloading (Calculator)
```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) {
        return a + b;
    }
    double add(double a, double b) {
        return a + b;
    }
    int add(int a, int b, int c) {
        return a + b + c;
    }
};

int main() {
    Calculator calc;
    cout << calc.add(2, 3) << endl;      // Output: 5
    cout << calc.add(2.5, 3.5) << endl;  // Output: 6
    cout << calc.add(1, 2, 3) << endl;   // Output: 6
    return 0;
}
```

#### Example 2: Overriding (Animals)
```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    void sound() {
        cout << "Some generic sound" << endl;
    }
};

class Cat : public Animal {
public:
    void sound() {  // Overrides parent’s method
        cout << "Meow!" << endl;
    }
};

int main() {
    Cat kitty;
    kitty.sound();  // Output: Meow!
    return 0;
}
```

---

### 2.5 Abstraction

- **Abstraction**: Showing only what’s needed and hiding the "how" (like using a TV remote without knowing its circuits).

#### Detailed Explanation:
Abstraction often uses **abstract classes** with **pure virtual functions** (methods with no body) to force child classes to define them.

#### Example 1: Shape Drawing
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual void draw() = 0;  // Pure virtual: must be overridden
};

class Triangle : public Shape {
public:
    void draw() override {
        cout << "Drawing a triangle: /\\" << endl;
    }
};

int main() {
    Triangle t;
    t.draw();  // Output: Drawing a triangle: /\  
    return 0;
}
```

#### Example 2: Game Character
```cpp
#include <iostream>
using namespace std;

class Character {
public:
    virtual void attack() = 0;  // Abstract method
};

class Warrior : public Character {
public:
    void attack() override {
        cout << "Swinging a sword!" << endl;
    }
};

int main() {
    Warrior w;
    w.attack();  // Output: Swinging a sword!
    return 0;
}
```

---

## 3. Syntax of a Class

Here’s the basic layout:
```cpp
class ClassName {
private:
    // Data only this class can touch
public:
    // Stuff anyone can use
protected:
    // Stuff this class and its kids can use
};
```

---

## 4. Constructors and Destructors

- **Constructor**: Runs when an object is born (sets it up).
- **Destructor**: Runs when an object dies (cleans up).

#### Detailed Explanation:
Constructors can take parameters to customize objects. Destructors ensure no mess is left behind (e.g., freeing memory).

#### Example 1: Book Class
```cpp
#include <iostream>
using namespace std;

class Book {
public:
    string title;
    Book(string t) {  // Constructor with parameter
        title = t;
        cout << "Book '" << title << "' created!" << endl;
    }
    ~Book() {  // Destructor
        cout << "Book '" << title << "' destroyed!" << endl;
    }
};

int main() {
    Book b("Harry Potter");
    // Output: Book 'Harry Potter' created!
    return 0;  // Output: Book 'Harry Potter' destroyed!
}
```

#### Example 2: Student with ID
```cpp
#include <iostream>
using namespace std;

class Student {
public:
    int id;
    Student(int i) : id(i) {  // Constructor with initialization list
        cout << "Student ID " << id << " enrolled." << endl;
    }
    ~Student() {
        cout << "Student ID " << id << " graduated!" << endl;
    }
};

int main() {
    Student s(123);
    // Output: Student ID 123 enrolled., Student ID 123 graduated!
    return 0;
}
```

--- 

## 5. Setters and Getters

- **Setter**: A function to set the value of a private data member.
- **Getter**: A function to get the value of a private data member.

#### Detailed Explanation:
Setters and getters provide controlled access to private data members. They help maintain **encapsulation** and allow validation when setting values.

#### Example 1: Student Class with Setters and Getters
```cpp
#include <iostream>
using namespace std;

class Student {
private:
    string name;
    int age;

public:
    string getName() const {
        return name;
    }
    
    void setName(const string& n) {
        name = n;
    }
    
    int getAge() const {
        return age;
    }
    
    void setAge(int a) {
        if (a > 0) {  // Validation to ensure age is positive
            age = a;
        }
    }
};

int main() {
    Student student;
    
    student.setName("Alex");
    student.setAge(20);
    
    cout << "Name: " << student.getName() << endl;  // Output: Name: Alex
    cout << "Age: " << student.getAge() << endl;    // Output: Age: 20
    
    student.setAge(-5);  // Output: Invalid age!
    
    return 0;
}
```

---

## 6. Access Specifiers

| Specifier   | Who Can Access?                |
|-------------|--------------------------------|
| `public`    | Everyone (outside too)         |
| `private`   | Only this class (default)      |
| `protected` | This class and its children    |

#### Example:
```cpp
#include <iostream>
using namespace std;

class Test {
private:
    int secret = 42;
protected:
    int familySecret = 100;
public:
    int open = 5;
};

class Child : public Test {
public:
    void show() {
        // cout << secret << endl;  // Error: private
        cout << "Family secret: " << familySecret << endl;  // OK: protected
        cout << "Open: " << open << endl;  // OK: public
    }
};

int main() {
    Test t;
    Child c;
    cout << t.open << endl;  // Output: 5
    c.show();  // Output: Family secret: 100, Open: 5
    return 0;
}
```

---

## 7. Types of Inheritance

- **Single**: One parent, one child.
- **Multiple**: One child, many parents.
- **Multilevel**: Grandparent → Parent → Child.

#### Example 1: Multiple Inheritance (Robot)
```cpp
#include <iostream>
using namespace std;

class Motor {
public:
    void run() { cout << "Motor running" << endl; }
};

class Sensor {
public:
    void scan() { cout << "Scanning environment" << endl; }
};

class Robot : public Motor, public Sensor {};

int main() {
    Robot r;
    r.run();   // Output: Motor running
    r.scan();  // Output: Scanning environment
    return 0;
}
```

#### Example 2: Multilevel (Family)
```cpp
#include <iostream>
using namespace std;

class Grandparent {
public:
    void wisdom() { cout << "I have wisdom!" << endl; }
};

class Parent : public Grandparent {};

class Child : public Parent {};

int main() {
    Child c;
    c.wisdom();  // Output: I have wisdom!
    return 0;
}
```

---

## 8. Function Overriding and Virtual Functions

- **Overriding**: Child redefines parent’s method.
- **Virtual**: Ensures the right method runs at runtime.

#### Detailed Explanation:
Without `virtual`, a parent pointer calls the parent’s method. With `virtual`, it calls the child’s method.

#### Example 1: Virtual Function
```cpp
#include <iostream>
using namespace std;

class Parent {
public:
    virtual void speak() {
        cout << "Parent speaking" << endl;
    }
};

class Child : public Parent {
public:
    void speak() override {
        cout << "Child speaking" << endl;
    }
};

int main() {
    Parent* ptr;
    Child c;
    ptr = &c;
    ptr->speak();  // Output: Child speaking (virtual works!)
    return 0;
}
```

#### Example 2: Game Enemies
```cpp
#include <iostream>
using namespace std;

class Enemy {
public:
    virtual void attack() {
        cout << "Generic attack" << endl;
    }
};

class Zombie : public Enemy {
public:
    void attack() override {
        cout << "Bites you!" << endl;
    }
};

int main() {
    Enemy* e = new Zombie();
    e->attack();  // Output: Bites you!
    delete e;
    return 0;
}
```

---

## 9. Problems and Practice

### Problem 1: Create a Class for a Laptop
```cpp
#include <iostream>
using namespace std;

class Laptop {
private:
    int battery;
public:
    Laptop() { battery = 100; }
    void charge() { battery = 100; cout << "Battery full!" << endl; }
    void use(int percent) {
        if (battery >= percent) {
            battery -= percent;
            cout << "Battery now at " << battery << "%" << endl;
        }
    }
};

int main() {
    Laptop myLaptop;
    myLaptop.use(40);  // Output: Battery now at 60%
    myLaptop.charge(); // Output: Battery full!
    return 0;
}
```

### Problem 2: Inheritance with Sports
```cpp
#include <iostream>
using namespace std;

class Sport {
public:
    string name = "Generic Sport";
    void play() { cout << "Playing " << name << endl; }
};

class Soccer : public Sport {
public:
    Soccer() { name = "Soccer"; }
    void kick() { cout << "Kicking the ball!" << endl; }
};

int main() {
    Soccer s;
    s.play();  // Output: Playing Soccer


    s.kick();  // Output: Kicking the ball!
    return 0;
}
```

### Problem 3: Polymorphism with Shapes
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual int area() = 0;
};

class Rectangle : public Shape {
private:
    int width, height;
public:
    Rectangle(int w, int h) : width(w), height(h) {}
    int area() override { return width * height; }
};

class Circle : public Shape {
private:
    int radius;
public:
    Circle(int r) : radius(r) {}
    int area() override { return 3.14 * radius * radius; }  // Approx PI
};

int main() {
    Rectangle r(4, 5);
    Circle c(3);
    cout << "Rectangle Area: " << r.area() << endl;  // Output: 20
    cout << "Circle Area: " << c.area() << endl;     // Output: 28 (approx)
    return 0;
}
```

---

## 10. Summary

| OOP Concept       | What It Does                                      | Example                 |
|-------------------|--------------------------------------------------|-------------------------|
| **Class/Object**  | Defines blueprints and creates instances.         | `Student` → `Alex`      |
| **Encapsulation** | Hides data, controls access with methods.         | Private `balance`       |
| **Inheritance**   | Reuses code from a parent class.                  | `Animal` → `Dog`        |
| **Polymorphism**  | Same name, different actions (overloading/overriding). | `add(int)` vs. `add(double)` |
| **Abstraction**   | Hides details, shows essentials.                  | `Shape` with `draw()`   |

---

### Teaching Tips
- **Start Simple**: Use `Classes and Objects` with everyday examples (pets, students).
- **Build Up**: Add encapsulation, then inheritance, etc., with relatable analogies.
- **Hands-On**: Let students modify examples or create their own (e.g., a "Game" class).
- **Visuals**: Draw class hierarchies (e.g., `Animal` → `Bird`) on a board.

