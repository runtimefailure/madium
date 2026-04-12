---
description: >-
  Here you can see a description and use of the functions related to our
  Environment library.
icon: earth-americas
---

# Environment

#### Add Spy Callback

```lua
<void> addspycallback(<function callback>)
```

* Registers a `callback` that will be executed whenever a RemoteEvent or function is invoked, allowing you to inspect or log the call.

***

#### Create Secure Folder

```lua
<void> createsecurefolder(<string> path)
```

* Creates a new secure folder to `path`.

> Note: The folder itself won't be able to be found by the game. This means you don't need to set the security of the instances within it.
>
> Alternative: `create_secure_folder`

***

#### Fire Click Detector

```lua
<void> fireclickdetector(<ClickDetector> ClickDetector, <number?> Distance = 0, <string?>)
```

* Fires the `ClickDetector`. If no distance supplied, it will default to `0`.

***

#### Fire Proximity Prompt

```lua
<void> fireproximityprompt(<ProximityPrompt> Prompt)
```

* Fires the `ProximityPrompt` trigger.

***

#### Fire Touch Interest

```lua
<void> firetouchinterest(<BasePart> totouch, <BasePart> Part, <uint?> toggle)
```

* Touches part with `totouch`.

**Actions**

| Action            | Toggle |
| ----------------- | ------ |
| Begins the touch. | 0      |
| Ends the touch.   | 1      |

***

#### Get Instances

```lua
<table> getinstances(<void>)
```

* Returns a `table` with instances.

> Alternative: `get_instances`

***

#### Get Nil Instances

```lua
<table> getnilinstances(<void>)
```

* Returns a `table` with instances parented to `nil`.

> Alternative: `get_nil_instances`

***

#### Is Secured Instance

```lua
<void> issecuredinstance(<Instance> Instance)
```

* Returns `true`/`false` if `Instance` is secured/not secured.

> Alternative: `is_secured_instance`

***

#### Protect Instance

```lua
<void> protectinstance(<Instance obj>)
```

* Marks `obj` as protected, preventing it from being tampered with or detected by certain internal checks.

***

#### Set Normal Instance

```lua
<table> setnormalinstance(<Instance> Instance)
```

* Sets `Instance` back to its normal state. Returns `false` if `Instance` is back to normal.

> Alternative: `set_normal_instance`

***

#### Set Simulation Radius

```lua
<void> setsimulationradius(<number radius>)
```

* Sets the simulation `radius` for the local player, controlling how far physics and character updates are processed around the player.

***

#### Set Secure Instance

```lua
<table> setsecureinstance(<Instance> Instance)
```

* Secures `Instance`. Returns `false` if `Instance` is secured.

> Alternative: `set_secure_instance`
