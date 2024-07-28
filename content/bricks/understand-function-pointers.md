---
title: Understand Function Pointers
draft: false
tags:
  - pointer
  - gist
---

Function pointers allow you to pass around and call functions like regular variables. They are powerful but can be confusing at first. This post will walk through how to declare, use, and pass function pointers in C.

> A function pointer is a pointer that holds the address of a function. This provides us with another way of executing functions in an order that ==may not be known at compile time and without using conditional statements==. _By Richard Reese_

## Declaring function pointers

To declare a function pointer, you specify the return type and parameters just like a regular function declaration, but with an asterisk `*` before the name:

```c
int (*fptrFoo)(int, float);
```

> [!tip]
> One suggested naming convention for function pointers is to always begin their name with the prefix: `fptr`.

Do not confuse functions that return a pointer with function pointers.

```c
int *func(); // a function that returns a pointer to an integer
int* func(); // rearrange whitespace for the readability
```

## Using a function pointer

To use a function pointer, you first define a function with the same signature as the pointer:

```c
int (*fptr1)(int, float);

int add(int x, float y) {
    return x + (int)y;
}
```

Then assign it to the pointer:

```c
fptr1 = add;
int result = fptr1(1, 2.14);
```

> [!note]
> We could have used the address-of operator with the function name as `fptr1 = &add`, but it is not necessary and is redundant. The compiler will effectively ignore the address-of operator when used in this context.

### Bonus

It is suggested to declare a **type definition** for function pointers. Check out 👉 [[master-function-pointers |here]] for more information.

## Passing function pointers

You can pass function pointers as arguments just like regular pointers:

```c
int sub(int x, float y) {
    return x - (int)y;
}

typedef int (*fptrOperation)(int, float);

int compute(fptrOperation operation, int x, float y) {
    return operation(x, y);
}

printf("%d\n",compute(add, 10, 6.5));
printf("%d\n",compute(sub, 10, 6.5));
```

The function signature must match the pointer.

## Returning function pointers

You can create an array of function pointers that can be indexed and called:

```c
fptrOperation select(char opcode) {
    switch(opcode) {
        case '+': return add;
        case '-': return sub;
    }
}

int evaluate(char opcode, int x, float y) {
    fptrOperation operation = select(opcode);
    return operation(x, y);
}
```

Again, the signatures must match up.

## Using an array of function pointers

You can create an array of function pointers that can be indexed and called:

```c
fptrOperation operations[2] = {add, sub};
```

Alternatively, you can declare this array without using a typedef as shown below:

```c
int (*operations[10])(int, float) = {NULL};
```

This provides a simple way to store and lookup functions.

## Summary

Understanding program memory structures like the stack and heap provides deeper insight into pointer behavior. Local variables live on the stack, while dynamic memory lives on the heap, this explains why returning a pointer to a local variable is problematic. While passing a pointer to constant data is efficient and prevents the function from modifying the data passed. And passing a pointer to a pointer allows the argument pointer to be reassigned to a different location in memory.

Function pointers specifically enable flexible control flow by calling different functions based on runtime needs. The key is making sure the function signatures match the pointer declarations.
