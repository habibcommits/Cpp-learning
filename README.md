Below is the **updated `README.md`** with **complete theory explanations** added to every section.  
Just **replace** your old `README.md` with this one (copy-paste).  
All theory is written in **simple English**, perfect for Pakistani students learning C++ in class.

---

## `README.md` (Full Theory + Code + Practice)

```markdown
# C++ Learning Hub 🚀  
**From Zero to Hero – Step by Step**

> A **complete beginner guide** for our class.  
> **Theory + Code + Practice** in every folder.  
> Made by **[Your Name]** for classmates.

---

## 📚 Table of Contents
| # | Topic | Folder |
|---|-------|--------|
| 1 | **Basics** (variables, data types, I/O) | `01_Basics/` |
| 2 | **Control Flow** (if-else, switch) | `02_ControlFlow/` |
| 3 | **Loops** (for, while, do-while) | `03_Loops/` |
| 4 | **Functions** (declaration, definition, parameters) | `04_Functions/` |
| 5 | **Arrays** (1D, 2D, passing to functions) | `05_Arrays/` |
| 6 | **Pointers** (address, dereference, dynamic memory) | `06_Pointers/` |
| 7 | **Structures** (struct, typedef, nested) | `07_Structures/` |
| 8 | **Extra** (strings, file I/O, OOP intro) | `08_Extra/` |

---

## 1. Basics (`01_Basics/`)

### Theory: What is C++?
- **C++** is a **general-purpose**, **compiled**, **high-level** programming language.
- Created by **Bjarne Stroustrup** in 1985 as "C with Classes".
- Used for **system software**, **games**, **apps**, **embedded systems**.

### Structure of a C++ Program
```cpp
#include <iostream>    // Preprocessor directive
using namespace std;   // Optional (we'll avoid it in class)

int main() {           // Entry point
    cout << "Hello";   // Statement
    return 0;          // End of program
}
```

### Key Concepts

| Concept | Explanation |
|--------|-------------|
| `#include` | Brings in **header files** (like `iostream` for input/output) |
| `int main()` | **Starting point** of every C++ program |
| `cout` | **Console Output** → prints to screen |
| `cin` | **Console Input** → reads from keyboard |
| `;` | Every statement ends with semicolon |
| `{}` | Define **blocks** of code |

### Data Types
| Type | Size | Example |
|------|------|--------|
| `int` | 4 bytes | `int age = 18;` |
| `float` | 4 bytes | `float pi = 3.14;` |
| `double` | 8 bytes | `double salary = 50000.50;` |
| `char` | 1 byte | `char grade = 'A';` |
| `bool` | 1 byte | `bool isStudent = true;` |

### Example Code: `hello.cpp`
```cpp
#include <iostream>
int main() {
    int roll = 101;
    float cgpa = 3.75;
    char grade = 'A';
    std::cout << "Roll: " << roll << "\nCGPA: " << cgpa << "\nGrade: " << grade << '\n';
    return 0;
}
```

### Practice
1. Take name (as string), age, and print: `"Hi [name], you are [age] years old."`
2. Take two numbers and print sum, difference, product.

---

## 2. Control Flow (`02_ControlFlow/`)

### Theory: Decision Making
Sometimes we want to **run code only if a condition is true**.

### `if`, `else if`, `else`
```cpp
if (condition) {
    // run if true
} else if (another_condition) {
    // run if first false, this true
} else {
    // run if all false
}
```

### Relational Operators
| Operator | Meaning |
|--------|--------|
| `==` | Equal to |
| `!=` | Not equal |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater or equal |
| `<=` | Less or equal |

### Logical Operators
| Operator | Meaning |
|--------|--------|
| `&&` | AND (both true) |
| `\|\|` | OR (any one true) |
| `!` | NOT (reverse) |

### `switch` Statement
- Used when comparing **one variable** with **many constant values**.
```cpp
switch (grade) {
    case 'A': cout << "Excellent"; break;
    case 'B': cout << "Good"; break;
    default: cout << "Try again";
}
```

### Example: `grade.cpp`
```cpp
#include <iostream>
int main() {
    char grade;
    std::cout << "Enter grade (A/B/C/F): ";
    std::cin >> grade;

    switch (grade) {
        case 'A': std::cout << "90-100\n"; break;
        case 'B': std::cout << "80-89\n"; break;
        case 'C': std::cout << "70-79\n"; break;
        default: std::cout << "Below 70\n";
    }
    return 0;
}
```

### Practice
- Build a **menu**: 1=Add, 2=Subtract, 3=Exit → use `switch`.

---

## 3. Loops (`03_Loops/`)

### Theory: Repetition
Run same code **multiple times**.

### Types of Loops

| Loop | Syntax | When to Use |
|------|--------|-------------|
| `for` | `for(init; condition; update)` | Known number of times |
| `while` | `while(condition)` | Check **before** running |
| `do-while` | `do { } while(condition);` | Run **at least once** |

### `break` and `continue`
- `break` → exit loop immediately
- `continue` → skip rest of current iteration

### Example: `table.cpp`
```cpp
#include <iostream>
int main() {
    int n;
    std::cout << "Enter number: ";
    std::cin >> n;

    for (int i = 1; i <= 10; ++i) {
        std::cout << n << " x " << i << " = " << n*i << '\n';
    }
    return 0;
}
```

### Practice
1. Print **Fibonacci** up to *n* terms using `while`.
2. Print **reverse** of a number using `do-while`.

---

## 4. Functions (`04_Functions/`)

### Theory: Reusable Code
A **function** is a block of code that does one job.

### Syntax
```cpp
return_type function_name(parameters) {
    // code
    return value;
}
```

### Types of Functions
| Type | Example |
|------|--------|
| No param, no return | `void greet()` |
| With param, no return | `void printSum(int a, int b)` |
| No param, with return | `int getRoll()` |
| With param & return | `int add(int x, int y)` |

### Pass by Value vs Reference
```cpp
void increment(int x) { x++; }        // copy → original unchanged
void increment(int &x) { x++; }       // reference → original changed
```

### Example: `factorial.cpp`
```cpp
#include <iostream>
long long factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n-1);  // recursion
}
int main() {
    int x; std::cin >> x;
    std::cout << factorial(x) << '\n';
    return 0;
}
```

### Practice
- Write `void swap(int &a, int &b)`
- Write `bool isPrime(int n)`

---

## 5. Arrays (`05_Arrays/`)

### Theory: Storing Multiple Values
An **array** is a collection of same-type items stored in **contiguous memory**.

### Declaration
```cpp
int arr[5];           // size 5
int marks[] = {90, 85, 88, 92, 87};
```

### Accessing Elements
- Index starts from **0**
- `arr[0]`, `arr[1]`, ..., `arr[4]`

### 2D Array (Matrix)
```cpp
int matrix[2][3] = {
    {1, 2, 3},
    {4, 5, 6}
};
```

### Passing Array to Function
```cpp
void printArray(int arr[], int size) {
    for(int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
}
```

### Example: `reverse.cpp`
```cpp
#include <iostream>
const int SZ = 5;
int main() {
    int arr[SZ];
    for (int i = 0; i < SZ; ++i) std::cin >> arr[i];

    // Reverse
    for (int i = 0; i < SZ/2; ++i) {
        int temp = arr[i];
        arr[i] = arr[SZ-1-i];
        arr[SZ-1-i] = temp;
    }
    for (int x : arr) std::cout << x << ' ';
    return 0;
}
```

### Practice
- Add two 2x2 matrices.
- Find **largest** element in array.

---

## 6. Pointers (`06_Pointers/`)

### Theory: Memory Address
A **pointer** is a variable that stores **memory address** of another variable.

### Syntax
```cpp
int x = 10;
int *p = &x;    // p holds address of x
*p = 20;        // change value at that address
```

### Key Symbols
| Symbol | Meaning |
|-------|--------|
| `&` | Address-of operator |
| `*` | Dereference (get value at address) |

### Pointer Arithmetic
```cpp
int arr[3] = {10, 20, 30};
int *p = arr;    // p points to arr[0]
cout << *(p+1);  // 20
```

### Dynamic Memory
```cpp
int *p = new int;      // allocate on heap
*p = 50;
delete p;              // free memory

int *arr = new int[10];
delete[] arr;
```

### Example: `pointer_basics.cpp`
```cpp
#include <iostream>
int main() {
    int x = 42;
    int *p = &x;
    std::cout << "Value: " << *p << "\nAddress: " << p << '\n';
    *p = 100;
    std::cout << "New x: " << x << '\n';
    return 0;
}
```

### Practice
- Write a function to **swap two numbers using pointers**.
- Create dynamic array, take input, print reverse.

---

## 7. Structures (`07_Structures/`)

### Theory: User-Defined Data Type
A **structure** groups **different data types** under one name.

### Syntax
```cpp
struct Student {
    std::string name;
    int roll;
    float cgpa;
};
```

### Creating Object
```cpp
Student s1;
s1.name = "Ali";
s1.roll = 101;
```

### `typedef` (optional shortcut)
```cpp
typedef struct {
    // fields
} Student;
```

### Array of Structures
```cpp
Student class[30];
```

### Example: `student.cpp`
```cpp
#include <iostream>
#include <string>
struct Student {
    std::string name;
    int roll;
    float cgpa;
};
int main() {
    Student s = {"Ali", 101, 3.8};
    std::cout << s.name << " – CGPA: " << s.cgpa << '\n';
    return 0;
}
```

### Practice
- Create array of 3 students → input → print in **sorted order by CGPA**.

---

## 8. Extra (`08_Extra/`)

| Topic | What You'll Learn |
|------|-------------------|
| `std::string` | Text handling, `+`, `length()`, `substr()` |
| File I/O | Read/write text files using `fstream` |
| Classes (OOP Intro) | `class`, `public`, `private`, `constructor` |

---

## 🛠 Compile & Run

```bash
g++ -std=c++17 filename.cpp -o output
./output
```

> Use **Dev-C++**, **Code::Blocks**, or **OnlineGDB.com**

---

## 📝 How to Contribute
1. **Fork** this repo
2. Create branch: `git checkout -b feature/your-name`
3. Add your **code + theory + exercise**
4. **Pull Request**

---

**Let’s make C++ easy for everyone!**  
*Tag your friends. Share the repo.* 🇵🇰✨
```

---

## Next Steps (Quick Actions)

1. **Replace** your current `README.md` with the above.
2. Create **one `.cpp` file per folder** using the example codes.
3. Add **comments** in code (already included).
4. Push to GitHub.

---

**Want me to generate all `.cpp` files automatically?**  
Just say:  
> “Generate all example .cpp files for the repo”

I’ll give you **8 ready-to-copy files** in one message. 🚀
```
