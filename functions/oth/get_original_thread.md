---
description: >-
  Returns the original thread associated with the hook, or nil if not in a hook
  thread.
icon: code-simple
---

# get\_original\_thread



## Syntax

```lua
get_original_thread() -> thread?
```

## Returns

| Type      | Description                                         |
| --------- | --------------------------------------------------- |
| `thread?` | The original thread, or nil if not in a hook thread |

## Description

`get_original_thread` returns the original thread that called the hooked function. This is useful for accessing thread-local data or resuming execution on the original thread.

## Example

```lua
local originalPrint = oth.hook(print, function(...)
    local originalThread = get_original_thread()
    if originalThread then
        print("Original thread:", originalThread)
        print("Arguments:", ...)
    end
    return originalPrint(...)
end)

print("Test")
```

## Thread Context

```lua
local originalFunc = oth.hook(someCFunction, function(...)
    local originalThread = get_original_thread()

    if originalThread then
        -- We're in a hook thread
        print("Hook thread, original:", originalThread)
        -- Access thread-local data if needed
    else
        -- Not in a hook thread
        print("Not in hook thread")
    end

    return originalFunc(...)
end)
```

## Notes

* Returns `nil` if not currently executing in a hook thread
* The returned thread is the one that originally called the hooked function
* Useful for thread-local data access or debugging

## Related Functions

* [`oth.hook`](hook.md) - Create a hook
* [`oth.is_hook_thread`](is_hook_thread.md) - Check if in a hook thread
