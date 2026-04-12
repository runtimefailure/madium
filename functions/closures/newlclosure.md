---
description: Wraps a C closure to appear as a Luau closure.
icon: code-simple
---

# newlclosure



## Syntax

```
newlclosure(func: function) -> function
```

## Parameters

| Parameter | Type       | Description           |
| --------- | ---------- | --------------------- |
| `func`    | `function` | The C closure to wrap |

## Returns

| Type       | Description                                             |
| ---------- | ------------------------------------------------------- |
| `function` | A Luau closure wrapper that calls the original function |

## Description

`newlclosure` wraps a C closure so that it appears to be a Luau closure when inspected. The wrapped function behaves identically but `islclosure` will return `true` for it.

## Example

```lua
-- print is a C closure
print(iscclosure(print)) -- true
print(islclosure(print)) -- false

-- Wrap it as a Luau closure
local wrappedPrint = newlclosure(print)

-- Now it appears as a Luau closure
print(iscclosure(wrappedPrint)) -- false
print(islclosure(wrappedPrint)) -- true

-- But still works the same
wrappedPrint("Hello!") -- Output: Hello!
```

## Notes

* The wrapper has minimal performance overhead

## Related Functions

* [`newcclosure`](newcclosure.md) - Wrap as C closure
* [`islclosure`](islclosure.md) - Check if Luau closure
* [`iscclosure`](iscclosure.md) - Check if C closure
