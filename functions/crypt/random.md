---
description: Generates cryptographically secure random bytes.
icon: code-simple
---

# random



## Syntax

```
crypt.random(length: number) -> string
```

## Parameters

| Parameter | Type     | Description                        |
| --------- | -------- | ---------------------------------- |
| `length`  | `number` | Number of random bytes to generate |

## Returns

| Type     | Description        |
| -------- | ------------------ |
| `string` | Random byte string |

## Description

`crypt.random` generates cryptographically secure random bytes, suitable for security-sensitive operations.

## Example

```lua
-- Generate 16 random bytes
local randomBytes = crypt.random(16)
print("Random bytes length:", #randomBytes)

-- Convert to hex for display
local hex = ""
for i = 1, #randomBytes do
    hex = hex .. string.format("%02x", string.byte(randomBytes, i))
end
print("Hex:", hex)
```

## Use Cases

* Generating session tokens
* Creating random IVs for encryption
* Generating salts for password hashing

## Related Functions

* [`crypt.generatebytes`](generatebytes.md) - Alias for random bytes
* [`crypt.generatekey`](generatekey.md) - Generate encryption key
