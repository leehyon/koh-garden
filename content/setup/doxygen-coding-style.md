---
title: "Doxygen Coding Style"
tags:
  - style
---

## Best practices

- Do not use `@a`. Instead use `@param` to document function parameters.
- Do not use `@return`. Instead use `@retval` to document return status codes.
- Do not write documentation for trivial functions.
- Do not repeat documentation, use `@see` for example.
- Do not use `@note`.
- Use groups and arrange them in a hierarchy. Put every file into at least one group.
- Use dot comments for state diagrams.
- Use one whitespace character after an asterisk.

## Header file example

### Header blocks

Header files should contain the similar comment blocks as other source files, described at coding-file-hdr.

```c
/**
 * @file
 *
 * @ingroup FlipFlop
 *
 * @brief Flip-Flop API
 */

/*
 * Copyright (c) YYYY Author.
 *
 * The license and distribution terms for this file may be
 * found in the file LICENSE in this distribution or at
 * http://www.rtems.com/license/LICENSE.
 */
```

### Header guard

After the comment blocks, use a header guard that assembles at least the include path of the file. For example, if `flipflop.h` is in `<rtems/lib/flipflop.h>` then

```c
#ifndef RTEMS_LIB_FLIP_FLOP_H
#define RTEMS_LIB_FLIP_FLOP_H
```

### Includes

Then add your include files before protecting C declarations from C++.

```c
#include <rtems.h>

#ifdef __cplusplus
extern "C" {
#endif /* __cplusplus */
```

### Using @defgroup for group definitions

Add any group definitions surrounding the function declarations that belong in that group. Rarely, a header may define more than one group. Here we use a dot diagram.

```c
/**
 * @defgroup FlipFlop Flip-Flop
 *
 * @brief Simple Flip-Flop state machine.
 *
 * @dot
 *   digraph {
 *     start [label="START"];
 *     flip [label="FLIP"];
 *     flop [label="FLOP"];
 *     flip -> flop [label="flop()", URL="\ref flop"];
 *     flop -> flip [label="flip()", URL="\ref flip"];
 *     start -> flip
 *       [label="flip_flop_initialize(FLIP)", URL="\ref flip_flop_initialize"];
 *     start -> flop
 *       [label="flip_flop_initialize(FLOP)", URL="\ref flip_flop_initialize"];
 *     flip -> start
 *       [label="flip_flop_restart()", URL="\ref flip_flop_restart"];
 *   }
 * @enddot
 *
 * @{
 */
```

### enum and struct

Provide documentation for declarations of enumerated types and structs. Use typedefs for structs, and do not use `_t` as a typename suffix.

```c
/**
 * @brief The set of possible flip-flop states.
 *
 * Enumerated type to define the set of states for a flip-flop.
 */
typedef enum {
  START = 0,
  FLIP,
  FLOP
} flip_flop_state;

/**
 * @brief Object containing multiple flip-flops.
 *
 * Encapsulates multiple flip-flops.
 */
typedef struct {
  /**
   * @brief Primary flip-flop.
   */
  flip_flop_state primary;
  /**
   * @brief Secondary flip-flop.
   */
  flip_flop_state secondary;
} flip_flop_multiple;
```

### Using @name for organization

Complicated groups can be given additional organization by using `@name`, or by declaring additional groups within the hierarchy of the header file’s top-level group.

```c
/**
 * @name Flip-Flop Maintenance
 *
 * @{
 */
```

### Declaring functions

Function declarations should have an @brief that states what the function does in a single topic sentence starting with a descriptive verb in the present tense.

```c
/**
 * @brief Initializes the flip-flop state.
 *
 * @param[in] state The initial state to set the flip-flop.
 *
 * @retval RTEMS_SUCCESSFUL Successfully initialized.
 * @retval RTEMS_INCORRECT_STATE Flip-flop state is not valid.
 */
rtems_status_code flip_flop_initialize(flip_flop_state state);

/**
 * @brief Restarts the flip-flop.
 *
 * @retval RTEMS_SUCCESSFUL Successfully restarted.
 * @retval RTEMS_INCORRECT_STATE Flip-flop not in flip state.
 */
rtems_status_code flip_flop_restart(void);
```

Do not document trivial functions, such as getter/setter methods.

```c
flip_flop_state flip_flop_current_state(void);
```

Close the documentation name definition and open a new name definition.

```c
/** @} */

/**
 * @name Flip-Flop Usage
 *
 * @{
 */

/**
 * @brief Flip operation.
 *
 * @retval RTEMS_SUCCESSFUL Flipped successfully.
 * @retval RTEMS_INCORRECT_STATE Incorrect state for flip operation.
 */
rtems_status_code flip( void );

/**
 * @brief Flop operation.
 *
 * @retval RTEMS_SUCCESSFUL Flopped successfully.
 * @retval RTEMS_INCORRECT_STATE Incorrect state for flop operation.
 */
rtems_status_code flop( void );

/** @} */
```

### Ending the file

Close the documentation group definition, then the extern C declarations, then the header guard.

```c
 /** @} */

 #ifdef __cplusplus
 }
 #endif /* __cplusplus */

 #endif /* RTEMS_LIB_FLIP_FLOP_H */

No newline at the end of the file.
```

## Source file example

```c
/**
 * @file
 *
 * @ingroup FlipFlop
 *
 * @brief Flip-Flop implementation.
 */

/*
 * Copyright (c) YYYY Author.
 *
 * The license and distribution terms for this file may be
 * found in the file LICENSE in this distribution or at
 * http://www.rtems.com/license/LICENSE.
 */

#include <rtems/lib/flipflop.h>

static flip_flop_state current_state;

rtems_status_code flip_flop_initialize(flip_flop_state state)
{
  if (current_state == START) {
    current_state = state;

    return RTEMS_SUCCESSFUL;
  } else {
    return RTEMS_INCORRECT_STATE;
  }
}

rtems_status_code flip_flop_restart(void)
{
  if (current_state == FLIP) {
    current_state = START;

    return RTEMS_SUCCESSFUL;
  } else {
    return RTEMS_INCORRECT_STATE;
  }
}

flip_flop_state flip_flop_current_state(void)
{
  return current_state;
}

rtems_status_code flip(void)
{
  if (current_state == FLOP) {
    current_state = FLIP;

    return RTEMS_SUCCESSFUL;
  } else {
    return RTEMS_INCORRECT_STATE;
  }
}

rtems_status_code flop(void)
{
  if (current_state == FLIP) {
    current_state = FLOP;

    return RTEMS_SUCCESSFUL;
  } else {
    return RTEMS_INCORRECT_STATE;
  }
}
```

### Files

Document files with the `@file` directive omitting the optional filename argument. Doxygen will infer the filename from the actual name of the file. Within one Doxygen run all files are unique and specified by the current Doxyfile. We can define how the generated output of path and filenames looks like in the Doxyfile via the `FULL_PATH_NAMES`, `STRIP_FROM_PATH` and `STRIP_FROM_INC_PATH` options.

### Functions

For documentation of function arguments there are basically to ways:

The first one uses `@param`:

```c
/**
 * @brief Copies from a source to a destination memory area.
 *
 * The source and destination areas may not overlap.
 *
 * @param[out] dest The destination memory area to copy to.
 * @param[in] src The source memory area to copy from.
 * @param[in] n The number of bytes to copy.
 */
```

The second is to use `@a` param in descriptive text, for example:

```c
/**
* Copies @a n bytes from a source memory area @a src to a destination memory
* area @a dest, where both areas may not overlap.
*/
```

The `@a` indicates that the next word is a function argument and deserves some kind of highlighting. However, we feel that `@a` buries the usage of function arguments within description text. In RTEMS sources, we prefer to use `@param` instead of `@a`.

## Learn more

- [4.3.5. General Doxygen Recommentations](https://ftp.rtems.org/pub/rtems/people/joel/sw_eng_hb/eng/coding-doxygen.html#)
- [Doxygen style guide](http://micro-os-plus.github.io/develop/doxygen-style-guide/)
