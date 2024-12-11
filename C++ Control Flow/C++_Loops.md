# **Loops in C++**

Loops in C++ are used to execute a block of code repeatedly until a specified condition is met. They are fundamental to programming, allowing repetitive tasks to be automated efficiently.

---

## **1. Types of Loops in C++**

C++ provides the following types of loops:

1. **for Loop**
2. **while Loop**
3. **do-while Loop**

**Note:** **Each loop type has its own syntax and is used for different purposes.**

---

## **2. The `for` Loop**

The `for` loop is used when the number of iterations is known beforehand.

### **Syntax:**

```cpp
for (initialization; condition; update) {
    // Code to execute in each iteration
}
```

### **Example:**

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        cout << "i: " << i << endl;
    }
    return 0;
}
```

### **Key Points:**

- **Initialization:** Executed once before the loop starts.
- **Condition:** Checked before each iteration; the loop exits if false.
- **Update:** Executed at the end of each iteration.

### **Nested `for` Loop:**

```cpp
#include <iostream>
using namespace std;

int main() {
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        cout << "i: " << i << ", j: " << j << endl;
    }
}
return 0;
}
```

---

## **3. The `while` Loop**

The `while` loop is used when the number of iterations is not known beforehand, and the loop continues as long as the condition is true.

### **Syntax:**

```cpp
while (condition) {
    // Code to execute in each iteration
}
```

### **Example:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int count = 0;
    while (count < 5) {
        cout << "Count: " << count << endl;
        count++;
    }
    return 0;
}
```

---

## **4. The `do-while` Loop**

The `do-while` loop is similar to the `while` loop, but it guarantees at least one execution of the loop body because the condition is checked after the loop body.

### **Syntax:**

```cpp
do {
    // Code to execute
} while (condition);
```

### **Example:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int count = 0;
    do {
        cout << "Count: " << count << endl;
        count++;
    } while (count < 5);
    return 0;
}
```

---

## **5. Controlling Loops**

### **Break Statement**

Exits the loop immediately.

```cpp
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break;
    }
    cout << i << endl;
}
```

### **Continue Statement**

Skips the rest of the loop body for the current iteration and proceeds to the next iteration.

```cpp
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        continue;
    }
    cout << i << endl;
}
```

### **Infinite Loops**

Loops that run indefinitely unless interrupted manually.

```cpp
while (true) {
    cout << "Infinite Loop" << endl;
}
```

---

## **6. Common Mistakes**

1. **Off-by-One Errors:**
   Forgetting that arrays are zero-indexed.

   ```cpp
   for (int i = 1; i <= n; i++) { // Incorrect for array
   }
   for (int i = 0; i < n; i++) {  // Correct
   }
   ```

2. **Infinite Loops:**
   Forgetting to update the loop variable.

   ```cpp
   int i = 0;
   while (i < 5) {  // Infinite loop without i++
       cout << i << endl;
   }
   ```

3. **Overusing `break` and `continue`:**
   Excessive use can make loops harder to read and debug.

---

## **7. Common Problems Using Loops**

### **1. Calculating the Sum of Numbers from 1 to n**

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n, sum = 0;
    cout << "Enter a number: ";
    cin >> n;
    for (int i = 1; i <= n; i++)
    {
        sum += i; // Adding each number to the sum
    }
    cout << "Sum: " << sum << endl;
    return 0;
}
```

### **2. Calculating the Factorial of a Number**

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n, fact = 1;
    cout << "Enter a number: ";
    cin >> n;
    if (n < 0)
    {
        cout << "Factorial is not defined for negative numbers." << endl;
    }
    else
    {
        for (int i = 1; i <= n; i++)
        {
            fact *= i; // Multiplying each number to the fact
        }
        cout << "Factorial: " << fact << endl;
    }
    return 0;
}
```


### **3. Printing a Pattern**
```cpp
#include <iostream>
using namespace std;

int main()
{
    int n;
    cout << "Enter a number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= i; j++)
        {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

### **4. Checking for Prime Numbers**

```cpp
#include <iostream>
using namespace std;

int main()
{
    int num;
    cout << "Enter a number: ";
    cin >> num;

    bool isPrime = true;
    if (num <= 1)
    {
        isPrime = false;
    }
    else
    {
        for (int i = 2; i * i <= num; i++)
        {
            if (num % i == 0)
            {
                isPrime = false;
                break;
            }
        }
    }

    if (isPrime)
    {
        cout << num << " is a prime number." << endl;
    }
    else
    {
        cout << num << " is not a prime number." << endl;
    }
    return 0;
}
```

---

## **11. Summary**

| Loop Type         | Use Case                                         |
| ----------------- | ------------------------------------------------ |
| `for`             | Known number of iterations                       |
| `while`           | Unknown number of iterations; condition-based    |
| `do-while`        | Executes at least once before checking condition |

