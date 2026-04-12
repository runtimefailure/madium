---
description: >-
  The oth library provides secure alternatives to hookfunction for C functions.
  Hooks are executed on separate threads, providing better isolation and safety.
icon: fishing-rod
---

# Oth



## Overview

The `oth` library allows you to:

* Hook C functions securely on separate threads
* Remove hooks when no longer needed
* Access the original function even after multiple hooks
* Detect if code is running in a hook thread

## Available Functions

| Function                                        | Description                            |
| ----------------------------------------------- | -------------------------------------- |
| [`oth.hook`](hook.md)                           | Hook a C function on a separate thread |
| [`oth.unhook`](unhook.md)                       | Remove a hook created with `oth.hook`  |
| [`oth.get_root_callback`](get_root_callback.md) | Get the original function              |
| [`oth.is_hook_thread`](is_hook_thread.md)       | Check if running in a hook thread      |
| [`get_original_thread`](get_original_thread.md) | Get the original thread                |

## Why Use oth?

Unlike `hookfunction`, `oth.hook` executes hooks on separate threads, providing:

* **Better isolation** - Hooks don't interfere with the main thread
* **Improved safety** - Reduces risk of crashes from hook conflicts
* **Thread awareness** - Know when you're in a hook context

## Related Libraries

* [`closures`](https://docs.volt.bz/docs/closures) - Standard function hooking with `hookfunction`
