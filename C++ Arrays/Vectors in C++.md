# Vectors in C++

A **vector** in C++ is a dynamic array that can grow or shrink in size. Vectors are part of the **Standard Template Library (STL)** and provide useful functionalities for handling sequences of elements.

---

## Table of Contents

1. [Introduction to Vectors](#1-introduction-to-vectors)
2. [Declaring and Initializing Vectors](#2-declaring-and-initializing-vectors)
3. [Adding and Removing Elements](#3-adding-and-removing-elements)
4. [Accessing Elements](#4-accessing-elements)
5. [Vector Properties and Functions](#5-vector-properties-and-functions)
6. [Iterating Over Vectors](#6-iterating-over-vectors)
7. [Sorting and Searching in Vectors](#7-sorting-and-searching-in-vectors)
8. [Problems and Practice](#8-problems-and-practice)
9. [Summary](#9-summary)

---

## 1. Introduction to Vectors

A **vector** is a sequence container that dynamically manages an array. Unlike regular arrays, vectors can change size dynamically and handle memory allocation automatically.

### Advantages of Vectors:

- **Dynamic resizing** (grows/shrinks automatically)
- **Easy element access** with indexing
- **Rich set of functions** from STL
- **Better memory management** compared to raw arrays

---

## 2. Declaring and Initializing Vectors

### Basic Declaration:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> vec;  // Declaring an empty vector
    return 0;
}
```

### Initializing with Values:

```cpp
vector<int> vec1 = {1, 2, 3, 4, 5};
vector<int> vec2(5, 10);  // Vector of size 5, all elements initialized to 10
```

---

## 3. Adding and Removing Elements

### Adding Elements:

```cpp
vector<int> vec;
vec.push_back(10);  // Adds 10 to the end
vec.push_back(20);  // Adds 20 to the end
```

### Removing Elements:

```cpp
vec.pop_back();  // Removes the last element
vec.clear();     // Removes all elements
```

---

## 4. Accessing Elements

### Using Indexing:

```cpp
cout << vec[0];  // Accessing the first element
cout << vec.at(1);  // Safe way to access elements
```

### Using Front and Back:

```cpp
cout << vec.front();  // First element
cout << vec.back();   // Last element
```

---

## 5. Vector Properties and Functions

| Function          | Description                                |
| ----------------- | ------------------------------------------ |
| `size()`          | Returns the number of elements             |
| `capacity()`      | Returns the current allocated storage      |
| `empty()`         | Checks if the vector is empty              |
| `resize(n)`       | Resizes the vector to contain `n` elements |
| `shrink_to_fit()` | Reduces memory usage                       |

### Example:

```cpp
vector<int> vec = {1, 2, 3};
cout << "Size: " << vec.size();
cout << "Capacity: " << vec.capacity();
```

---

## 6. Iterating Over Vectors

### Using a For Loop:

```cpp
for (int i = 0; i < vec.size(); i++) {
    cout << vec[i] << " ";
}
```

---

## 7. Sorting and Searching in Vectors

### Sorting a Vector:

```cpp
sort(vec.begin(), vec.end());
```

### Binary Search:

```cpp
bool found = binary_search(vec.begin(), vec.end(), 3);
```

---

## 8. Problems and Practice

### Problem 1: Find the Maximum Element in a Vector

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    vector<int> vec = {10, 20, 5, 8};
    cout << "Max element: " << *max_element(vec.begin(), vec.end());
    return 0;
}
```

### Problem 2: Remove Even Numbers from a Vector

```cpp
#include <iostream>
#include <vector>
using namespace std;

vector<int> removeEvenNumbers(vector<int> vec)
{
    vector<int> oddnumbers;
    for (int i = 0; i < vec.size(); i++)
    {
        if (vec[i] % 2 != 0)
        {
            oddnumbers.push_back(vec[i]);
        }
    }
    return oddnumbers;
}

int main()
{
    // Example vector
    vector<int> vec = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    // Call the function to remove even numbers
    vector<int> result = removeEvenNumbers(vec);

    // Print the result
    cout << "Vector after removing even numbers: ";
    for (int i = 0; i < result.size(); i++)
    {
        cout << result[i] << " ";
    }
    cout << endl;

    return 0;
}
```

### Problem 3: Reverse a Vector

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> vec = {1, 2, 3, 4, 5};
    reverse(vec.begin(), vec.end());
    for (int i = 0; i < vec.size(); i++)
    {
        cout << vec[i] << " ";
    }
    return 0;
}
```

### Problem 4: Find the Sum of All Elements in a Vector

```cpp
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    vector<int> vec = {1, 2, 3, 4, 5};
    int sum = 0;
    for (int i = 0; i <= vec.size(); i++)
    {
        sum = vec[i] + sum;
    }
    cout << "Sum: " << sum; // Output: 15
    return 0;
}
```

---

## 9. Summary

| Feature              | Description                             |
| -------------------- | --------------------------------------- |
| **Dynamic**          | Can grow and shrink in size             |
| **STL Functions**    | Provides rich built-in functionalities  |
| **Memory Efficient** | Handles memory allocation automatically |
| **Indexing**         | Supports fast access via indices        |

---

Vectors provide a flexible way to manage dynamic arrays in C++. Practice using them to master efficient programming! 🚀
