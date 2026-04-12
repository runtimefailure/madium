---
description: >-
  The Crypt library provides cryptographic functions for encryption, hashing,
  and random number generation.
icon: code-branch
---

# Crypt



## Overview

These functions allow you to:

* Encrypt and decrypt data
* Generate cryptographic hashes
* Create secure random values
* Perform HMAC authentication

## Available Functions

| Function                                  | Description                       |
| ----------------------------------------- | --------------------------------- |
| [`crypt.encrypt`](encrypt.md)             | Encrypt data with a key           |
| [`crypt.decrypt`](decrypt.md)             | Decrypt data with a key           |
| [`crypt.hash`](hash.md)                   | Generate a hash of data           |
| [`crypt.hmac`](hmac.md)                   | Generate HMAC authentication code |
| [`crypt.random`](random.md)               | Generate random bytes             |
| [`crypt.generatekey`](generatekey.md)     | Generate a random encryption key  |
| [`crypt.generatebytes`](generatebytes.md) | Generate random bytes             |

## Note

Base64 encoding functions (`crypt.base64encode`, `crypt.base64decode`) and LZ4 compression functions (`crypt.lz4compress`, `crypt.lz4decompress`) are documented in the [Encoding](https://docs.volt.bz/docs/encoding) section.
