# Enum and Struct in C++

This guide explores the concepts of **enum** and **struct** in C++, providing explanations, syntax, examples, and common use cases.

---

## Table of Contents

1. [Enumeration (enum)](#1-enumeration-enum)
    - [What is an enum?](#what-is-an-enum)
    - [Defining and Using Enums](#defining-and-using-enums)
    - [Scoped Enum (enum class)](#scoped-enum-enum-class)
    - [Examples](#examples)
2. [Structures (struct)](#2-structures-struct)
    - [What is a struct?](#what-is-a-struct)
    - [Defining and Using Structs](#defining-and-using-structs)
    - [Struct vs Class](#struct-vs-class)
    - [Examples](#examples-1)
3. [Common Problems and Practice](#3-common-problems-and-practice)

---

## 1. Enumeration (enum)

### What is an enum?

An **enum** (short for enumeration) is a user-defined data type in C++ that consists of integral constants. Enums make your code more readable and less error-prone by replacing magic numbers with meaningful names.

---

### Defining and Using Enums

Syntax for defining an `enum`:

```cpp
enum EnumName {
    VALUE1,
    VALUE2,
    VALUE3
};
```

**Example:**

```cpp
enum Direction {
    NORTH,
    EAST,
    SOUTH,
    WEST
};

int main() {
    Direction dir = NORTH;

    if (dir == NORTH) {
        cout << "Heading North!";
    }
}
```

By default, the values start from 0 and increment by 1. You can also assign specific values:

```cpp
enum ErrorCode {
    SUCCESS = 0,
    WARNING = 1,
    ERROR = 2
};
```

---

### Scoped Enum (enum class)

In C++11 and later, **scoped enums** (`enum class`) are introduced. Scoped enums improve type safety by not allowing implicit conversion to integers.

**Syntax:**

```cpp
enum class EnumName {
    VALUE1,
    VALUE2,
    VALUE3
};
```

**Example:**

```cpp
enum class TrafficLight {
    RED,
    YELLOW,
    GREEN
};

int main() {
    TrafficLight light = TrafficLight::RED;

    if (light == TrafficLight::RED) {
        cout << "Stop!";
    }
}
```

---

### Examples

**Using Enums in Switch Cases:**

```cpp
#include <iostream>
using namespace std;

enum Weather {
    SUNNY,
    RAINY,
    CLOUDY
};

int main() {
    int choice;
    cout << "Enter weather condition (0 for Sunny, 1 for Rainy, 2 for Cloudy): ";
    cin >> choice;

    switch (choice) {
        case SUNNY:
            cout << "It's a sunny day!" << endl;
            break;
        case RAINY:
            cout << "It's raining outside." << endl;
            break;
        case CLOUDY:
            cout << "It's cloudy today." << endl;
            break;
        default:
            cout << "Invalid weather condition!" << endl;
    }

    return 0;
}

```

---

## 2. Structures (struct)

### What is a struct?

A **struct** in C++ is a user-defined data type that groups variables (of potentially different types) under a single name. Structures are useful for modeling real-world entities.

---

### Defining and Using Structs

**Syntax:**

```cpp
struct StructName {
    Type1 member1;
    Type2 member2;
    // Add more members as needed
};
```

**Example:**

```cpp
struct Point {
    int x;
    int y;
};

int main() {
    Point p1 = {10, 20};

    cout << "x: " << p1.x << ", y: " << p1.y;
}
```

---

### Struct vs Class

Both `struct` and `class` are used to define user-defined types in C++, but there are key differences:

| Feature       | struct       | class        |
|---------------|--------------|--------------|
| Default Access| public       | private      |
| Usage         | Simple data grouping | More functionality and OOP features |

---

### Examples

**Using Struct with Functions:**

```cpp
struct Rectangle {
    int length;
    int width;
};

int calculateArea(Rectangle rect) {
    return rect.length * rect.width;
}

int main() {
    Rectangle r = {5, 10};
    cout << "Area: " << calculateArea(r);
}
```

**Struct with Constructors:**

Constructors are special member functions that are called when an object of the struct is created. They are used to initialize the members of the struct when an object is declared. The constructor is called only once, when the object is created. The constructor has the same name as the structure and does not have a return type, not even void. The constructor is declared with the keyword `struct` followed by the name of the structure and the parameters in parentheses. The parameters are used to initialize the members of the struct.

```cpp
struct Circle {
    double radius;

    Circle(double r)
    {
        radius = r;
    }

    double area() {
        return 3.14 * radius * radius;
    }
};

int main() {
    Circle c(5.0);
    cout << "Area: " << c.area();
}
```

---

## 3. Common Problems and Practice

### Problem 1: Use Enum for Days of the Week

Define an `enum` for the days of the week and write a program that prints the day based on a user input.

```cpp
#include <iostream>
using namespace std;

enum Days {
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY,
    SUNDAY
};

int main() {
    int day;
    cout << "Enter a number (0-6): ";
    cin >> day;

    switch (day) {
        case MONDAY: cout << "Monday"; break;
        case TUESDAY: cout << "Tuesday"; break;
        case WEDNESDAY: cout << "Wednesday"; break;
        case THURSDAY: cout << "Thursday"; break;
        case FRIDAY: cout << "Friday"; break;
        case SATURDAY: cout << "Saturday"; break;
        case SUNDAY: cout << "Sunday"; break;
        default: cout << "Invalid input!";
    }
}
```

### Problem 2: Model a Student Using Struct

Define a `struct` for a student containing the name, age, and grade. Write a program that creates a student object and displays its data.

```cpp
#include <iostream>
using namespace std;

struct Student {
    string name;
    int age;
    char grade;
};

int main() {
    Student s = {"Ali Kazempour", 20, 'A'};

    cout << "Name: " << s.name << endl;
    cout << "Age: " << s.age << endl;
    cout << "Grade: " << s.grade << endl;
}
```

### Problem 3: Calculate User Age in Days

Write a program that takes two dates as input: the user's birth date and today's date. Then, calculate and display the user's age in days (e.g., "7825 days have passed since your birth").

```cpp
#include <iostream>
using namespace std;

struct Date {
    int year;
    int month;
    int day;
};

int calculateDays(Date birthDate, Date currentDate) {
    int days = 0;

    // Convert years to days
    days += (currentDate.year - birthDate.year) * 365;

    // Convert months to days (approximation)
    days += (currentDate.month - birthDate.month) * 30;

    // Add remaining days
    days += (currentDate.day - birthDate.day);

    return days;
}

int main() {
    Date birthDate, currentDate;

    cout << "Enter your birth date (year,month,day): ";
    cin >> birthDate.year >> birthDate.month >> birthDate.day;

    cout << "Enter today's date (year,month,day): ";
    cin >> currentDate.year >> currentDate.month >> currentDate.day;

    int ageInDays = calculateDays(birthDate, currentDate);

    cout << "You are " << ageInDays << " days old." << endl;

    return 0;
}
```

---

By understanding and practicing with enums and structs, you can create more organized, readable, and maintainable C++ programs.

