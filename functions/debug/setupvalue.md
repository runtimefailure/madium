---
description: Sets an upvalue in a function by index.
icon: code-simple
---

# setupvalue



## Syntax

```
debug.setupvalue(func: function | number, index: number, value: any) -> void
```

## Parameters

| Parameter | Type                   | Description                   |
| --------- | ---------------------- | ----------------------------- |
| `func`    | `function` or `number` | The function or stack level   |
| `index`   | `number`               | The upvalue index (1-based)   |
| `value`   | `any`                  | The new value for the upvalue |

## Returns

This function does not return a value.

## Description

`debug.setupvalue` modifies an upvalue (captured variable) in a function. Changes affect the shared variable, so all functions that capture the same upvalue will see the change.

## Example

```lua
local count = 0

local function getCount()
    return count
end

local function increment()
    count = count + 1
end

print(getCount()) -- 0

-- Directly modify the upvalue
debug.setupvalue(getCount, 1, 100)

print(getCount()) -- 100
increment()
print(getCount()) -- 101
```

## Shared Upvalues

When multiple functions share an upvalue, modifying it affects all of them:

```lua
local shared = "original"

local function read()
    return shared
end

local function write(val)
    shared = val
end

-- Both functions share the same upvalue
debug.setupvalue(read, 1, "modified")

print(read())  -- "modified"
print(write)   -- The write function also sees the change
```

## Related Functions

* [`debug.getupvalue`](getupvalue.md) - Get an upvalue
* [`debug.getupvalues`](getupvalues.md) - Get all upvalues
