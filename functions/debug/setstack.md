---
description: Sets a value on the stack at a specific level and index.
icon: code-simple
---

# setstack



## Syntax

```lua
debug.setstack(level: number, index: number, value: any) -> void
```

## Parameters

| Parameter | Type     | Description                            |
| --------- | -------- | -------------------------------------- |
| `level`   | `number` | The stack level (1 = current function) |
| `index`   | `number` | The stack slot index                   |
| `value`   | `any`    | The new value to set                   |

## Returns

This function does not return a value.

## Description

`debug.setstack` modifies a value on the call stack. This can change local variables in any active function on the stack.

## Example

```lua
local function modifier()
    debug.setstack(2, 1, "modified!")
end

local function example()
    local value = "original"
    modifier()
    print(value) -- "modified!"
end

example()
```

## Caution

{% hint style="warning" %}
Modifying stack values can cause crashes or undefined behavior if:

* You set an incompatible type
* The index doesn't exist
* The value is used in unexpected ways
{% endhint %}

## Related Functions

* [`debug.getstack`](getstack.md) - Get a stack value
