# C Cheat Sheet

<div align="center">

# 🔵 C Beginner-to-Advanced Cheat Sheet

### Quick syntax and concept reference following the A1Lab C learning sequence.

Part of **[A1Lab Learning Resources](https://a1lab.tech)**

<br>

<a href="https://a1lab.tech/c/introduction">
  <img
    src="https://img.shields.io/badge/Learn_C-A1Lab-A8B9CC?style=for-the-badge&logo=c&logoColor=black"
    alt="Learn C on A1Lab"
  />
</a>

<a href="../roadmaps/c-roadmap.md">
  <img
    src="https://img.shields.io/badge/View-C_Roadmap-283593?style=for-the-badge&logo=c&logoColor=white"
    alt="C Roadmap"
  />
</a>

</div>

---

## ⚠️ C Version Note

C has multiple language standards such as C90, C99, C11, C17, and C23.

Some features and compiler behavior can depend on the selected C standard.

This cheat sheet focuses on common modern C syntax.

---

## 📚 Quick Navigation

1. C Basics
2. C Output
3. C Input
4. C Variables
5. C Data Types
6. C Operators
7. C Decision Making
8. C Loops
9. C Functions
10. C Scope & Storage
11. C Arrays
12. C Strings
13. C Pointers
14. C Dynamic Memory
15. C Structures
16. C Unions
17. C Enumerations
18. C typedef
19. C Files
20. C Preprocessor
21. C Error Handling
22. C Bit Manipulation
23. C Memory Concepts
24. C Command Line
25. C Multi File Programs
26. C Standard Library
27. Intermediate C Concepts
28. C Projects

---

# 1. C Basics

## First C Program

```c
#include <stdio.h>

int main(void)
{
    printf("Hello, C!\n");

    return 0;
}
```

---

## Program Structure

```c
#include <stdio.h>

int main(void)
{
    /* Program statements */

    return 0;
}
```

---

## Statements

```c
int age = 20;

printf("%d\n", age);
```

---

## Keywords

Common examples:

```text
int
char
float
double
if
else
for
while
return
struct
typedef
const
static
```

---

## Identifiers

```c
int student_age = 20;
float total_marks = 95.5f;
```

---

## Tokens

Examples of C tokens:

```text
Keywords
Identifiers
Constants
String literals
Operators
Punctuators
```

---

## Character Set

C programs commonly use:

```text
Letters
Digits
Whitespace
Special symbols
Escape sequences
```

---

## Comments

Single-line:

```c
// Single-line comment
```

Multi-line:

```c
/*
    Multi-line comment
*/
```

---

# 2. C Output

## printf()

```c
printf("Hello, C!\n");
```

---

## Escape Sequences

```c
printf("Hello\nWorld\n");
printf("Name:\tAli\n");
printf("\"C Programming\"\n");
printf("C:\\Files\\data.txt\n");
```

---

## New Line

```c
printf("First line\n");
printf("Second line\n");
```

---

## Format Specifiers

Common examples:

```text
%d   int
%u   unsigned int
%f   floating-point output
%c   character
%s   string
%ld  long
%lld long long
%p   pointer
```

Example:

```c
int age = 20;
double price = 99.95;

printf("Age: %d\n", age);
printf("Price: %.2f\n", price);
```

---

## Print Variables

```c
int age = 20;
char grade = 'A';

printf("Age: %d\n", age);
printf("Grade: %c\n", grade);
```

---

## Multiple Output

```c
char name[] = "Ali";
int age = 20;

printf("Name: %s, Age: %d\n", name, age);
```

---

# 3. C Input

## scanf()

```c
#include <stdio.h>

int main(void)
{
    int age;

    printf("Enter age: ");
    scanf("%d", &age);

    printf("Age: %d\n", age);

    return 0;
}
```

---

## Multiple Inputs

```c
int x;
int y;

scanf("%d %d", &x, &y);
```

---

## Read Character

```c
char grade;

scanf(" %c", &grade);
```

The leading space helps skip pending whitespace.

---

## Read String

For a single word:

```c
char name[50];

scanf("%49s", name);
```

For a full line:

```c
char name[100];

fgets(name, sizeof(name), stdin);
```

---

## Input Validation

```c
int number;

if (scanf("%d", &number) == 1)
{
    printf("Valid number\n");
}
else
{
    printf("Invalid input\n");
}
```

---

# 4. C Variables

## Variable Declaration

```c
int age;
float price;
char grade;
```

---

## Variable Initialization

```c
int age = 20;
float price = 10.5f;
```

---

## Multiple Variables

```c
int x = 10;
int y = 20;
int z = 30;
```

---

## Constants

```c
const double PI = 3.14159;
```

---

## Variable Scope

```c
int global_value = 100;

void example(void)
{
    int local_value = 10;
}
```

---

## Static Variable

```c
void counter(void)
{
    static int count = 0;

    count++;

    printf("%d\n", count);
}
```

---

## extern

```c
extern int global_value;
```

---

# 5. C Data Types

## int

```c
int age = 20;
```

---

## float

```c
float price = 10.5f;
```

---

## double

```c
double salary = 5000.75;
```

---

## char

```c
char grade = 'A';
```

---

## void

```c
void greet(void)
{
    printf("Hello\n");
}
```

---

## bool

With `<stdbool.h>` in C99 through C17:

```c
#include <stdbool.h>

bool is_active = true;
```

---

## short

```c
short value = 100;
```

---

## long

```c
long value = 100000L;
```

---

## long long

```c
long long value = 9000000000LL;
```

---

## signed and unsigned

```c
signed int a = -10;
unsigned int b = 10U;
```

---

## Type Casting

```c
double value = 10.8;

int number = (int)value;
```

---

## Type Conversion

```c
int number = 10;

double value = number;
```

---

# 6. C Operators

## Arithmetic Operators

```c
+
-
*
/
%
```

Example:

```c
int a = 10;
int b = 3;

printf("%d\n", a + b);
printf("%d\n", a - b);
printf("%d\n", a * b);
printf("%d\n", a / b);
printf("%d\n", a % b);
```

---

## Assignment Operators

```c
=
+=
-=
*=
/=
%=
```

---

## Comparison Operators

```c
==
!=
>
<
>=
<=
```

---

## Logical Operators

```c
&&
||
!
```

---

## Bitwise Operators

```c
&
|
^
~
<<
>>
```

---

## Increment and Decrement

```c
x++;
x--;
++x;
--x;
```

---

## Conditional Operator

```c
const char *status = age >= 18 ? "Adult" : "Minor";
```

---

## Comma Operator

```c
int x;

x = (printf("Hello\n"), 10);
```

Use carefully because it can reduce readability.

---

## sizeof

```c
printf("%zu\n", sizeof(int));
```

---

# 7. C Decision Making

## if

```c
if (age >= 18)
{
    printf("Adult\n");
}
```

---

## if else

```c
if (number > 0)
{
    printf("Positive\n");
}
else
{
    printf("Not positive\n");
}
```

---

## else if

```c
if (marks >= 90)
{
    printf("A\n");
}
else if (marks >= 80)
{
    printf("B\n");
}
else
{
    printf("C\n");
}
```

---

## Nested if

```c
if (age >= 18)
{
    if (has_id)
    {
        printf("Allowed\n");
    }
}
```

---

## switch

```c
switch (choice)
{
    case 1:
        printf("Add\n");
        break;

    case 2:
        printf("Delete\n");
        break;

    default:
        printf("Invalid choice\n");
}
```

---

# 8. C Loops

## while

```c
int i = 1;

while (i <= 5)
{
    printf("%d\n", i);
    i++;
}
```

---

## do while

```c
int i = 1;

do
{
    printf("%d\n", i);
    i++;
}
while (i <= 5);
```

---

## for

```c
for (int i = 1; i <= 5; i++)
{
    printf("%d\n", i);
}
```

---

## Nested Loop

```c
for (int row = 0; row < 3; row++)
{
    for (int column = 0; column < 3; column++)
    {
        printf("%d %d\n", row, column);
    }
}
```

---

## break

```c
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

```c
for (int i = 0; i < 5; i++)
{
    if (i == 2)
    {
        continue;
    }

    printf("%d\n", i);
}
```

---

## goto

```c
goto end;

printf("Skipped\n");

end:
printf("Done\n");
```

Generally prefer structured control flow where possible.

---

# 9. C Functions

## Function Declaration

```c
int add(int a, int b);
```

---

## Function Definition

```c
int add(int a, int b)
{
    return a + b;
}
```

---

## Function Call

```c
int result = add(10, 20);
```

---

## Parameters and Arguments

```c
void greet(const char name[])
{
    printf("Hello %s\n", name);
}

greet("Ali");
```

---

## Return Statement

```c
int square(int number)
{
    return number * number;
}
```

---

## Call by Value

```c
void change(int value)
{
    value = 100;
}
```

The function receives a copy of the argument value.

---

## Recursion

```c
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

## Function Prototype

```c
double calculate(double x, double y);
```

---

# 10. C Scope & Storage

## Local Variable

```c
void example(void)
{
    int local_value = 10;
}
```

---

## Global Variable

```c
int global_value = 100;
```

---

## Static Variable

```c
static int count = 0;
```

---

## Extern Variable

```c
extern int global_value;
```

---

## Variable Lifetime

Automatic local variables normally exist while their block is active.

Static-storage objects exist for the duration of the program.

---

# 11. C Arrays

## Array

```c
int numbers[5] = {10, 20, 30, 40, 50};
```

---

## Access Element

```c
printf("%d\n", numbers[0]);
```

---

## One-Dimensional Array

```c
int values[] = {1, 2, 3};
```

---

## Two-Dimensional Array

```c
int matrix[2][2] = {
    {1, 2},
    {3, 4}
};
```

---

## Multi-Dimensional Array

```c
int values[2][2][2] = {0};
```

---

## Pass Array to Function

```c
void print_array(const int values[], size_t size)
{
    for (size_t i = 0; i < size; i++)
    {
        printf("%d\n", values[i]);
    }
}
```

---

## Array of Strings

```c
char names[3][20] = {
    "Ali",
    "Sara",
    "Ahmed"
};
```

---

# 12. C Strings

## String

```c
char name[] = "Ali";
```

C strings end with the null character `'\0'`.

---

## Character Array

```c
char text[6] = {
    'H',
    'e',
    'l',
    'l',
    'o',
    '\0'
};
```

---

## strlen()

```c
#include <string.h>

size_t length = strlen("Hello");
```

---

## strcpy()

```c
char destination[20];

strcpy(destination, "Hello");
```

Destination must have enough space.

---

## strncpy()

```c
char destination[20];

strncpy(
    destination,
    "Hello",
    sizeof(destination) - 1
);

destination[sizeof(destination) - 1] = '\0';
```

---

## strcat()

```c
char text[50] = "Hello ";

strcat(text, "World");
```

---

## strncat()

```c
strncat(text, "World", 5);
```

Ensure the destination has enough capacity.

---

## strcmp()

```c
if (strcmp("Ali", "Ali") == 0)
{
    printf("Equal\n");
}
```

---

## strchr()

```c
char *position = strchr("Hello", 'e');
```

---

## strstr()

```c
char *position = strstr(
    "Learn C Programming",
    "C Programming"
);
```

---

## strtok()

```c
char text[] = "C,Python,Java";

char *token = strtok(text, ",");

while (token != NULL)
{
    printf("%s\n", token);

    token = strtok(NULL, ",");
}
```

---

# 13. C Pointers

## Pointer Declaration

```c
int number = 10;

int *pointer = &number;
```

---

## Dereference Pointer

```c
printf("%d\n", *pointer);
```

---

## NULL Pointer

```c
int *pointer = NULL;
```

---

## Void Pointer

```c
int value = 10;

void *pointer = &value;
```

A `void *` must be converted to an appropriate object pointer type before dereferencing.

---

## Dangling Pointer

Bad pattern:

```c
int *pointer = malloc(sizeof(int));

free(pointer);

/* pointer still contains the old address */
```

Better:

```c
free(pointer);
pointer = NULL;
```

---

## Pointer Arithmetic

```c
int numbers[] = {10, 20, 30};

int *pointer = numbers;

printf("%d\n", *(pointer + 1));
```

---

## Pointer to Pointer

```c
int value = 10;
int *pointer = &value;
int **double_pointer = &pointer;
```

---

## Pointer and Arrays

```c
int numbers[] = {10, 20, 30};

int *pointer = numbers;
```

---

## Pointer and Strings

```c
const char *message = "Hello";
```

---

## Function Pointer

```c
int add(int a, int b)
{
    return a + b;
}

int (*operation)(int, int) = add;

printf("%d\n", operation(10, 20));
```

---

# 14. C Dynamic Memory

Include:

```c
#include <stdlib.h>
```

---

## malloc()

```c
int *number = malloc(sizeof *number);

if (number != NULL)
{
    *number = 10;
}
```

---

## calloc()

```c
int *numbers = calloc(
    5,
    sizeof *numbers
);
```

---

## realloc()

```c
int *temporary = realloc(
    numbers,
    10 * sizeof *numbers
);

if (temporary != NULL)
{
    numbers = temporary;
}
```

---

## free()

```c
free(numbers);
numbers = NULL;
```

---

## Memory Leak

Memory allocated dynamically must eventually be released when it is no longer needed.

```c
int *value = malloc(sizeof *value);

/* use value */

free(value);
value = NULL;
```

---

# 15. C Structures

## Structure

```c
struct Student
{
    int id;
    char name[50];
    float marks;
};
```

---

## Declare Structure Variable

```c
struct Student student;
```

---

## Initialize Structure

```c
struct Student student = {
    1,
    "Ali",
    95.5f
};
```

---

## Access Members

```c
printf("%s\n", student.name);
```

---

## Array of Structures

```c
struct Student students[3];
```

---

## Nested Structure

```c
struct Address
{
    char city[50];
};

struct Student
{
    char name[50];
    struct Address address;
};
```

---

## Structure Pointer

```c
struct Student student = {
    1,
    "Ali",
    95.5f
};

struct Student *pointer = &student;

printf("%s\n", pointer->name);
```

---

## typedef with Structure

```c
typedef struct
{
    int id;
    char name[50];
} Student;

Student student;
```

---

# 16. C Unions

## Union

```c
union Data
{
    int integer_value;
    float float_value;
    char character;
};
```

Members share the same storage region.

---

## Union vs Structure

```text
Structure
→ each member has its own storage

Union
→ members share storage
```

---

# 17. C Enumerations

## enum

```c
enum Status
{
    STATUS_INACTIVE,
    STATUS_ACTIVE
};
```

Usage:

```c
enum Status status = STATUS_ACTIVE;
```

---

## Custom Enum Values

```c
enum Level
{
    LOW = 1,
    MEDIUM = 5,
    HIGH = 10
};
```

---

# 18. C typedef

## Basic typedef

```c
typedef unsigned long ulong;

ulong value = 100UL;
```

---

## typedef with Structure

```c
typedef struct
{
    int id;
    char name[50];
} Student;
```

---

## typedef with Pointer

```c
typedef int *IntPointer;

int value = 10;

IntPointer pointer = &value;
```

---

# 19. C Files

## fopen()

```c
FILE *file = fopen(
    "data.txt",
    "r"
);
```

Always check:

```c
if (file == NULL)
{
    perror("Unable to open file");
    return 1;
}
```

---

## fclose()

```c
fclose(file);
```

---

## fprintf()

```c
FILE *file = fopen(
    "data.txt",
    "w"
);

if (file != NULL)
{
    fprintf(file, "Hello C\n");
    fclose(file);
}
```

---

## fscanf()

```c
int number;

fscanf(file, "%d", &number);
```

---

## fgets()

```c
char buffer[100];

fgets(
    buffer,
    sizeof(buffer),
    file
);
```

---

## fputs()

```c
fputs(
    "Hello C\n",
    file
);
```

---

## fread()

```c
fread(
    buffer,
    sizeof(char),
    sizeof(buffer),
    file
);
```

---

## fwrite()

```c
fwrite(
    buffer,
    sizeof(char),
    length,
    file
);
```

---

## fseek()

```c
fseek(
    file,
    0,
    SEEK_SET
);
```

---

## ftell()

```c
long position = ftell(file);
```

---

## rewind()

```c
rewind(file);
```

---

## remove()

```c
remove("data.txt");
```

---

## rename()

```c
rename(
    "old.txt",
    "new.txt"
);
```

---

## Common File Modes

```text
r   Read
w   Write
a   Append
r+  Read and write
w+  Read and write, truncate/create
a+  Read and append
rb  Binary read
wb  Binary write
```

---

## EOF

```c
int character;

while (
    (character = fgetc(file)) != EOF
)
{
    putchar(character);
}
```

---

# 20. C Preprocessor

## #include

```c
#include <stdio.h>
#include <stdlib.h>
```

---

## #define

```c
#define PI 3.14159
```

---

## Macro

```c
#define SQUARE(x) ((x) * (x))
```

Macros should be used carefully because they are textual substitutions.

---

## Header File

Example:

```c
#ifndef MATH_TOOLS_H
#define MATH_TOOLS_H

int add(int a, int b);

#endif
```

---

## Conditional Compilation

```c
#ifdef DEBUG
printf("Debug mode\n");
#endif
```

---

## #ifndef

```c
#ifndef MY_HEADER_H
#define MY_HEADER_H

/* declarations */

#endif
```

---

## #pragma

Behavior may depend on compiler.

Example:

```c
#pragma once
```

`#pragma once` is widely supported but is not part of the ISO C standard.

---

# 21. C Error Handling

## perror()

```c
FILE *file = fopen(
    "missing.txt",
    "r"
);

if (file == NULL)
{
    perror("File error");
}
```

---

## errno

```c
#include <errno.h>

printf("%d\n", errno);
```

---

## strerror()

```c
#include <errno.h>
#include <string.h>

printf("%s\n", strerror(errno));
```

---

## assert()

```c
#include <assert.h>

int age = 20;

assert(age >= 0);
```

Assertions are normally used to detect programming assumptions during development.

---

# 22. C Bit Manipulation

## Set Bit

```c
value |= (1U << position);
```

---

## Clear Bit

```c
value &= ~(1U << position);
```

---

## Toggle Bit

```c
value ^= (1U << position);
```

---

## Check Bit

```c
if (value & (1U << position))
{
    printf("Bit is set\n");
}
```

---

## Bit Mask

```c
unsigned int mask = 0x0FU;

unsigned int result =
    value & mask;
```

---

# 23. C Memory Concepts

## Stack Memory

Automatic local objects commonly use stack-like runtime storage.

Example:

```c
void example(void)
{
    int value = 10;
}
```

---

## Heap Memory

Dynamically allocated memory:

```c
int *value = malloc(sizeof *value);
```

Release it:

```c
free(value);
```

---

## Typical Process Memory Concepts

Common conceptual regions include:

```text
Code / text
Read-only data
Initialized data
Zero-initialized data
Heap
Stack
```

Exact layout is implementation-specific.

---

# 24. C Command Line

## argc and argv

```c
#include <stdio.h>

int main(
    int argc,
    char *argv[]
)
{
    printf(
        "Argument count: %d\n",
        argc
    );

    for (int i = 0; i < argc; i++)
    {
        printf(
            "argv[%d] = %s\n",
            i,
            argv[i]
        );
    }

    return 0;
}
```

---

# 25. C Multi File Programs

Example structure:

```text
project/
├── main.c
├── math_tools.c
└── math_tools.h
```

---

## math_tools.h

```c
#ifndef MATH_TOOLS_H
#define MATH_TOOLS_H

int add(int a, int b);

#endif
```

---

## math_tools.c

```c
#include "math_tools.h"

int add(int a, int b)
{
    return a + b;
}
```

---

## main.c

```c
#include <stdio.h>

#include "math_tools.h"

int main(void)
{
    printf(
        "%d\n",
        add(10, 20)
    );

    return 0;
}
```

---

## Compile

Example with GCC:

```bash
gcc main.c math_tools.c -o app
```

---

# 26. C Standard Library

## stdio.h

Common functions:

```c
printf();
scanf();
getchar();
putchar();
puts();
fopen();
fclose();
```

---

## getchar()

```c
int character = getchar();
```

---

## putchar()

```c
putchar('A');
```

---

## puts()

```c
puts("Hello C");
```

---

## stdlib.h

Common functions:

```c
malloc();
calloc();
realloc();
free();
atoi();
atof();
exit();
```

---

## atoi()

```c
#include <stdlib.h>

int number = atoi("123");
```

For robust error checking, `strtol()` is usually more suitable.

---

## atof()

```c
double number = atof("12.5");
```

For robust conversion, `strtod()` is usually more suitable.

---

## exit()

```c
exit(EXIT_SUCCESS);
```

---

## string.h

Common functions:

```c
strlen();
strcpy();
strncpy();
strcat();
strcmp();
memset();
memcpy();
```

---

## memset()

```c
int numbers[5];

memset(
    numbers,
    0,
    sizeof(numbers)
);
```

---

## memcpy()

```c
int source[] = {1, 2, 3};
int destination[3];

memcpy(
    destination,
    source,
    sizeof(source)
);
```

---

## math.h

Common functions:

```c
sqrt()
pow()
ceil()
floor()
```

Example:

```c
#include <math.h>

double result = sqrt(25.0);
```

---

## abs()

```c
#include <stdlib.h>

int value = abs(-10);
```

---

## ctype.h

Common functions:

```c
isalpha()
isdigit()
isupper()
islower()
toupper()
tolower()
```

Example:

```c
#include <ctype.h>

if (isdigit((unsigned char)character))
{
    printf("Digit\n");
}
```

---

## time.h

Common functions:

```c
time()
clock()
difftime()
```

Example:

```c
#include <time.h>

time_t current_time =
    time(NULL);
```

---

# 27. Intermediate C Concepts

## Nested Functions

Nested function definitions are **not part of standard ISO C**.

Some compilers, such as GCC, support them as extensions.

---

## volatile

```c
volatile int status = 0;
```

`volatile` tells the compiler that accesses to the object are observable and should not be optimized away as ordinary redundant accesses.

It is not a replacement for thread synchronization.

---

## restrict

C99 feature:

```c
void copy_values(
    int *restrict destination,
    const int *restrict source,
    size_t count
)
{
    for (size_t i = 0; i < count; i++)
    {
        destination[i] = source[i];
    }
}
```

---

## const with Pointer

Pointer to const:

```c
const int *pointer;
```

Const pointer:

```c
int *const pointer = &value;
```

Const pointer to const:

```c
const int *const pointer = &value;
```

---

## Callback Function

```c
void execute(
    void (*callback)(void)
)
{
    callback();
}
```

Example:

```c
void greet(void)
{
    printf("Hello\n");
}

execute(greet);
```

---

## Generic Macros

C11 `_Generic`:

```c
#define TYPE_NAME(x) \
    _Generic((x), \
        int: "int", \
        double: "double", \
        default: "other" \
    )
```

Usage:

```c
printf(
    "%s\n",
    TYPE_NAME(10)
);
```

---

## Flexible Array Member

```c
struct Packet
{
    size_t length;
    unsigned char data[];
};
```

The flexible array member must be the final member of the structure.

---

# 28. C Projects

## 🎓 Student Management System

Suggested concepts:

```text
Structures
Functions
Arrays
Pointers
Strings
File Handling
Searching
Updating records
```

Basic data model:

```c
typedef struct
{
    int id;
    char name[50];
    float marks;
} Student;
```

---

## 📚 Library Management System

Suggested concepts:

```text
Structures
Strings
Functions
Pointers
Dynamic Memory
File Handling
Searching
Updating records
```

Basic data model:

```c
typedef struct
{
    int id;
    char title[100];
    char author[100];
    int available;
} Book;
```

---

# ⚡ Frequently Used C Headers

```c
#include <assert.h>
#include <ctype.h>
#include <errno.h>
#include <math.h>
#include <stdbool.h>
#include <stddef.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>
```

---

# ⚡ Frequently Used C Functions

```text
printf()
scanf()
fgets()
puts()
strlen()
strcmp()
memcpy()
memset()

malloc()
calloc()
realloc()
free()

fopen()
fclose()
fprintf()
fscanf()
fread()
fwrite()

sqrt()
pow()
abs()

isalpha()
isdigit()
toupper()
tolower()
```

---

# 🧠 Common C Patterns

## Array Length

For an actual array in the same scope:

```c
size_t length =
    sizeof(numbers)
    / sizeof(numbers[0]);
```

This does not work after the array has decayed to a pointer.

---

## Safe malloc Pattern

```c
int *numbers =
    malloc(
        count * sizeof *numbers
    );

if (numbers == NULL)
{
    return 1;
}
```

---

## Safe realloc Pattern

```c
int *temporary =
    realloc(
        numbers,
        new_count * sizeof *numbers
    );

if (temporary != NULL)
{
    numbers = temporary;
}
```

---

## Set Pointer to NULL After free

```c
free(pointer);
pointer = NULL;
```

---

## Check File Open

```c
FILE *file =
    fopen("data.txt", "r");

if (file == NULL)
{
    perror("data.txt");
    return 1;
}
```

---

# 🎯 C Learning Flow

```text
C Basics
   ↓
Output
   ↓
Input
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
Strings
   ↓
Pointers
   ↓
Dynamic Memory
   ↓
Structures
   ↓
Files
   ↓
Preprocessor
   ↓
Error Handling
   ↓
Memory Concepts
   ↓
Standard Library
   ↓
Intermediate C
   ↓
Projects
```

---

# 📘 Complete C Roadmap

For the complete topic-by-topic learning sequence:

## [Open the C Learning Roadmap →](../roadmaps/c-roadmap.md)

---

# 🌐 Learn C With A1Lab

A1Lab combines:

- 🎓 Structured C lessons
- 💻 Interactive coding
- 🧠 Visual explanations
- 🧪 Practical examples
- 📝 Practice activities
- ❓ MCQs and code challenges
- 💬 Developer discussions

<div align="center">

<a href="https://a1lab.tech/c/introduction">
  <img
    src="https://img.shields.io/badge/Start_C_Course-A1Lab-A8B9CC?style=for-the-badge&logo=c&logoColor=black"
    alt="Start C Course on A1Lab"
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

# 🔵 Learn. Code. Build.

### C quick reference from fundamentals to memory-level programming.

**A1Lab Learning Resources**

### [Start Learning C →](https://a1lab.tech/c/introduction)

</div>
