# Operators

Operators are special symbols or keywords in C++ that perform specific operations on variables or values. C++ provides a rich set of operators that allow you to perform calculations, comparisons, logical operations, and more.

## Types of Operators in C++

C++ operators can be broadly classified into the following categories:

1. **Arithmetic Operators**
2. **Relational (Comparison) Operators**
3. **Logical Operators**
4. **Bitwise Operators**
5. **Assignment Operators**

---

### 1. Arithmetic Operators

Arithmetic operators perform mathematical operations on numeric values.

| Operator | Description          | Example         |
|----------|----------------------|-----------------|
| `+`      | Addition             | `a + b`         |
| `-`      | Subtraction          | `a - b`         |
| `*`      | Multiplication       | `a * b`         |
| `/`      | Division             | `a / b`         |
| `%`      | Modulus (remainder)  | `a % b` (only for integers) |

#### Example:
```cpp
int a = 10, b = 3;
cout << "Addition: " << (a + b) << endl; // Output: 13
cout << "Subtraction: " << (a - b) << endl; // Output: 7
cout << "Division: " << (a / b) << endl; // Output: 3
cout << "Modulus: " << (a % b) << endl; // Output: 1
cout << "Multiplication: " << (a * b) << endl; // Output: 30

```

---

### 2. Relational (Comparison) Operators

Relational operators are used to compare two values. They return `true` (1) or `false` (0).

| Operator | Description          | Example         |
|----------|----------------------|-----------------|
| `==`     | Equal to             | `a == b`        |
| `!=`     | Not equal to         | `a != b`        |
| `>`      | Greater than         | `a > b`         |
| `<`      | Less than            | `a < b`         |
| `>=`     | Greater than or equal to | `a >= b`    |
| `<=`     | Less than or equal to   | `a <= b`    |

#### Example:
```cpp
int a = 5, b = 10;
cout << (a < b) << endl;  // Outputs 1 (true)
cout << (a == b) << endl; // Outputs 0 (false)
```

---

### 3. Logical Operators

Logical operators are used to combine or negate Boolean expressions.

| Operator | Description                     | Example         |
|----------|---------------------------------|-----------------|
| `&&`     | Logical AND (true if both true) | `(a > b) && (b > c)` |
| `\|\|`   | Logical OR           | `(a > b) \|\| (b > c)` |
| `!`      | Logical NOT (negates the result)| `!(a > b)` |

#### Example:
```cpp
bool x = true, y = false;
cout << (x && y) << endl;  // Outputs 0 (false)
cout << (x || y) << endl;  // Outputs 1 (true)
cout << (!x) << endl;      // Outputs 0 (false)
```

---

### 4. Bitwise Operators

Bitwise operators work on bits and perform operations at the binary level.

| Operator | Description        | Example         |
|----------|--------------------|-----------------|
| `&`      | Bitwise AND        | `a & b`         |
| `\|`      | Bitwise OR         | `a \| b`         |
| `^`      | Bitwise XOR        | `a ^ b`         |
| `~`      | Bitwise NOT        | `~a`            |


#### Example:
```cpp
int a = 5, b = 3; // Binary: a=0101, b=0011
cout << (a & b) << endl; // Outputs 1 (0001)
cout << (a | b) << endl; // Outputs 7 (0111)
cout << (a ^ b) << endl; // Outputs 6 (0110)
cout << (~a) << endl;    // Outputs -6 (1010)
```

---

### 5. Assignment Operators

Assignment operators are used to assign values to variables.

| Operator | Description              | Example         |
|----------|--------------------------|-----------------|
| `=`      | Assign                  | `a = b`         |
| `+=`     | Add and assign          | `a += b` (same as `a = a + b`) |
| `-=`     | Subtract and assign     | `a -= b` (same as `a = a - b`) |
| `*=`     | Multiply and assign     | `a *= b`        |
| `/=`     | Divide and assign       | `a /= b`        |


#### Example:
```cpp
int a = 10;
a += 5;   // a = a + 5
cout << a << endl; // Outputs 15
```
```cpp
int a = 10;
a -= 5;   // a = a - 5
cout << a << endl; // Outputs 5
```
```cpp
int a = 10;
a *= 5;   // a = a * 5
cout << a << endl; // Outputs 50
```
```cpp
int a = 10;
a /= 5;   // a = a / 5
cout << a << endl; // Outputs 2
```

---

## Conclusion
In this article you have learned about operators in C++, which are used to perform various operations on variables and values. Understanding these concepts is essential for writing efficient and readable C++ code.