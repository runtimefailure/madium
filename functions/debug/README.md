---
description: >-
  The Debug library provides functions for runtime inspection of Luau functions,
  including access to constants, upvalues, protos, and stack values.
icon: bug
---

# Debug



## Overview

These functions allow you to:

* **Inspect** function internals (constants, upvalues, protos)
* **Modify** function behavior at runtime
* **Access** the call stack

## Available Functions

| Function                                | Description                                   |
| --------------------------------------- | --------------------------------------------- |
| [`debug.getcallstack`](getcallstack.md) | Get the current call stack                    |
| [`debug.getconstant`](getconstant.md)   | Get a constant from a function                |
| [`debug.getconstants`](getconstants.md) | Get all constants from a function             |
| [`debug.getinfo`](getinfo.md)           | Get information about a function              |
| [`debug.getproto`](getproto.md)         | Get a proto (nested function) from a function |
| [`debug.getprotos`](getprotos.md)       | Get all protos from a function                |
| [`debug.getstack`](getstack.md)         | Get a value from the stack                    |
| [`debug.getupvalue`](getupvalue.md)     | Get an upvalue from a function                |
| [`debug.getupvalues`](getupvalues.md)   | Get all upvalues from a function              |
| [`debug.setconstant`](setconstant.md)   | Set a constant in a function                  |
| [`debug.setstack`](setstack.md)         | Set a value on the stack                      |
| [`debug.setupvalue`](setupvalue.md)     | Set an upvalue in a function                  |
| [`debug.validlevel`](validlevel.md)     | Check if a stack level is valid               |

## Terminology

### Constants

Values embedded directly in the function's bytecode. These include:

* String literals
* Numbers
* Booleans
* `nil`

### Upvalues

Variables captured from the enclosing scope. When a function references a variable from outside its own scope, that variable becomes an upvalue.

### Protos

Nested function definitions within a function. These are the "prototypes" of inner functions.

### Stack

The call stack containing local variables and temporary values for the current execution context.
