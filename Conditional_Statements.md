# **Conditional Statements in C++**

Conditional statements in C++ are used to execute specific blocks of code based on whether a condition is true or false. They allow decision-making in programs.

---

## **1. Basic Syntax**

### **if Statement**
Executes a block of code if the condition evaluates to true.
```cpp
if (condition) {
    // Code to execute if condition is true
}
```
Example:
```cpp
int age = 18;
if (age >= 18) {
    cout << "You are an adult." << endl;
}
```

### **if-else Statement**
Adds an alternative block of code to execute if the condition is false.
```cpp
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

Example:
```cpp
int age = 15;
if (age >= 18) {
    cout << "You are an adult." << endl;
} else {
    cout << "You are a minor." << endl;
}
```

### **if-else-if Ladder**
Checks multiple conditions sequentially.
```cpp
if (condition1) {
    // Code for condition1
} else if (condition2) {
    // Code for condition2
} else {
    // Default code
}
```

Example:
```cpp
int score = 85;
if (score >= 90) {
    cout << "Excellent!" << endl;
} else if (score >= 80) {
    cout << "Good!" << endl;
} else {
    cout << "Average." << endl;
}
```

---

## **2. Nested if Statements**
You can nest `if` statements for more complex decision-making.
```cpp
if (condition1) {
    if (condition2) {
        // Code to execute if both condition1 and condition2 are true
    }
}
```

### Example:
```cpp
int age = 25;
if (age >= 18) {
    cout << "You are an adult." << endl;
    if (age >= 65) {
        cout << "You are a senior citizen." <<endl;
    }
}

---

## **3. The switch Statement**
The `switch` statement tests a variable against a list of values and executes the matching block.
```cpp
switch (variable) {
    case value1:
        // Code for value1
        break;
    case value2:
        // Code for value2
        break;
    default:
        // Default code
}
```

### Notes:
- The `break` statement prevents fall-through.
- `default` is optional and executes if no case matches.

### Example:
```cpp
int day = 3;
switch (day) {
    case 1:
        cout << "Monday" << endl;
        break;
    case 2:
        cout << "Tuesday" << endl;
        break;
    case 3:
        cout << "Wednesday" << endl;
        break;
    default:
        cout << "Invalid day." << endl;
}
```
---

## **4. Logical Operators**
Logical operators are often used in conditional statements to combine multiple conditions:
- `&&` (AND): True if both conditions are true.
- `||` (OR): True if at least one condition is true.
- `!` (NOT): Reverses the truth value.

### Example:
```cpp
int age = 20, hasLicense = true;
if (age > 18 && hasLicense) {
    cout << "You can drive.";
}
```

---

## **5. Relational Operators**
Relational operators compare two values:
- `==` (Equal)
- `!=` (Not equal)
- `<` (Less than)
- `>` (Greater than)
- `<=` (Less than or equal to)
- `>=` (Greater than or equal to)

### Example:
```cpp
if (x >= y) {
    cout << "x is greater than or equal to y.";
}
```

---

## **6. Advanced Concepts**

### **a. Combining Conditions**
Conditions can be complex by combining multiple logical and relational operators.
```cpp
if ((x > 10 && y < 5) || z == 0) {
    // Execute this block if the combined condition is true
}
```

### **b. Switch with Multiple Cases**
Multiple cases can execute the same block of code.
```cpp
switch (grade) {
    case 'A':
    case 'B':
        cout << "Good Job!";
        break;
    case 'C':
        cout << "You can do better.";
        break;
    default:
        cout << "Invalid grade.";
}
```

### **c. Conditional Statements with Loops**
Conditions are often used inside loops to control the flow dynamically.
```cpp
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        cout << i << " is even\n";
    }
}
```

---

## **7. Common Mistakes**
1. **Missing `break` in `switch`:**
   Causes fall-through to the next case unintentionally.
   ```cpp
   switch (x) {
       case 1:
           cout << "One";
           // Fall-through happens here
       case 2:
           cout << "Two";
   }
   ```
2. **Improper Parentheses:**
   Ambiguity in conditions due to missing parentheses.
   ```cpp
   if (x > 10 && y < 5 || z == 0)  // May not behave as expected
   if ((x > 10 && y < 5) || z == 0)  // Clearer and correct
   ```
3. **Floating-Point Comparisons:**
   Avoid direct equality checks with floating-point numbers.
   ```cpp
   if (a == b)  // May not work as expected due to precision issues
   if (fabs(a - b) < 1e-9)  // Better way to compare
   ```

---

## **8. Examples**

### **Example 1: Simple if-else**
```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    cout << "Enter a number: ";
    cin >> number;

    if (number % 2 == 0) {
        cout << "Even number";
    } else {
        cout << "Odd number";
    }
    return 0;
}
```

### **Example 2: Grade Evaluation with switch**
```cpp
#include <iostream>
using namespace std;

int main() {
    char grade;
    cout << "Enter your grade (A, B, C, D, F): ";
    cin >> grade;

    switch (grade) {
        case 'A':
            cout << "Excellent!";
            break;
        case 'B':
        case 'C':
            cout << "Good work!";
            break;
        case 'D':
            cout << "You passed.";
            break;
        case 'F':
            cout << "Better luck next time.";
            break;
        default:
            cout << "Invalid grade.";
    }
    return 0;
}

```

---

## **10. Practical Use Cases**
1. **User Authentication System**
   ```cpp
   if (username == "admin" && password == "12345") {
       cout << "Access Granted";
   } else {
       cout << "Access Denied";
   }
   ```
2. **Game Mechanics**
   ```cpp
   if (playerHealth <= 0) {
       cout << "Game Over!";
   }
   ```

---

## **Summary**
Conditional statements in C++ form the backbone of decision-making in programming. By mastering these structures, you can create efficient and complex programs.

