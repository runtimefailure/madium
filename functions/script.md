---
description: >-
  Here you can see a description and use of the functions related to our
  Scripting library.
icon: scroll
---

# Script

#### Filter Garbage Collection

```
<table> filtergc(<any search, bool includeTables>)
```

* Searches the garbage collector for objects matching `search`.

> Alternative: `filter_gc`

***

#### Get Calling Script

```
<Instance> getcallingscript(<void>)
```

* Gets the script that is calling this function.

> Alternative: `get_calling_script`, `getscriptcaller`, `getcaller`

***

#### Get Garbage Collection

```
<table> getgc(<bool includeTables>)
```

* Returns all objects currently tracked by the garbage collector.

> Alternative: `get_gc_objects`

***

#### Get Function Hash

```
<string> getfunctionhash(<function fn>)
```

* Returns a hash from `fn`.

***

#### Get Global Environment

```
<table> getgenv(<void>)
```

* Returns the `environment` that will be applied to each script ran by Wave.

***

#### Get Loaded Modules

```
<table> getloadedmodules(<void>)
```

* Returns a `table` with all loaded `modules` currently in game.

> Alternative: `get_loaded_modules`

***

#### Get Modules

```
<table> getmodules(<Instance parent>)
```

* Returns all ModuleScripts that are children of `parent`.

> Alternative: `get_modules`

***

#### Get Roblox Environment

```
<table> getrenv(<void>)
```

* Returns the Roblox environment.

***

#### Get Roblox Environment Global

```
<any> getrenvglobal(<string name>)
```

* Returns the value of a global variable in the Roblox environment (`renv`).

***

#### Get Roblox Environment Shared

```
<any> getrenvshared(<string name>)
```

* Returns the value of a shared variable in the Roblox environment (`renv`).

***

#### Get Running Scripts

```
<table> getrunningscripts(<void>)
```

* Returns a list of scripts that are running in the environment. Returns `nil` if there are no scripts running.

***

#### Get Scripts

```
<table> getscripts(<void>)
```

* Returns a list of scripts within the global state of the caller.

> Alternative: `get_scripts`

***

#### Get Script Bytecode

```
<string> getscriptbytecode(<Instance> Script)
```

* Returns the bytecode of the given script. This can be used in a dissassembler.

> Alternative: `dumpstring`

***

#### Get Script Closure

```
<function> getscriptclosure(<Instance> Script)
```

* Returns the closure from the given script, can be used to gather `upvalues` or `constants`.

> Alternative: `getscriptfunction`, `get_script_function`

***

#### Get Script Environment

```
<table> getsenv(<LocalScript, ModuleScript> Script)
```

* Returns the global environment of the given script.

> Alternative: `getmenv`

***

#### Get Script Hash

```
<string> getscripthash(<Instance> Script)
```

* Returns a SHA384 hash of the scripts bytecode. You can use this to detect changes of a script.

***

#### Get Table Environment

```
<table> gettenv(<void>)
```

* Returns the environment table of the current script.

> Alternative: `getstateenv`

***

#### Get Thread Script

```
<Instance> getthreadscript(<thread thrd>)
```

* Returns the `LocalScript` or `ModuleScript` instance that the given thread originated from.

***

#### Is Local Source Container

```
<bool> islocalsourcecontainer(<Instance obj>)
```

* Checks if `obj` is a local source container (like a LocalScript).

***

#### Require

```
<any> require(<Instance ModuleScript>)
```

* Loads and returns the value of `ModuleScript`.

***

#### Set Closure Identity

```
<void> setclosureidentity(<function fn>, <int identity>)
```

* Sets the security identity of a function closure.

> Alternative: `setclosurecaps`
