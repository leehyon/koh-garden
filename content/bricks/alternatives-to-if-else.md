---
title: Alternatives to If-Else
date: 2024-06-11
draft: false
tags:
  - gist
---

There are several alternatives to using if-else statements in C besides switch statements. These alternatives can often lead to more readable, maintainable, and efficient code. Let's explore some of these options:

## Ternary operator

The ternary operator provides a concise way to write simple if-else statements in a single line:

```c
result = (condition) ? value_if_true : value_if_false;
```

## Lookup tables

For scenarios where you need to map inputs to outputs, especially with numeric or enum types:

```c
typedef struct {
    const char* colorName;
    const char* colorCode;
} ColorCode;

const ColorCode colorTable[] = {
    {"blue", "#2196F3"},
    {"green", "#4CAF50"},
    {"orange", "#FF9800"},
    {"pink", "#E91E63"},
    {"default", "#F44336"}
};

const char* SetBackgroundColor(const char* colorName) {
    int i;
    for (i = 0; i < sizeof(colorTable) / sizeof(colorTable[0]); i++) {
        if (strcmp(colorName, colorTable[i].colorName) == 0) {
            return colorTable[i].colorCode;
        }
    }
    return colorTable[4].colorCode; // default color
}
```

## Function pointers

Useful for selecting behavior based on conditions:

```c
typedef void (*FuncType)();

FuncType funcTable[] = {Func1, Func2, Func3};

int index = GetIndex(); // Determine which function to call
funcTable[index](); // Call the appropriate function
```

## Bitwise operations

For flag-based conditions or optimizing multiple boolean checks:

```c
unsigned int flags = FLAG_A | FLAG_B;
if (flags & FLAG_A) {
    // Action for FLAG_A
}
```

> [!summary]
> Each of these alternatives has its own use cases and trade-offs. The choice depends on the specific requirements of your program, readability considerations, and performance needs.
