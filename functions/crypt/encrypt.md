---
description: Encrypts data using a specified algorithm and key.
icon: code-simple
---

# encrypt



## Syntax

```lua
crypt.encrypt(data: string, key: string, iv: string?, algorithm: string?) -> string
```

## Parameters

| Parameter   | Type     | Description                                 |
| ----------- | -------- | ------------------------------------------- |
| `data`      | `string` | The data to encrypt                         |
| `key`       | `string` | The encryption key                          |
| `iv`        | `string` | (Optional) Initialization vector            |
| `algorithm` | `string` | (Optional) Algorithm, defaults to "AES-CBC" |

## Returns

| Type     | Description        |
| -------- | ------------------ |
| `string` | The encrypted data |

## Description

`crypt.encrypt` encrypts the provided data using the specified algorithm and key. The result is typically Base64-encoded.

## Supported Algorithms

* `AES-CBC` (default)
* `AES-GCM`
* `AES-CTR`

## Example

```lua
local key = crypt.generatekey()
local data = "Secret message"

-- Encrypt with default algorithm
local encrypted = crypt.encrypt(data, key)
print("Encrypted:", encrypted)

-- Decrypt to verify
local decrypted = crypt.decrypt(encrypted, key)
print("Decrypted:", decrypted)
```

## With Custom IV

```lua
local key = crypt.generatekey()
local iv = crypt.generatebytes(16)
local data = "Secret message"

local encrypted = crypt.encrypt(data, key, iv, "AES-CBC")
local decrypted = crypt.decrypt(encrypted, key, iv, "AES-CBC")
```

## Related Functions

* [`crypt.decrypt`](decrypt.md) - Decrypt data
* [`crypt.generatekey`](generatekey.md) - Generate a key
