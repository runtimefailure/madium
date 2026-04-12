---
description: Checks if a function is a newcclosure wrapper.
icon: code-simple
---

# isnewcclosure



## Syntax

```lua
isnewcclosure(func: function) -> boolean
```

## Aliases

* `iscustomcclosure`

## Parameters

| Parameter | Type       | Description           |
| --------- | ---------- | --------------------- |
| `func`    | `function` | The function to check |

## Returns

| Type      | Description                                 |
| --------- | ------------------------------------------- |
| `boolean` | True if function was created by newcclosure |

## Description

`isnewcclosure` checks whether a function was wrapped using `newcclosure`.

## Example

```lua
local function luaFunc()
    return "lua"
end

local wrapped = newcclosure(luaFunc)

print(isnewcclosure(luaFunc)) -- false
print(isnewcclosure(wrapped)) -- true
print(isnewcclosure(print))   -- false (native C closure)
```

## Notes

* Useful for distinguishing between native C closures and wrapped functions
* Returns false for native C closures like `print`

## Related Functions

* [`newcclosure`](newcclosure.md) - Wrap as C closure
* [`iscclosure`](iscclosure.md) - Check if C closure
* [`islclosure`](islclosure.md) - Check if Luau closure
