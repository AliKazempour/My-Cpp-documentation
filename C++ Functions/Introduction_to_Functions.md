# Functions in C++

A **function** in C++ is a reusable block of code designed to perform a specific task. Functions help in modularizing the code, making it easier to read, debug, and reuse.

---

## Table of Contents

1. [Introduction to Functions](#1-introduction-to-functions)
2. [Syntax of a Function](#2-syntax-of-a-function)
3. [Function Declaration and Definition](#3-function-declaration-and-definition)
4. [Calling a Function](#4-calling-a-function)
5. [Function Parameters](#5-function-parameters)
   - [Pass by Value](#51-pass-by-value)
   - [Pass by Reference](#52-pass-by-reference)
6. [Return Statement](#6-return-statement)
7. [Types of Functions](#7-types-of-functions)
   - [Built-in Functions](#71-built-in-functions)
   - [User-Defined Functions](#72-user-defined-functions)
   - [Void Functions](#73-void-functions)
   - [Parameterized Functions](#74-parameterized-functions)
   - [Default Arguments in Functions](#75-default-arguments-in-functions)
   - [Recursive Functions](#76-recursive-functions)
   - [Function Overloading](#77-function-overloading)
8. [Problems and Practice](#8-problems-and-practice)
9. [Summary](#9-summary)

---

## 1. Introduction to Functions

A **function** is a self-contained block of code that performs a specific task. By using functions, you can avoid code duplication, organize your program, and make debugging easier.

### Advantages of Functions:

- Improves **modularity** and code structure.
- Promotes **code reusability**.
- Simplifies debugging and maintenance.
- Enhances program readability.

---

## 2. Syntax of a Function

The general syntax of a function in C++ is:

```cpp
returnType functionName(parameters) {
    // Function body
    // Code to execute
    return value;  // Optional return statement
}
```

---

## 3. Function Declaration and Definition

### Function Declaration and Definition

| Term | Description |
| --- | --- |
| **Function Declaration** | A **function declaration** introduces the function's name, return type, and parameter types to the compiler, serving as a blueprint or prototype. It tells the compiler what the function will look like without providing the actual implementation. |
| **Function Definition** | A **function definition** provides the complete implementation of the function, including the specific operations or tasks it performs. This is where the actual code resides that is executed when the function is called. |
```cpp
int add(int a, int b) {  // Definition
    return a + b;
}
```

---

## 4. Calling a Function

To execute a function, you "call" it by using its name and passing the required arguments.

### Example:

```cpp
#include <iostream>
using namespace std;

int add(int a, int b);  // Function declaration

int main() {
    int result = add(5, 3);  // Function call
    cout << "The sum is: " << result;  // Output: 8
    return 0;
}

int add(int a, int b) {  // Function definition
    return a + b;
}
```

---

## 5. Function Parameters

### 5.1 Pass by Value

When arguments are passed **by value**, a copy of the variable is sent to the function. Changes made to the parameter inside the function do not affect the original variable.

```cpp
#include <iostream>
using namespace std;

void changeValue(int x) {
    x = 10;  // Modifies only the copy of x
}

int main() {
    int a = 5;
    changeValue(a);
    cout << "Value of a: " << a;  // Output: 5
    return 0;
}
```

---

### 5.2 Pass by Reference

In **pass by reference**, the function receives the memory address of the argument, so changes made inside the function affect the original variable.

```cpp
#include <iostream>
using namespace std;

void changeValue(int &x) {  // Pass by reference
    x = 10;  // Changes the original variable
}

int main() {
    int a = 5;
    changeValue(a);
    cout << "Value of a: " << a;  // Output: 10
    return 0;
}
```

---

## 6. Return Statement

The `return` statement is used to return a value from a function.

### Example:

```cpp
#include <iostream>
using namespace std;

int square(int x) {
    return x * x;  // Return the square of x
}

int main() {
    int num = 4;
    cout << "Square of " << num << ": " << square(num);  // Output: 16
    return 0;
}
```

---

## 7. Types of Functions

---

### 7.1 Built-in Functions

C++ provides many predefined functions in its libraries, such as:

- `sqrt()` to calculate the square root.
- `pow()` to calculate powers.
- `abs()` to find absolute values.

#### Example:

```cpp
#include <iostream>
#include <cmath>  // For math functions
using namespace std;

int main() {
    cout << "Square root of 16 is: " << sqrt(16) << endl;  // Output: 4
    cout << "2 raised to 3 is: " << pow(2, 3) << endl;  // Output: 8
    cout << "Absolute value of -7 is: " << abs(-7) << endl;  // Output: 7
    return 0;
}
```

---

### 7.2 User-Defined Functions

Functions created by the programmer are called **user-defined functions**.

#### Example:

```cpp
#include <iostream>
using namespace std;

int add(int a, int b) {  // User-defined function
    return a + b;
}

int main() {
    cout << "Sum: " << add(4, 5);  // Output: 9
    return 0;
}
```

---

### 7.3 Void Functions

A **void function** does not return any value.

#### Example:

```cpp
#include <iostream>
using namespace std;

void greet() {  // Void function
    cout << "Hello, welcome to C++!" << endl;
}

int main() {
    greet();
    return 0;
}
```

---

### 7.4 Parameterized Functions

A **parameterized function** takes inputs (parameters) to perform its task.

#### Example:

```cpp
#include <iostream>
using namespace std;

int multiply(int a, int b) {
    return a * b;
}

int main() {
    cout << "Multiplication: " << multiply(3, 4);  // Output: 12
    return 0;
}
```

---

### 7.5 Default Arguments in Functions

You can assign **default values** to function parameters.

#### Example:

```cpp
#include <iostream>
using namespace std;

int add(int a, int b = 5) {  // Default value for b
    return a + b;
}

int main() {
    cout << add(10) << endl;  // Uses default value: Output: 15
    cout << add(10, 2) << endl;  // Overwrites default: Output: 12
    return 0;
}
```

---

### 7.6 Recursive Functions

A **recursive function** calls itself to solve a problem.

#### Example: Factorial Calculation

```cpp
#include <iostream>
using namespace std;

int factorial(int n) {
    if (n == 0) return 1;  // Base case
    return n * factorial(n - 1);  // Recursive call
}

int main() {
    cout << "Factorial of 5: " << factorial(5);  // Output: 120
    return 0;
}
```

---

### 7.7 Function Overloading

**Function overloading** allows functions with the same name but different parameter types or counts.

#### Example:

```cpp
#include <iostream>
using namespace std;

int add(int a, int b) {
    return a + b;
}

double add(double a, double b) {
    return a + b;
}

int main() {
    cout << "Sum of integers: " << add(2, 3) << endl;  // Output: 5
    cout << "Sum of doubles: " << add(2.5, 3.5) << endl;  // Output: 6
    return 0;
}
```

---

## 8. Problems and Practice

### Problem 1: Write a Function to Find the Maximum of Two Numbers

```cpp
#include <iostream>
using namespace std;

int maximum(int a, int b) {
    return (a > b) ? a : b;
}

int main() {
    cout << "Max: " << maximum(10, 20);  // Output: 20
    return 0;
}
```

### Problem 2: Write a Function to Check if a Number is Even

```cpp
#include <iostream>
using namespace std;

bool isEven(int n) {
    return n % 2 == 0;
}

int main() {
    cout << "Is 4 even? " << (isEven(4) ? "Yes" : "No");  // Output: Yes
    return 0;
}
```

### Problem 3: Write a Function to Calculate the Factorial of a Number

```cpp
#include <iostream>
using namespace std;

int factorial(int n) {
    int result = 1;
    for (int i = 1; i <= n; ++i) {
        result *= i;
    }
    return result;
}

int main() {
    cout << "Factorial of 5: " << factorial(5);  // Output: 120
    return 0;
}
```

---

## 9. Summary

| Function Type            | Description                                                           |
| ------------------------ | --------------------------------------------------------------------- |
| **Built-in**             | Predefined in libraries.                                              |
| **User-defined**         | Written by the programmer.                                            |
| **Void**                 | Perform tasks without returning values.                               |
| **Parameterized**        | Take inputs (parameters).                                             |
| **Default arguments**    | Simplify parameterized functions.                                     |
| **Recursive**            | Call themselves.                                                      |
| **Function overloading** | Allow multiple functions with the same name but different parameters. |

---

By mastering functions, you can write organized, modular, and reusable code. Practice these concepts to solidify your understanding! 🚀
