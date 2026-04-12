---
description: Generates a random encryption key.
icon: code-simple
---

# generatekey



## Syntax

```lua
crypt.generatekey() -> string
```

## Returns

| Type     | Description                 |
| -------- | --------------------------- |
| `string` | A Base64-encoded random key |

## Description

`crypt.generatekey` generates a cryptographically secure random key suitable for use with encryption functions.

## Example

```lua
-- Generate a key
local key = crypt.generatekey()
print("Generated key:", key)

-- Use the key for encryption
local data = "Secret message"
local encrypted = crypt.encrypt(data, key)
local decrypted = crypt.decrypt(encrypted, key)

print("Original:", data)
print("Decrypted:", decrypted)
```

## Notes

* The key is suitable for AES encryption
* Keys should be stored securely and not shared

## Related Functions

* [`crypt.encrypt`](encrypt.md) - Encrypt data
* [`crypt.decrypt`](decrypt.md) - Decrypt data
* [`crypt.generatebytes`](generatebytes.md) - Generate raw bytes
