---
description: Returns a hash of the function's bytecode.
icon: code-simple
---

# getfunctionhash



## Syntax

```lua
getfunctionhash(func: function) -> string
```

## Parameters

| Parameter | Type       | Description          |
| --------- | ---------- | -------------------- |
| `func`    | `function` | The function to hash |

## Returns

| Type     | Description                                        |
| -------- | -------------------------------------------------- |
| `string` | A hash string representing the function's bytecode |

## Description

`getfunctionhash` generates a unique hash based on the function's compiled bytecode. Functions with identical source code will produce the same hash, making this useful for identifying and comparing functions.

## Example

```lua
local function testFunc()
    return 1 + 1
end

local hash = getfunctionhash(testFunc)
print(hash) -- Output: something like "a1b2c3d4..."

-- Same code produces same hash
local function testFunc2()
    return 1 + 1
end

print(getfunctionhash(testFunc2) == hash) -- true
```

## Notes

* Only works with Luau closures (not C closures)
* Slight changes in function bytecode will alter the returned hash
