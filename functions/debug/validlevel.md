---
description: Checks if a stack level is valid.
icon: code-simple
---

# validlevel



## Syntax

```lua
debug.validlevel(level: number) -> boolean
```

## Aliases

* `debug.isvalidlevel`

## Parameters

| Parameter | Type     | Description     |
| --------- | -------- | --------------- |
| `level`   | `number` | The stack level |

## Returns

| Type      | Description                      |
| --------- | -------------------------------- |
| `boolean` | True if the stack level is valid |

## Description

`debug.validlevel` checks whether a given stack level exists and is valid for debugging operations.

## Example

```lua
-- Check stack levels
for i = 0, 10 do
    if debug.validlevel(i) then
        print("Level " .. i .. " is valid")
    else
        print("Level " .. i .. " is invalid")
        break
    end
end
```

## Related Functions

* [`debug.getinfo`](getinfo.md) - Get function info
* [`debug.getcallstack`](getcallstack.md) - Get call stack
