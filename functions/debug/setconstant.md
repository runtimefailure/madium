---
description: Sets a constant in a function at the specified index.
icon: code-simple
---

# setconstant



## Syntax

```lua
debug.setconstant(func: function | number, index: number, value: any) -> void
```

## Parameters

| Parameter | Type                   | Description                    |
| --------- | ---------------------- | ------------------------------ |
| `func`    | `function` or `number` | The function or stack level    |
| `index`   | `number`               | The constant index (1-based)   |
| `value`   | `any`                  | The new value for the constant |

## Returns

This function does not return a value.

## Description

`debug.setconstant` modifies a constant value in a function's bytecode. This allows you to change literal values that the function uses.

## Example

```lua
local function greet()
    return "Hello, World!"
end

print(greet()) -- "Hello, World!"

-- Find and change the string constant
local constants = debug.getconstants(greet)
for i, v in pairs(constants) do
    if v == "Hello, World!" then
        debug.setconstant(greet, i, "Goodbye, World!")
        break
    end
end

print(greet()) -- "Goodbye, World!"
```

## Caution

{% hint style="warning" %}
Modifying constants can cause unexpected behavior if:

* The constant is used in multiple places
* You set an incompatible type
* The bytecode expects a specific value
{% endhint %}

## Use Cases

* **Patching**: Change hardcoded values in game scripts
* **Testing**: Modify behavior without changing source
* **Bypasses**: Alter check values

## Related Functions

* [`debug.getconstant`](getconstant.md) - Get a constant
* [`debug.getconstants`](getconstants.md) - Get all constants
