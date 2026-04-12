---
description: Removes an instance from the reference cache.
icon: code-simple
---

# invalidate



## Syntax

```lua
cache.invalidate(instance: Instance) -> void
```

## Parameters

| Parameter  | Type       | Description                |
| ---------- | ---------- | -------------------------- |
| `instance` | `Instance` | The instance to invalidate |

## Returns

This function does not return a value.

## Description

`cache.invalidate` removes an instance from the internal reference cache. The next access to this instance will create a new reference.

## Example

```lua
local part = workspace.Part

-- Store a reference
local ref1 = part

-- Invalidate the cache
cache.invalidate(part)

-- New reference is created
local ref2 = workspace.Part

print(ref1 == ref2) -- May be false
```

## Notes

* Used for advanced instance manipulation
* Affects how references are tracked

## Related Functions

* [`cache.replace`](replace.md) - Replace cached instance
* [`cache.iscached`](iscached.md) - Check if cached
