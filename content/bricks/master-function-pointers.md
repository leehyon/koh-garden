---
title: Master Function Pointers
draft: false
tags:
  - pointer
  - gist
---

💡 _The post is primarily inspired by [this article](http://vandervoord.net/blog/2015/6/2/making-function-pointers-usable-in-c), click to read more._

## Motivation

Function pointers in C have a reputation for being difficult to use and prone to bugs. The syntax is confusing, and misusing them can lead to crashes or undefined behavior. However, when applied carefully, function pointers enable flexible and extensible code. In this post, I'll explore best practices for making function pointers more readable, safe, and usable in C.

Please refer to 👉 [[understand-function-pointers|my previous post]] for an introduction to the basics of function pointers.

## Readable syntax with typedefs

The syntax for declaring raw function pointer types in C is messy:

```c
// DO NOT define your function pointer directly
int16_t (*funcPtr)(int8_t); 
// This is even worse
int16_t OuterFunc(int16_t val, int16_t (*innerFunc)(int8_t)); 
```

A better approach is to **typedef** the function pointer:

```c
typedef int16_t (*FuncType)(int8_t); 
FuncType funcPtr;
int16_t OuterFunc(int16_t val, FuncType innerFunc);
```

This makes the code more readable and allows catching errors at compile time. Use descriptive typedefs for all function pointer types.

## Safety first

Use `const` to prevent accidentally modifying function pointers:

```c
const FuncType funcPtr = YourFunction;
```

Always check for `NULL` before calling a function pointer:

```c
if (funcPtr != NULL) { 
    int16_t result = funcPtr(args);
}
```

When indexing function pointer arrays, validate the bounds:

```c
if (index < 0 || index >= MAX_FUNCS) {
    HandleError(); 
}
```

Consider an error handler function as the last entry in the array to catch off-by-one errors.

## Uses cases

Some common uses cases are:

- Dispatch tables/switch statements
- Plugin architectures
- Asynchronous callbacks/events
- Decoupling event sources from handlers

## Code snippets

Define a typedef for the function pointer:

```c
typedef int16_t (*FuncType)(void *data);
```

Declare a function pointer variable:

```c
const FuncType myCallback = NULL;
```

Define a function accepting a function pointer argument:

```c
void RegisterCallback(const FuncType callback) {
    if (callback != NULL) {
        // register the callback
    }
}
```

An array of function pointers acting as a dispatch table:

```c
typedef void (*CommandFunc)(void);

const CommandFunc commands[] = {
    command1,
    command2,
    command3,
    errorHandler // last entry is error handler 
};

void Dispatch(int8_t cmd) {
    if (cmd < 0 || cmd >= MAX_COMMANDS) {
        commands[MAX_COMMANDS](); // call error handler
    } else {
        commands[cmd](); // call command handler
    }
}
```

Using a function pointer for a plugin architecture:

```c
typedef int16_t (*PluginInitFunc)(void);

int16_t LoadPlugin(PluginInitFunc initFunc) {
    if (initFunc != NULL) {
        return InitFunc(); // call plugin's init function
    }
    return -1;
}
```

## Conclusion

With some care taken to use typedefs, validation, and bounds checking, function pointers can be used effectively in C without introducing bugs. They enable useful patterns like dispatch tables and callbacks while avoiding common pitfalls. 

1. Use **typedefs** to define cleaner syntax for function pointer types. This makes the code more readable.
2. Declare function pointers as **constant** whenever possible to prevent accidental modification.
3. Always validate that function pointers are not `NULL` before use.
4. Do **bounds checking** when indexing into arrays of function pointers to avoid calling invalid functions.
5. Consider using an **error handling** function as the last entry in a function pointer array to catch off-by-one errors.
6. Fill any "holes" in function pointer arrays with **default handler** functions rather than nulls.
