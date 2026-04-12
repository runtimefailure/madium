---
description: Checks if an instance is in the reference cache.
icon: code-simple
---

# iscached



## Syntax

```lua
cache.iscached(instance: Instance) -> boolean
```

## Parameters

| Parameter  | Type       | Description           |
| ---------- | ---------- | --------------------- |
| `instance` | `Instance` | The instance to check |

## Returns

| Type      | Description                    |
| --------- | ------------------------------ |
| `boolean` | True if the instance is cached |

## Description

`cache.iscached` checks whether an instance currently exists in the reference cache.

## Example

```lua
local part = workspace.Part

if cache.iscached(part) then
    print("Part is cached")
else
    print("Part is not cached")
end

-- After invalidation
cache.invalidate(part)
print(cache.iscached(part)) -- false
```

## Related Functions

* [`cache.replace`](replace.md) - Replace cached instance
* [`cache.invalidate`](invalidate.md) - Remove from cache
