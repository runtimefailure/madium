---
description: Checks if the current thread is running in parallel.
icon: code-simple
---

# isparallel



## Syntax

```lua
isparallel() -> boolean
```

## Aliases

* `is_parallel`

## Returns

| Type      | Description                           |
| --------- | ------------------------------------- |
| `boolean` | True if running in a parallel context |

## Description

`isparallel` returns whether the current code is executing in a parallel Luau context (inside an Actor).

## Example

```lua
if isparallel() then
    print("Running in parallel!")
    -- Safe to do parallel-safe operations
else
    print("Running on main thread")
end
```

## Use in Actor

```lua
run_on_actor(someActor, [[\
    print("Is parallel:", isparallel()) -- true\
]])

print("Is parallel:", isparallel()) -- false (main thread)
```

## Notes

* Returns `false` on the main game thread
* Returns `true` when running inside an actor via `run_on_actor`

## Related Functions

* [`run_on_actor`](run_on_actor.md) - Run code on an actor
* [`getactors`](getactors.md) - Get all actors
