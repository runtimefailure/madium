---
description: Here you can see a description and use of the other functions we provide.
icon: align-justify
---

# Miscellaneous

#### Clear Teleport Queue

```lua
<void> clearteleportqueue(<void>)
```

* Clears all queued teleport requests for the local player.

> Alternative: `clear_teleport_queue`

***

#### Decompile

```lua
<string> decompile(<Instance> Script)
```

* Decompiles `Script` and returns the decompiled output.

{% hint style="warning" %}
`decompile()`  function is using lua.expert as its decompiler and u might get rate-limited by it sometimes.
{% endhint %}

**Example:**

```lua
local LocalPlayer = game:GetService("Players").LocalPlayer
local PlayerModule = LocalPlayer.PlayerScripts.PlayerModule
local Decompiled = decompile(PlayerModule) -- Decompiles PlayerModule
setclipboard(Decompiled) -- Copies the decompiled output to your clipboard
```

***

#### Get Clipboard

```lua
<void> getclipboard(<void>)
```

* Gets the content from your clipboard.

> Alternative: `fromclipboard`

***

#### Get Fast Flag

```lua
<bool> getfflag(<string flagName>)
```

* Returns the value of `flagName`.

***

#### Get FPS Cap

```lua
<void> getfpscap(<void>)
```

* Gets your FPS in-game.

***

#### Get Hidden UI

```lua
<Instance> gethui(<void>)
```

* Returns the `CoreGui` service, allowing GUI's being hidden from detection in-game.

***

#### Get HWID

```lua
<string> gethwid(<void>)
```

* Gets the hardware ID (HWID) of the local system.

> Alternative: `get_hwid`

***

#### Get Namecall Method

```lua
<string> getnamecallmethod(<void>)
```

* Returns the namecall method if the function is called in an `__namecall` metatable hook.

***

#### Get Objects

```lua
<table> getobjects(<string assetIdOrUri>)
```

* Loads instances from `assetIdOrUri`.

***

#### Get Thread Identity

```lua
<void> getthreadidentity(<value> number)
```

* Returns the current thread's identification number.

> Alternative: `getidentity`, `getcontext`, `getthreadcontext`, `get_thread_context`, `get_thread_identity`

***

#### Http Get

```lua
<string> httpget(<string url>)
```

* Sends an HTTP GET request to `url` and returns the response body as a string.

***

#### Identify Executor

```lua
<string, string> identifyexecutor(<void>)
```

* Returns `Wave` and the version if the current executor is Wave.

> Alternative: `getexecutorname`

***

#### Is Scriptable

```lua
<bool> isscriptable(<Instance> object)
```

* Checks if `object` can be scripted or modified by a script.

***

{% hint style="warning" %}
`saveinstance()`  function is not safe, and it could get you potentially banned from one of your games.
{% endhint %}

#### Save Instance

```lua
<void> saveinstance(<Instance?> Object, <string?> FilePath, <table?> Options)
```

* Saves the current game into your workspace folder as a `.RBXL` file.

> If `Object` is specified, it will save that object and its descendants as a `.RBXM` file.

> If `Object` is `game`, it will be saved as a `.RBXL` file.

> If `FilePath` is specified, it will write the file to the specified path.

> `FilePath` does not need to contain a file extension, only the name of the file.

**Options:**

| Name                   | Type    | Default                               | Description                                                                                                                      |
| ---------------------- | ------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Decompile              | Boolean | false                                 | If enabled, `LocalScripts` and `ModuleScripts` will be decompiled.                                                               |
| DecompileTimeout       | Number  | 10                                    | If the decompilation run time exceeds this value, it will be canceled. This value is in seconds.                                 |
| DecompileIgnore        | Table   | `{"Chat", "CoreGui", "CorePackages"}` | Scripts that are a descendant of the specified services will be saved but not decompiled.                                        |
| NilInstances           | Boolean | false                                 | If enabled, instances parented to `nil` will be saved.                                                                           |
| RemovePlayerCharacters | Boolean | true                                  | If enabled, player characters will not be saved.                                                                                 |
| SavePlayers            | Boolean | false                                 | If enabled, Player objects and their descendants will be saved.                                                                  |
| MaxThreads             | Number  | 3                                     | The number of decompilation threads that can run at once. More threads allow for more scripts to be decompiled at the same time. |
| ShowStatus             | Boolean | true                                  | If enabled, Save Instance progress will be displayed.                                                                            |
| IgnoreDefaultProps     | Boolean | true                                  | If enabled, default properties will not be saved.                                                                                |
| IsolateStarterPlayer   | Boolean | true                                  | If enabled, `StarterPlayer` will be cleared and the saved starter player will be placed into folders.                            |

**Example - Saving the game to a custom folder:**

```lua
makefolder("MySaves")
saveinstance(game, "MySaves/Cool Game")
```

**Example - Saving a specific object with decompiled scripts:**

```lua
saveinstance(workspace.CoolModel, "Cool Model", {
    Decompile = true
})
```

***

#### Set Clipboard

```lua
<void> setclipboard(<string> content)
```

* Sets `content` to the clipboard.

> Alternative: `toclipboaard`

***

#### Set Fast Flag

```lua
<void> setfflag(<string> flag, <string> value)
```

* Sets `flag`'s value to `value`.

> You can find a list of all Fast Flags here: [FFlag Trackerarrow-up-right](https://raw.githubusercontent.com/MaximumADHD/Roblox-FFlag-Tracker/main/PCDesktopClient.json)

***

#### Set FPS Cap

```lua
<void> setfpscap(<uint> cap)
```

* Sets the fps cap to `cap`.

***

#### Set Namecall Method

```lua
<void> setnamecallmethod(<string> method)
```

* Sets the current namecall method to the new namecall method. Must be called in a `__namecall` metatable hook.

***

#### Set Roblox Clipboard

```lua
<void> setrbxclipboard(<string> content)
```

* Sets `content` to the clipboard inside of Roblox.

***

#### Set Thread Identity

```lua
<void> setthreadidentity(<value> number)
```

* Sets the current thread's identification `number`.

> Alternative: `setidentity`, `setcontext`, `setthreadcontext`, `set_thread_context`, `set_thread_identity`

***

#### Message Box

```lua
<uint> messagebox(<string> text, <string> title, <uint> flag)
```

* Creates a message box.

> Alternative: `messageboxasync`

**Flags:**

| Flag                          | Value |
| ----------------------------- | ----- |
| OK                            | 0     |
| OK / Cancel                   | 1     |
| Abort / Retry / Ignore        | 2     |
| Yes / No / Cancel             | 3     |
| Yes / No                      | 4     |
| Retry / Cancel                | 5     |
| Cancel / Try Again / Continue | 6     |

**Return Values:**

| Value | Description            |
| ----- | ---------------------- |
| 1     | OK was clicked.        |
| 2     | Cancel was clicked.    |
| 3     | Abort was clicked.     |
| 4     | Retry was clicked.     |
| 5     | Ignore was clicked     |
| 6     | Yes was clicked.       |
| 7     | No was clicked.        |
| 10    | Try Again was clicked. |
| 11    | Continue was clicked.  |

***

#### Queue On Teleport

```lua
<void> queue_on_teleport(<string> script)
```

* Queues `script` to be executed after the next teleport.

> Alternative `queueonteleport`

***

#### Request

```lua
<table> request(<table> a1, <bool?> Async)
```

* Creates an http request with `a1`.

> Alternative: `http_request`

***

#### ZSTD Compress

```lua
<string> zstdcompress(<string data>)
```

* Compresses `data` using the Zstandard (ZSTD) compression algorithm.

***

#### ZSTD Decompress

```lua
<string> zstddecompress(<string data>)
```

* Decompresses `data` that was compressed with the Zstandard (ZSTD) algorithm.
