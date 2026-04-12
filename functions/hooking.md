---
description: >-
  Here you can see a description and use of the functions related to our Hooking
  library.
icon: lasso
---

# Hooking

#### Clone Function

```txt
<function> clonefunction(<function> a1)
```

* Clones function `a1`.

> Alternative: `clonefunc`

***

#### Get Callback Value

```txt
<any> getcallbackvalue(<function fn>)
```

* Retrieves the current value or reference of `fn` that has been set or hooked.

***

#### Hook Function

```txt
<function> hookfunction(<function> old, <function> new)
```

* Hooks function `old`, replacing it with the function `new`. The `old` function is returned, you _must_ use this function in order to call the original function.

> Alternative: `replaceclosure`, `hookfunc`, `replacefunction`, `replacefunc`, `detourfunction`, `replaceclosure`, `detour_function`

***

#### Hook Metamethod

```txt
<function> hookmetamethod(<Object> object, <string> metamethod, <function> a1)
```

* Hooks the `metamethod` passed in `object`'s metatable with `a1`.

***

#### Is Hooked

```txt
<bool> ishooked(<function fn>)
```

* Checks if `fn` has been hooked (i.e., replaced or wrapped by a hook).

> Alternative: `isfunctionhooked`

***

#### Is Our Call Stack

```txt
<bool> isourcallstack(<int level>)
```

* Checks the entire callstack to see if it is from Wave or Roblox.

***

#### New C Closure

```txt
<function> newcclosure(<function> a1)
```

* Pushes a new C Closure that invokes the function `a1` upon call.

***

#### New Lua Closure

```txt
<function> newlclosure(<function fn>)
```

* Pushes a new L Closure that invokes the function `fn` upon call.

***

#### Protect Closure

```txt
<void> protectclosure(<function fn>)
```

* Prevents `fn` from being hooked or modified by external code.

> Alternative: `protectfunction`

***

#### Restore Closure

```txt
<void> restoreclosure(<function fn>)
```

* Restores `fn` back to its original, unmodified closure.

> Alternative: `restorefunction`, `restorefunc`
