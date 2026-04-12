---
description: >-
  Here you can see a description and use of the functions related to our
  Reflection library.
icon: square-dashed-circle-plus
---

# Reflection

### Check Caller

```lua
<bool> checkcaller(<void>)
```

* Returns `true` if the current thread was created by Wave.

***

### Get Hidden Property

```lua
<variant> gethiddenproperty(<Instance> Object, <string> Property)
```

* Returns the `value` of the property that cannot be accessed through Lua.

***

### Is Executor Closure

```lua
<bool> isexecutorclosure(<function> a1)
```

* Returns `true` if `a1` was created by Wave.

> Alternative: `isourclosure`, `is_our_closure`, `is_executor_closure`, `checkclosure`

***

### Is C Closure

```lua
<bool> iscclosure(<function fn>)
```

* Returns true if `fn` is a C closure (a function implemented in C, not Lua).

> Alternative: `is_c_closure`

***

### Is Line Info

```lua
<bool> islineinfo(<function fn>)
```

* Checks if `fn` contains Lua line information (debug metadata such as source file and line numbers).

***

### Is Lua Closure

```lua
<bool> islclosure(<function> a1)
```

* Returns `true` if `a1` is an L closure.

> Alternative: `is_l_closure`

***

### Loadstring

```lua
<function> loadstring(<string> chunk, <string?> chunkName)
```

* Loads `chunk` as a Lua function with optional `chunkName` and returns it.

***

### Set Hidden Property

```lua
<void> sethiddenproperty(<Instance> Object, <string> Property, <variant> Value)
```

* Sets the given property to new `value`.

***

### Set Scriptable

```lua
<void> setscriptable(<Instance> Object, <string> Property, <bool> toggle)
```

* Sets the property's scriptable state to `toggle`.
