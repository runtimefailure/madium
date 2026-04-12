---
description: Generates cryptographically secure random bytes.
icon: code-simple
---

# generatebytes



## Syntax

```
crypt.generatebytes(length: number) -> string
```

## Parameters

| Parameter | Type     | Description                 |
| --------- | -------- | --------------------------- |
| `length`  | `number` | Number of bytes to generate |

## Returns

| Type     | Description               |
| -------- | ------------------------- |
| `string` | Random bytes (raw string) |

## Description

`crypt.generatebytes` generates cryptographically secure random bytes, useful for creating initialization vectors, salts, or other random data.

## Example

```lua
-- Generate 16 bytes for an IV
local iv = crypt.generatebytes(16)

-- Generate 32 bytes for a salt
local salt = crypt.generatebytes(32)
```

## Related Functions

* [`crypt.random`](random.md) - Same functionality
* [`crypt.generatekey`](generatekey.md) - Generate encryption key
