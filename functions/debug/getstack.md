---
description: Gets a value from the stack at a specific level and index.
icon: code-simple
---

# getstack



## Syntax

```
debug.getstack(level: number, index: number) -> any
```

## Parameters

| Parameter | Type     | Description                            |
| --------- | -------- | -------------------------------------- |
| `level`   | `number` | The stack level (1 = current function) |
| `index`   | `number` | The stack slot index                   |

## Returns

| Type  | Description                               |
| ----- | ----------------------------------------- |
| `any` | The value at the specified stack position |

## Description

`debug.getstack` retrieves a value from the call stack. This allows you to read local variables and temporary values from any level of the current call stack.

## Example

```lua
local function level2()
    local secret = "hidden value"
    level1()
end

local function level1()
    -- Get the 'secret' variable from level2
    local value = debug.getstack(2, 1)
    print(value) -- "hidden value"
end

level2()
```

## Stack Levels

| Level | Meaning              |
| ----- | -------------------- |
| 1     | Current function     |
| 2     | Calling function     |
| 3     | Caller of the caller |
| ...   | And so on            |

## Notes

* Stack indices correspond to local variable slots
* The exact index depends on the function's compiled bytecode
* Values may include locals, parameters, and temporaries

## Related Functions

* [`debug.setstack`](setstack.md) - Modify a stack value
