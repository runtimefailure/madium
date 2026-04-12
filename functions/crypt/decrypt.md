---
description: Decrypts data using a specified algorithm and key.
icon: code-simple
---

# decrypt



## Syntax

```
crypt.decrypt(data: string, key: string, iv: string?, algorithm: string?) -> string
```

## Parameters

| Parameter   | Type     | Description                                 |
| ----------- | -------- | ------------------------------------------- |
| `data`      | `string` | The encrypted data                          |
| `key`       | `string` | The decryption key                          |
| `iv`        | `string` | (Optional) Initialization vector            |
| `algorithm` | `string` | (Optional) Algorithm, defaults to "AES-CBC" |

## Returns

| Type     | Description        |
| -------- | ------------------ |
| `string` | The decrypted data |

## Description

`crypt.decrypt` decrypts data that was encrypted with `crypt.encrypt` using the same algorithm and key.

## Example

```lua
local key = crypt.generatekey()
local original = "Hello, World!"

-- Encrypt and decrypt
local encrypted = crypt.encrypt(original, key)
local decrypted = crypt.decrypt(encrypted, key)

print(decrypted) -- "Hello, World!"
```

## Related Functions

* [`crypt.encrypt`](encrypt.md) - Encrypt data
* [`crypt.generatekey`](generatekey.md) - Generate a key
