
# Input/Output

In C++, input and output operations allow programs to interact with users by taking inputs and displaying outputs. The `<iostream>` library provides the basic tools for handling input and output in C++.

## Output in C++

Output in C++ is handled using the `cout` object, which is part of the standard `std` namespace and requires the `<iostream>` library. The `cout` object stands for "character output."

### Syntax for Output
The syntax for outputting data with `cout` is as follows:

```cpp
cout << "Hello, Ali!";
```

- The `<<` operator is called the **insertion operator**, and it directs the output to the standard output (usually the console).

### Example
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, Ali!" << endl;
    cout << "The value of pi is approximately: " << 3.14159 << endl;
    return 0;
}
```

**Explanation**:
- `"Hello, Ali!"` and `"The value of pi is approximately:"` are strings displayed on the console.
- `endl` inserts a newline, moving the cursor to the next line.

### Outputting Multiple Values
You can output multiple values in a single statement by chaining the `<<` operator.

```cpp
int a = 5, b = 10;
cout << "The values are " << a << " and " << b << endl;
```

**Output**:
```
The values are 5 and 10
```

---

## Input in C++

Input in C++ is handled using the `cin` object, which stands for "character input." The `cin` object reads input from the standard input (usually the keyboard).

### Syntax for Input
The syntax for taking input with `cin` is as follows:

```cpp
cin >> variable;
```

- The `>>` operator is called the **extraction operator**, and it directs the input from the keyboard to the specified variable.

### Example
```cpp
#include <iostream>
using namespace std;

int main() {
    int age;
    cout << "Enter your age: ";
    cin >> age;  // Takes input and stores it in 'age'
    cout << "You entered: " << age << endl;
    return 0;
}
```

**Explanation**:
- `cout << "Enter your age: "` displays a prompt message.
- `cin >> age;` waits for the user to input a value and stores it in the `age` variable.

### Taking Multiple Inputs
You can take multiple inputs in a single statement by chaining the `>>` operator.

```cpp
int num1, num2;
cout << "Enter two numbers: ";
cin >> num1 >> num2;
cout << "The numbers you entered are: " << num1 << " and " << num2 << endl;
```

**Example Interaction**:
```
Enter two numbers: 5 10
The numbers you entered are: 5 and 10
```

---

## Working with Strings

The `cin` object can also handle string input, but by default, it reads only a single word. For input with spaces, use `getline()`.

### Single Word Input with `cin`
```cpp
#include <iostream>
using namespace std;

int main() {
    string name;
    cout << "Enter your name: ";
    cin >> name;
    cout << "Hello, " << name << "!" << endl;
    return 0;
}
```

**Note**: If you enter "Ali Kazempour", only "Ali" will be stored in `name`.

### Multi-Word Input with `getline()`
To capture an entire line, including spaces, use the `getline()` function.

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string fullName;
    cout << "Enter your full name: ";
    getline(cin, fullName);  // Reads an entire line of text
    cout << "Hello, " << fullName << "!" << endl;
    return 0;
}
```

**Example Interaction**:
```
Enter your full name: Ali Kazempour
Hello, Ali Kazempour!
```

---

## Input/Output with Different Data Types

C++ `cin` and `cout` support multiple data types, including integers, floating-point numbers, and characters.

### Integer and Floating-Point Input/Output
```cpp
#include <iostream>
using namespace std;

int main() {
    int age;
    double salary;
    
    cout << "Enter your age: ";
    cin >> age;
    
    cout << "Enter your monthly salary: ";
    cin >> salary;
    
    cout << "Age: " << age << ", Salary: " << salary << endl;
    return 0;
}
```

### Character Input
Characters can be read and displayed using `char` variables.

```cpp
#include <iostream>
using namespace std;

int main() {
    char initial;
    cout << "Enter your initial: ";
    cin >> initial;
    cout << "Your initial is: " << initial << endl;
    return 0;
}
```

---

## Formatting Output

The `<iomanip>` library in C++ provides additional formatting options for output, such as setting the number of decimal places.

### Example with `setprecision`
```cpp
#include <iostream>
#include <iomanip>  // Include for formatting options
using namespace std;

int main() {
    double pi = 3.141592653589793;
    cout << "Default: " << pi << endl;
    cout << "Fixed, 2 decimal places: " << fixed << setprecision(2) << pi << endl;
    return 0;
}
```

**Output**:
```
Default: 3.14159
Fixed, 2 decimal places: 3.14
```


## Summary
## Input and Output in C++ is a fundamental part of any C++ program. Understanding how to take input and display output is essential for interactive programs and user interfaces. By mastering input/output, you can create dynamic and interactive applications that respond to user input.
