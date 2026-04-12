---
description: Gets all actors in the game.
icon: code-simple
---

# getactors



## Syntax

```lua
getactors() -> {Actor}
```

## Aliases

* `get_actors`

## Returns

| Type      | Description                     |
| --------- | ------------------------------- |
| `{Actor}` | Array of all actors in the game |

## Description

`getactors` returns all Actor instances currently in the game. This is useful for discovering available actors to run code on.

## Example

```lua
local actors = getactors()
print("Total actors:", #actors)

for i, actor in ipairs(actors) do
    print(i, actor:GetFullName())
end
```

## Related Functions

* [`run_on_actor`](run_on_actor.md) - Run code on an actor
* [`isparallel`](isparallel.md) - Check if running in parallel
