---
description: Replaces a cached instance reference with another.
icon: code-simple
---

# replace



## Syntax

```lua
cache.replace(instance: Instance, replacement: Instance) -> void
```

## Parameters

| Parameter     | Type       | Description              |
| ------------- | ---------- | ------------------------ |
| `instance`    | `Instance` | The instance to replace  |
| `replacement` | `Instance` | The replacement instance |

## Returns

This function does not return a value.

## Description

`cache.replace` replaces a cached instance reference with another instance. All existing references to the original instance will now point to the replacement.

## Example

```lua
local original = workspace.Part
local replacement = Instance.new("Part")
replacement.Name = "FakePart"

-- Replace the cached reference
cache.replace(original, replacement)

-- Now any access to the original returns the replacement
print(workspace.Part.Name) -- "FakePart"
```

## Notes

* Use with caution as this affects all references
* The original instance still exists

## Related Functions

* [`cache.invalidate`](invalidate.md) - Remove from cache
* [`cache.iscached`](iscached.md) - Check if cached
