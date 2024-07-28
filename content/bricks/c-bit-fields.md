---
title: C Bit Fields
draft: false
tags:
  - c
  - gist
---

## Motivation

When programming close to the hardware, you often need to manipulate bits and flags efficiently. Doing this with bitwise operators and macros can get messy:

```c
#define FLAG1 0x01 
#define FLAG2 0x02

unsigned int flags = FLAG1 | FLAG2;

if (flags & FLAG1) {
    // do something for FLAG1
}
```

**Bit fields** provide a cleaner way to work with bits and flags in C structures.

## Syntax

```c
type [declarator] : width;
```

- The `type` for the `declarator` must be `unsigned int`, `signed int`, or `int`.
- The `width` must be less than or equal to the size of the underlying `type`.

## Improved readability

With bit fields, the code reads more like accessing normal struct members:

```c
struct {
    unsigned int FLAG1 : 1;
    unsigned int FLAG2 : 1; 
} flags;

flags.FLAG1 = 1; 

if (flags.FLAG1) {
    // do something for FLAG1
}
```

And it is obviously less error-prone.

## Memory optimization

Bit fields also enable packing data efficiently into the smallest space needed. For example, if you write:

```c
struct {
    unsigned int isKeyword;
    unsigned int isExtern;
    unsigned int isStatic;
} flags;
```

You will use at least `3 * sizeof(unsigned int)` or 12 bytes to represent three small flags, that should only need three bits.

So if you write:

```c
struct {
    unsigned int isKeyword : 1;
    unsigned int isExtern : 1;
    unsigned int isStatic : 1;
} flags;
```

This uses up the same space as one `unsigned int`, which is 4 bytes.

## Hardware registers

Besides, bit fields are commonly used to represent hardware registers. If a 32-bit system register has a meaning for each bit, you can define it like:

```c
struct {
    unsigned int power : 1;
    unsigned int clock : 1;
    //...
} systemRegisters;
```

This maps cleanly to the hardware while abstracting away the nitty-gritty of bit shifts.

> [!note]
> Bit fields can also be used to store values larger than one bit, although flags are more common.

```c
struct {
    unsigned short icon : 8;
    unsigned short color : 4;
    unsigned short underline : 1;
    unsigned short blink : 1;
} screen[25][80]; // The size of each structure is 2 bytes.
```

## Learn more

- [C Bit Fields | Microsoft Learn](https://learn.microsoft.com/en-us/cpp/c-language/c-bit-fields?view=msvc-170)