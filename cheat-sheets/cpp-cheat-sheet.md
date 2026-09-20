# C++ Cheat Sheet

<div align="center">

# ⚙️ C++ Beginner-to-Advanced Cheat Sheet

### Quick syntax and concept reference following the A1Lab C++ learning sequence.

Part of **[A1Lab Learning Resources](https://a1lab.tech)**

<br>

<a href="https://a1lab.tech/cpp/introduction">
  <img
    src="https://img.shields.io/badge/Learn_C++-A1Lab-00599C?style=for-the-badge&logo=cplusplus&logoColor=white"
    alt="Learn C++ on A1Lab"
  />
</a>

<a href="../roadmaps/cpp-roadmap.md">
  <img
    src="https://img.shields.io/badge/View-C++_Roadmap-00599C?style=for-the-badge&logo=cplusplus&logoColor=white"
    alt="C++ Roadmap"
  />
</a>

</div>

---

## 📚 Quick Navigation

1. Basics
2. Input & Output
3. Variables
4. Data Types
5. Operators
6. Decision Making
7. Loops
8. Functions
9. Scope & Storage
10. Arrays
11. Pointers
12. Dynamic Memory
13. References
14. Strings
15. Object-Oriented Programming
16. Encapsulation
17. Inheritance
18. Polymorphism
19. Abstraction
20. Type Casting
21. Namespaces
22. Exception Handling
23. Templates
24. STL Basics
25. File Handling
26. Preprocessor
27. Modern C++
28. Mini Projects

---

# 1. Basics

## First C++ Program

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello, C++!" << '\n';
    return 0;
}
```

---

## Program Structure

```cpp
#include <iostream>

int main()
{
    // Program code
    return 0;
}
```

---

## Statements

```cpp
int age = 20;
std::cout << age << '\n';
```

---

## Keywords

Examples:

```text
int
double
if
else
for
while
class
public
private
return
const
```

---

## Identifiers

```cpp
int studentAge = 20;
double totalMarks = 95.5;
```

---

## Comments

Single-line:

```cpp
// This is a comment
```

Multi-line:

```cpp
/*
This is
a multi-line comment.
*/
```

---

# 2. Input & Output

## C++ Output

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello" << '\n';
    return 0;
}
```

---

## C++ Input

```cpp
#include <iostream>

int main()
{
    int age;

    std::cout << "Enter age: ";
    std::cin >> age;

    std::cout << "Age: " << age << '\n';

    return 0;
}
```

---

## Escape Sequences

```cpp
std::cout << "Hello\nWorld";
std::cout << "Name:\tAli";
std::cout << "\"C++\"";
std::cout << "C:\\Files";
```

---

## New Line

```cpp
std::cout << "Hello" << '\n';
std::cout << "World" << std::endl;
```

---

## Multiple Outputs

```cpp
std::string name = "Ali";
int age = 20;

std::cout << name << " " << age << '\n';
```

---

## Formatting Output

```cpp
#include <iomanip>
#include <iostream>

int main()
{
    double price = 12.3456;

    std::cout << std::fixed
              << std::setprecision(2)
              << price << '\n';

    return 0;
}
```

---

# 3. Variables

## Variable Declaration

```cpp
int age;
double price;
char grade;
```

---

## Variable Initialization

```cpp
int age = 20;
double price = 99.99;
```

---

## auto Type

```cpp
auto number = 10;
auto price = 10.5;
auto name = "Ali";
```

---

## Multiple Variables

```cpp
int x = 10, y = 20, z = 30;
```

---

## Constants

```cpp
const double PI = 3.14159;
```

---

## const Keyword

```cpp
const int MAX_USERS = 100;
```

---

# 4. Data Types

## Integer Types

```cpp
short a = 10;
int b = 20;
long c = 30;
long long d = 40;
```

---

## Floating Point Types

```cpp
float price = 10.5f;
double salary = 5000.75;
long double value = 100.123L;
```

---

## Character Type

```cpp
char grade = 'A';
```

---

## Boolean Type

```cpp
bool isActive = true;
```

---

## void Type

```cpp
void showMessage()
{
    std::cout << "Hello" << '\n';
}
```

---

## Type Conversion

Implicit:

```cpp
int number = 10;
double value = number;
```

Explicit:

```cpp
double value = 10.8;
int number = static_cast<int>(value);
```

---

# 5. Operators

## Arithmetic Operators

```cpp
int a = 10;
int b = 3;

std::cout << a + b << '\n';
std::cout << a - b << '\n';
std::cout << a * b << '\n';
std::cout << a / b << '\n';
std::cout << a % b << '\n';
```

---

## Assignment Operators

```cpp
int x = 10;

x += 5;
x -= 2;
x *= 3;
x /= 2;
```

---

## Comparison Operators

```cpp
a == b
a != b
a > b
a < b
a >= b
a <= b
```

---

## Logical Operators

```cpp
&&
||
!
```

Example:

```cpp
if (age >= 18 && hasId)
{
    std::cout << "Allowed" << '\n';
}
```

---

## Bitwise Operators

```cpp
&
|
^
~
<<
>>
```

---

## Increment and Decrement

```cpp
x++;
x--;
++x;
--x;
```

---

## Conditional Operator

```cpp
std::string result = age >= 18 ? "Adult" : "Minor";
```

---

## sizeof Operator

```cpp
std::cout << sizeof(int) << '\n';
```

---

# 6. Decision Making

## if Statement

```cpp
if (age >= 18)
{
    std::cout << "Adult" << '\n';
}
```

---

## if else

```cpp
if (number > 0)
{
    std::cout << "Positive" << '\n';
}
else
{
    std::cout << "Not positive" << '\n';
}
```

---

## else if

```cpp
if (marks >= 90)
{
    std::cout << "A" << '\n';
}
else if (marks >= 80)
{
    std::cout << "B" << '\n';
}
else
{
    std::cout << "C" << '\n';
}
```

---

## Nested if

```cpp
if (age >= 18)
{
    if (hasId)
    {
        std::cout << "Allowed" << '\n';
    }
}
```

---

## switch Statement

```cpp
switch (choice)
{
    case 1:
        std::cout << "Add" << '\n';
        break;

    case 2:
        std::cout << "Delete" << '\n';
        break;

    default:
        std::cout << "Invalid" << '\n';
}
```

---

# 7. Loops

## while Loop

```cpp
int i = 1;

while (i <= 5)
{
    std::cout << i << '\n';
    i++;
}
```

---

## do while Loop

```cpp
int i = 1;

do
{
    std::cout << i << '\n';
    i++;
}
while (i <= 5);
```

---

## for Loop

```cpp
for (int i = 1; i <= 5; i++)
{
    std::cout << i << '\n';
}
```

---

## Range-Based for Loop

```cpp
int numbers[] = {10, 20, 30};

for (int number : numbers)
{
    std::cout << number << '\n';
}
```

---

## Nested Loops

```cpp
for (int row = 0; row < 3; row++)
{
    for (int column = 0; column < 3; column++)
    {
        std::cout << row << " " << column << '\n';
    }
}
```

---

## break

```cpp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        break;
    }
}
```

---

## continue

```cpp
for (int i = 0; i < 5; i++)
{
    if (i == 2)
    {
        continue;
    }

    std::cout << i << '\n';
}
```

---

# 8. Functions

## Function Declaration

```cpp
int add(int a, int b);
```

---

## Function Definition

```cpp
int add(int a, int b)
{
    return a + b;
}
```

---

## Function Call

```cpp
int result = add(10, 20);
```

---

## Parameters and Arguments

```cpp
void greet(std::string name)
{
    std::cout << "Hello " << name << '\n';
}

greet("Ali");
```

---

## Default Arguments

```cpp
void greet(std::string name = "Guest")
{
    std::cout << name << '\n';
}
```

---

## Inline Function

```cpp
inline int square(int number)
{
    return number * number;
}
```

---

## Function Overloading

```cpp
int add(int a, int b)
{
    return a + b;
}

double add(double a, double b)
{
    return a + b;
}
```

---

## Recursion

```cpp
int factorial(int number)
{
    if (number <= 1)
    {
        return 1;
    }

    return number * factorial(number - 1);
}
```

---

# 9. Scope & Storage

## Local Variable

```cpp
void example()
{
    int value = 10;
}
```

---

## Global Variable

```cpp
int globalValue = 100;
```

---

## Static Variable

```cpp
void counter()
{
    static int count = 0;
    count++;

    std::cout << count << '\n';
}
```

---

## extern

```cpp
extern int globalValue;
```

---

## Scope Resolution Operator

```cpp
::globalValue
```

---

# 10. Arrays

## One-Dimensional Array

```cpp
int numbers[5] = {10, 20, 30, 40, 50};
```

---

## Access Array Item

```cpp
std::cout << numbers[0] << '\n';
```

---

## Two-Dimensional Array

```cpp
int matrix[2][2] = {
    {1, 2},
    {3, 4}
};
```

---

## Multi-Dimensional Array

```cpp
int values[2][2][2] = {};
```

---

## Pass Array to Function

```cpp
void show(const int numbers[], int size)
{
    for (int i = 0; i < size; i++)
    {
        std::cout << numbers[i] << '\n';
    }
}
```

---

# 11. Pointers

## Pointer Declaration

```cpp
int number = 10;
int* pointer = &number;
```

---

## Dereference Pointer

```cpp
std::cout << *pointer << '\n';
```

---

## Null Pointer

```cpp
int* pointer = nullptr;
```

---

## Void Pointer

```cpp
int value = 10;
void* pointer = &value;
```

---

## Pointer Arithmetic

```cpp
int numbers[] = {10, 20, 30};
int* pointer = numbers;

std::cout << *(pointer + 1) << '\n';
```

---

## Pointer to Pointer

```cpp
int value = 10;
int* pointer = &value;
int** doublePointer = &pointer;
```

---

## Function Pointer

```cpp
int add(int a, int b)
{
    return a + b;
}

int (*operation)(int, int) = add;
```

---

# 12. Dynamic Memory

## new Operator

```cpp
int* number = new int(10);
```

---

## delete Operator

```cpp
delete number;
number = nullptr;
```

---

## Dynamic Array

```cpp
int* numbers = new int[5];

delete[] numbers;
numbers = nullptr;
```

---

## Memory Leak

Bad:

```cpp
int* number = new int(10);
```

If never deleted, memory can remain allocated unnecessarily.

---

## Smart Pointer

```cpp
#include <memory>

auto number = std::make_unique<int>(10);
```

---

# 13. References

## Reference

```cpp
int value = 10;
int& reference = value;
```

---

## Pass by Reference

```cpp
void increase(int& number)
{
    number++;
}
```

---

## const Reference

```cpp
void printName(const std::string& name)
{
    std::cout << name << '\n';
}
```

---

# 14. Strings

## C-Style String

```cpp
char name[] = "Ali";
```

---

## std::string

```cpp
#include <string>

std::string name = "Ali";
```

---

## String Input

```cpp
std::string name;

std::getline(std::cin, name);
```

---

## String Length

```cpp
std::cout << name.length() << '\n';
```

---

## Concatenation

```cpp
std::string first = "Hello";
std::string second = "World";

std::string result = first + " " + second;
```

---

## Compare Strings

```cpp
if (first == second)
{
    std::cout << "Equal" << '\n';
}
```

---

## find()

```cpp
std::size_t position = text.find("C++");
```

---

## replace()

```cpp
text.replace(0, 3, "Java");
```

---

## insert()

```cpp
text.insert(0, "Learn ");
```

---

## erase()

```cpp
text.erase(0, 5);
```

---

## substring

```cpp
std::string part = text.substr(0, 3);
```

---

# 15. Object-Oriented Programming

## Class

```cpp
class Student
{
public:
    std::string name;
    int age;
};
```

---

## Object

```cpp
Student student;
student.name = "Ali";
student.age = 20;
```

---

## Member Function

```cpp
class Student
{
public:
    void greet()
    {
        std::cout << "Hello" << '\n';
    }
};
```

---

## Access Specifiers

```cpp
class Example
{
public:
    int publicValue;

private:
    int privateValue;

protected:
    int protectedValue;
};
```

---

## Constructor

```cpp
class Student
{
public:
    Student()
    {
        std::cout << "Created" << '\n';
    }
};
```

---

## Parameterized Constructor

```cpp
class Student
{
public:
    std::string name;

    Student(const std::string& studentName)
        : name(studentName)
    {
    }
};
```

---

## Copy Constructor

```cpp
class Student
{
public:
    std::string name;

    Student(const Student& other)
        : name(other.name)
    {
    }
};
```

---

## Destructor

```cpp
~Student()
{
    std::cout << "Destroyed" << '\n';
}
```

---

## this Pointer

```cpp
class Student
{
private:
    std::string name;

public:
    void setName(const std::string& name)
    {
        this->name = name;
    }
};
```

---

## Static Member

```cpp
class Student
{
public:
    static int count;
};

int Student::count = 0;
```

---

# 16. Encapsulation

```cpp
class BankAccount
{
private:
    double balance = 0.0;

public:
    void deposit(double amount)
    {
        if (amount > 0)
        {
            balance += amount;
        }
    }

    double getBalance() const
    {
        return balance;
    }
};
```

---

## Getter

```cpp
double getBalance() const
{
    return balance;
}
```

---

## Setter

```cpp
void setBalance(double value)
{
    if (value >= 0)
    {
        balance = value;
    }
}
```

---

# 17. Inheritance

## Single Inheritance

```cpp
class Animal
{
public:
    void eat()
    {
        std::cout << "Eating" << '\n';
    }
};

class Dog : public Animal
{
};
```

---

## Multiple Inheritance

```cpp
class A
{
};

class B
{
};

class C : public A, public B
{
};
```

---

## Hierarchical Inheritance

```cpp
class Animal
{
};

class Dog : public Animal
{
};

class Cat : public Animal
{
};
```

---

## Protected Members

```cpp
class Parent
{
protected:
    int value = 10;
};
```

---

# 18. Polymorphism

## Virtual Function

```cpp
class Animal
{
public:
    virtual void speak()
    {
        std::cout << "Animal sound" << '\n';
    }

    virtual ~Animal() = default;
};
```

---

## Method Override

```cpp
class Dog : public Animal
{
public:
    void speak() override
    {
        std::cout << "Bark" << '\n';
    }
};
```

---

## Pure Virtual Function

```cpp
class Shape
{
public:
    virtual double area() const = 0;
    virtual ~Shape() = default;
};
```

---

## Abstract Class

A class with at least one pure virtual function is abstract.

---

# 19. Abstraction

```cpp
class Payment
{
public:
    virtual void pay(double amount) = 0;
    virtual ~Payment() = default;
};
```

---

# 20. Type Casting

## C-Style Cast

```cpp
int number = (int)10.5;
```

---

## static_cast

```cpp
double value = 10.5;
int number = static_cast<int>(value);
```

---

## dynamic_cast

```cpp
Derived* derived = dynamic_cast<Derived*>(basePointer);
```

Used with polymorphic class hierarchies.

---

## const_cast

```cpp
const int value = 10;
const int* pointer = &value;

int* mutablePointer = const_cast<int*>(pointer);
```

Use carefully.

---

## reinterpret_cast

```cpp
std::uintptr_t address =
    reinterpret_cast<std::uintptr_t>(pointer);
```

Low-level cast; use only when appropriate.

---

# 21. Namespaces

## Namespace

```cpp
namespace Math
{
    int add(int a, int b)
    {
        return a + b;
    }
}
```

Usage:

```cpp
int result = Math::add(10, 20);
```

---

## std Namespace

```cpp
std::cout << "Hello" << '\n';
std::string name = "Ali";
```

---

## using Keyword

```cpp
using std::cout;
using std::string;
```

---

## Namespace Alias

```cpp
namespace fs = std::filesystem;
```

---

# 22. Exception Handling

## try and catch

```cpp
try
{
    throw 10;
}
catch (int error)
{
    std::cout << error << '\n';
}
```

---

## Standard Exception

```cpp
#include <stdexcept>

throw std::runtime_error("Something went wrong");
```

---

## Multiple Catch

```cpp
try
{
}
catch (const std::invalid_argument& error)
{
}
catch (const std::exception& error)
{
}
```

---

## Custom Exception

```cpp
#include <exception>

class InvalidAgeException : public std::exception
{
public:
    const char* what() const noexcept override
    {
        return "Invalid age";
    }
};
```

---

# 23. Templates

## Function Template

```cpp
template <typename T>
T add(T a, T b)
{
    return a + b;
}
```

---

## Class Template

```cpp
template <typename T>
class Box
{
private:
    T value;

public:
    Box(T value)
        : value(value)
    {
    }

    T getValue() const
    {
        return value;
    }
};
```

---

## Non-Type Template

```cpp
template <typename T, int Size>
class Array
{
private:
    T values[Size];
};
```

---

# 24. STL Basics

## pair

```cpp
#include <utility>

std::pair<std::string, int> student = {"Ali", 20};
```

---

## array

```cpp
#include <array>

std::array<int, 3> numbers = {10, 20, 30};
```

---

## vector

```cpp
#include <vector>

std::vector<int> numbers = {10, 20, 30};

numbers.push_back(40);
numbers.pop_back();
```

---

## Iterators

```cpp
for (auto iterator = numbers.begin();
     iterator != numbers.end();
     ++iterator)
{
    std::cout << *iterator << '\n';
}
```

---

## deque

```cpp
#include <deque>

std::deque<int> values;

values.push_front(10);
values.push_back(20);
```

---

## list

```cpp
#include <list>

std::list<int> values = {1, 2, 3};
```

---

## queue

```cpp
#include <queue>

std::queue<int> values;

values.push(10);
values.push(20);
values.pop();
```

---

## priority_queue

```cpp
std::priority_queue<int> values;

values.push(10);
values.push(30);
values.push(20);
```

---

## set

```cpp
#include <set>

std::set<int> values = {3, 1, 2};
```

Stores unique keys.

---

## multiset

```cpp
std::multiset<int> values = {1, 1, 2};
```

Allows duplicate keys.

---

## map

```cpp
#include <map>

std::map<std::string, int> ages;

ages["Ali"] = 20;
ages["Sara"] = 19;
```

---

## multimap

```cpp
std::multimap<std::string, int> values;
```

Allows duplicate keys.

---

## unordered_set

```cpp
#include <unordered_set>

std::unordered_set<int> values = {1, 2, 3};
```

---

## unordered_map

```cpp
#include <unordered_map>

std::unordered_map<std::string, int> ages;
```

---

# 25. File Handling

## Write File

```cpp
#include <fstream>

std::ofstream file("data.txt");

file << "Hello C++";
file.close();
```

---

## Read File

```cpp
#include <fstream>
#include <iostream>
#include <string>

std::ifstream file("data.txt");
std::string line;

while (std::getline(file, line))
{
    std::cout << line << '\n';
}
```

---

## fstream

```cpp
std::fstream file;
```

---

## Append File

```cpp
std::ofstream file(
    "data.txt",
    std::ios::app
);

file << "New line\n";
```

---

## Binary File

```cpp
std::ofstream file(
    "data.bin",
    std::ios::binary
);
```

---

# 26. Preprocessor

## #include

```cpp
#include <iostream>
#include <string>
```

---

## Header File

Example:

```cpp
#ifndef MATH_TOOLS_H
#define MATH_TOOLS_H

int add(int a, int b);

#endif
```

---

## #define

```cpp
#define PI 3.14159
```

Prefer typed constants such as `constexpr` when appropriate.

---

## Macro

```cpp
#define SQUARE(x) ((x) * (x))
```

Use carefully.

---

## Conditional Compilation

```cpp
#ifdef DEBUG
std::cout << "Debug mode" << '\n';
#endif
```

---

## #ifndef

```cpp
#ifndef MY_HEADER_H
#define MY_HEADER_H

// declarations

#endif
```

---

## #pragma once

```cpp
#pragma once
```

Common header guard alternative supported by major compilers.

---

# 27. Modern C++

## Uniform Initialization

```cpp
int age{20};
double price{99.99};
```

---

## auto Keyword

```cpp
auto number = 10;
auto name = std::string{"Ali"};
```

---

## nullptr

```cpp
int* pointer = nullptr;
```

---

## enum class

```cpp
enum class Status
{
    Active,
    Inactive
};

Status status = Status::Active;
```

---

## constexpr

```cpp
constexpr double PI = 3.14159;
```

---

## Lambda

```cpp
auto add = [](int a, int b)
{
    return a + b;
};

std::cout << add(10, 20) << '\n';
```

---

# 28. Mini Projects

## 🧮 Calculator

Practice:

```text
Variables
Input and Output
Operators
switch
Functions
```

Example structure:

```cpp
#include <iostream>

int main()
{
    double a;
    double b;
    char operation;

    std::cin >> a >> operation >> b;

    switch (operation)
    {
        case '+':
            std::cout << a + b << '\n';
            break;

        case '-':
            std::cout << a - b << '\n';
            break;

        case '*':
            std::cout << a * b << '\n';
            break;

        case '/':
            if (b != 0)
            {
                std::cout << a / b << '\n';
            }
            break;

        default:
            std::cout << "Invalid operation" << '\n';
    }

    return 0;
}
```

---

## 🎓 Student Management System

Practice:

```text
Classes
Objects
Encapsulation
STL
Functions
File Handling
```

---

## 📚 Library Management System

Practice:

```text
Classes
Objects
Inheritance
STL containers
File Handling
Searching
Updating records
```

---

# ⚡ Frequently Used C++ Headers

```cpp
#include <algorithm>
#include <array>
#include <cmath>
#include <fstream>
#include <iomanip>
#include <iostream>
#include <list>
#include <map>
#include <memory>
#include <queue>
#include <set>
#include <string>
#include <unordered_map>
#include <unordered_set>
#include <utility>
#include <vector>
```

---

# ⚡ Frequently Used STL Operations

```cpp
vector.push_back(value);
vector.pop_back();
vector.size();
vector.empty();

set.insert(value);
set.find(value);

map[key] = value;
map.find(key);
```

---

# 🧠 Common C++ Patterns

## Loop Through Vector

```cpp
for (const int value : numbers)
{
    std::cout << value << '\n';
}
```

---

## Pass Large Object Efficiently

```cpp
void printName(const std::string& name)
{
    std::cout << name << '\n';
}
```

---

## Smart Pointer

```cpp
auto object = std::make_unique<MyClass>();
```

---

## Check Pointer

```cpp
if (pointer != nullptr)
{
    std::cout << *pointer << '\n';
}
```

---

## Safer Container Access

```cpp
std::cout << numbers.at(0) << '\n';
```

`at()` performs bounds checking.

---

# 🎯 C++ Learning Flow

```text
Basics
   ↓
Input & Output
   ↓
Variables
   ↓
Data Types
   ↓
Operators
   ↓
Decision Making
   ↓
Loops
   ↓
Functions
   ↓
Arrays
   ↓
Pointers
   ↓
Dynamic Memory
   ↓
References
   ↓
Strings
   ↓
OOP
   ↓
Inheritance
   ↓
Polymorphism
   ↓
Templates
   ↓
STL
   ↓
Files
   ↓
Modern C++
   ↓
Projects
```

---

# 📘 Complete C++ Roadmap

For the complete topic-by-topic learning sequence:

## [Open the C++ Learning Roadmap →](../roadmaps/cpp-roadmap.md)

---

# 🌐 Learn C++ With A1Lab

A1Lab combines:

- 🎓 Structured C++ lessons
- 💻 Interactive coding
- 🧠 Visual explanations
- 🧪 Practical examples
- 📝 Practice activities
- ❓ MCQs and code challenges
- 💬 Developer discussions

<div align="center">

<a href="https://a1lab.tech/cpp/introduction">
  <img
    src="https://img.shields.io/badge/Start_C++_Course-A1Lab-00599C?style=for-the-badge&logo=cplusplus&logoColor=white"
    alt="Start C++ Course on A1Lab"
  />
</a>

<br><br>

## [Explore A1Lab →](https://a1lab.tech)

</div>

---

# 👨‍💻 Maintainer

**Muhammad Ahmad**

Founder & Full-Stack Developer behind
**[A1Lab](https://a1lab.tech)**

GitHub:

[mahmad786-cloud](https://github.com/mahmad786-cloud)

---

<div align="center">

# ⚙️ Learn. Code. Build.

### C++ quick reference from fundamentals to modern C++.

**A1Lab Learning Resources**

### [Start Learning C++ →](https://a1lab.tech/cpp/introduction)

</div>
