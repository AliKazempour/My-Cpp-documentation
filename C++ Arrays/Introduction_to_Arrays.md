# Arrays in C++

This guide covers essential concepts of **arrays** in C++, including their declaration, initialization, and manipulation. It also includes straightforward examples and problems that demonstrate how to use arrays effectively in various scenarios.

---

## Table of Contents

1. [Introduction to Arrays](#introduction-to-arrays)
2. [Declaring and Initializing Arrays](#declaring-and-initializing-arrays)
3. [Common Array Operations](#common-array-operations)
4. [Multidimensional Arrays](#multidimensional-arrays)
5. [Problems and Practice](#problems-and-practice)
6. [Matrix Multiplication](#matrix-multiplication)
7. [Summary](#summary)

---

## 1. Introduction to Arrays

An **array** is a collection of variables of the same type, stored in contiguous memory locations. Arrays allow you to store multiple values in a single variable. Each element in the array is accessed using its **index**, which starts at 0.

### Array Syntax

```cpp
type arrayName[arraySize];
```

### Example

```cpp
int arr[5];  // An array of 5 integers
```

---

## 2. Declaring and Initializing Arrays

Arrays can be declared and initialized in several ways in C++. You can either explicitly initialize the array with values or let C++ initialize it automatically.

### Declaration and Initialization

```cpp
int arr[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
```

If you do not specify the size, C++ will automatically determine the size based on the number of elements:

```cpp
int arr[] = {10, 20, 30, 40};  // Size is inferred as 4
```

### Default Initialization

If the array is not explicitly initialized, the elements will contain garbage values. To initialize an array with zeros, use `{}`:

```cpp
int arr[5] = {};  // All elements will be initialized to 0
```

---

## 3. Common Array Operations

### 3.1 Finding the Length of an Array

To determine the length of a statically allocated array, use the `sizeof` operator:

**Note:** The `sizeof` operator returns the size of a type in bytes.

```cpp
int arr[5] = {1, 2, 3, 4, 5};
int length = sizeof(arr) / sizeof(arr[0]);  // Output: 5
```

### 3.2 Copying Arrays

Arrays cannot be copied directly using the `=` operator. To copy an array, you need to use a loop:

```cpp
int arr1[5] = {1, 2, 3, 4, 5};
int arr2[5];

for (int i = 0; i < 5; i++) {
    arr2[i] = arr1[i];  // Copy elements from arr1 to arr2
}
```

### 3.3 Finding the Maximum and Minimum Values in an Array

```cpp
int arr[5] = {10, 20, 30, 40, 50};
int max = arr[0];
int min = arr[0];

for (int i = 1; i < 5; i++) {
    if (arr[i] > max) max = arr[i];
    if (arr[i] < min) min = arr[i];
}

cout << "Max: " << max << ", Min: " << min;
```

### 3.4 Reversing an Array

To reverse an array, you can use a loop to swap elements from both ends:

```cpp
int arr[5] = {1, 2, 3, 4, 5};

for (int i = 0; i < 5 / 2; i++) {
    swap(arr[i], arr[5 - i - 1]);
}

for (int i = 0; i < 5; i++) {
    cout << arr[i] << " ";  // Output: 5 4 3 2 1
}
```

---

## 4. Multidimensional Arrays

### 4.1 Two-Dimensional Arrays

A **two-dimensional array** is essentially an array of arrays. It is used to represent a table or matrix structure.

```cpp
int arr[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

### Accessing Two-Dimensional Array Elements

```cpp
cout << arr[1][2];  // Output: 6
```

### 4.2 Iterating Over a Two-Dimensional Array

To iterate over a 2D array, use nested loops:

```cpp
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        cout << arr[i][j] << " ";
    }
    cout << endl;
}
```

### 4.3 Three-Dimensional Arrays

You can create multi-dimensional arrays with more than two dimensions. For example, a 3D array:

```cpp
int arr[2][3][4];  // A 2x3x4 3D array
```

---

## 5. Problems and Practice

Here are some simple array-related problems for practice.

### Problem 1: Find the Sum of Elements in an Array

Write a program to calculate the sum of all elements in an array.

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {1, 2, 3, 4, 5};
    int sum = 0;

    for (int i = 0; i < 5; i++) {
        sum += arr[i];  // Add each element to sum
    }

    cout << "Sum of elements: " << sum;  // Output: 15
}
```

### Problem 2: Find the Largest Element in an Array

Write a program to find the largest element in an array.

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {3, 1, 4, 1, 5};
    int largest = arr[0];

    for (int i = 1; i < 5; i++) {
        if (arr[i] > largest) {
            largest = arr[i];  // Update largest if current element is bigger
        }
    }

    cout << "Largest element: " << largest;  // Output: 5
}
```

### Problem 3: Count Occurrences of an Element

Write a program to count how many times a specific element occurs in an array.

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[6] = {1, 2, 3, 4, 3, 5};
    int target = 3;
    int count = 0;

    for (int i = 0; i < 6; i++) {
        if (arr[i] == target) {
            count++;  // Increment count if the target is found
        }
    }

    cout << "Occurrences of " << target << ": " << count;  // Output: 2
}
```

---

## 6. Matrix Multiplication

Matrix multiplication is one of the most common operations involving arrays. If you want to multiply two matrices, the number of columns in the first matrix must equal the number of rows in the second matrix.

Given two matrices **A** and **B**:

```
A = { {1, 2},
      {3, 4} }

B = { {5, 6},
      {7, 8} }
```

The resulting matrix **C** will be:

```
C = { { (1*5 + 2*7), (1*6 + 2*8) },
      { (3*5 + 4*7), (3*6 + 4*8) } }
```

### Matrix Multiplication Code

```cpp
#include <iostream>
using namespace std;

int main() {
    int A[2][2] = {{1, 2}, {3, 4}};
    int B[2][2] = {{5, 6}, {7, 8}};

    int C[2][2];  // Resultant matrix

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            C[i][j] = 0;
            for (int k = 0; k < 2; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }

    // Display the result
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            cout << C[i][j] << " ";  // Output: 19 22 43 50
        }
        cout << endl;
    }
}
```

---

## 7. Summary

In conclusion, arrays are an essential data structure in C++ for storing and manipulating collections of data. By mastering the concepts of declaring, initializing, and manipulating arrays, you can tackle a wide range of programming tasks efficiently and effectively.
