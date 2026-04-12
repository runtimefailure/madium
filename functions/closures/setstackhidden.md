---
description: Sets whether a function is hidden from stack traces.
icon: code-simple
---

# setstackhidden



## Syntax

```lua
setstackhidden(func: function, hidden: boolean) -> void
```

## Parameters

| Parameter | Type       | Description                |
| --------- | ---------- | -------------------------- |
| `func`    | `function` | The function to modify     |
| `hidden`  | `boolean`  | Whether to hide from stack |

## Returns

This function does not return a value.

## Description

`setstackhidden` controls whether a function appears in stack traces and debug info. Hidden functions are invisible to stack inspection.

## Example

```lua
local function secretFunc()
    print("This function is hidden!")
end

setstackhidden(secretFunc, true)

-- Now secretFunc won't appear in debug.traceback()
```

## Use Cases

* Hiding hook implementations
* Preventing detection via stack inspection
* Clean stack traces

## Related Functions

* [`debug.getinfo`](https://docs.volt.bz/docs/debug/getinfo) - Get function info
* [`debug.getcallstack`](https://docs.volt.bz/docs/debug/getcallstack) - Get call stack
