---
description: >-
  The Closures library allows for viewing info about a closures origin and
  allowing the manipulation of said closure.
icon: shield-keyhole
---

# Closures



## Overview

This library provides tools to:

* **Inspect** closures to determine their type and origin
* **Modify** closures by hooking or replacing them
* **Create** new closures with specific properties

## Available Functions

| Function                                    | Description                               |
| ------------------------------------------- | ----------------------------------------- |
| [`checkcaller`](checkcaller.md)             | Check if the current call is from volt    |
| [`clonefunction`](clonefunction.md)         | Create a copy of a function               |
| [`getfunctionhash`](getfunctionhash.md)     | Get the hash of a function's bytecode     |
| [`hookfunction`](hookfunction.md)           | Replace a function with another           |
| [`hookmetamethod`](hookmetamethod.md)       | Hook a metatable metamethod               |
| [`iscclosure`](iscclosure.md)               | Check if a function is a C closure        |
| [`isexecutorclosure`](isexecutorclosure.md) | Check if a function is from volt          |
| [`isfunctionhooked`](isfunctionhooked.md)   | Check if a function has been hooked       |
| [`islclosure`](islclosure.md)               | Check if a function is a Luau closure     |
| [`isnewcclosure`](isnewcclosure.md)         | Check if a function is a newcclosure      |
| [`newcclosure`](newcclosure.md)             | Wrap a Luau function as a C closure       |
| [`newlclosure`](newlclosure.md)             | Wrap a C closure as a Luau closure        |
| [`restorefunction`](restorefunction.md)     | Restore a hooked function to its original |
| [`setstackhidden`](setstackhidden.md)       | Hide a function from stack traces         |

## Closure Types

There are two main types of closures:

### C Closures

Functions implemented in C/C++. These are typically:

* Built-in Lua functions like `print`, `type`
* Roblox API methods
* Majority of custom functions

### Luau Closures

Functions written in Luau. These are typically:

* User-defined functions
* Game Script functions
