---
description: >-
  Here you can see a description and use of the functions related to our Signals
  library.
icon: satellite-dish
---

# Signal

#### Can Signal Replicate

```lua
<bool> cansignalreplicate(<RBXScriptSignal signal>)
```

* Checks if `RBXScriptSignal` is capable of being replicated (i.e., fired to the server or across the client-server boundary).

***

#### Disable Connection

```lua
<void> disableconnection(<RBXScriptConnection> Connection)
```

* Disables `Connection`.

***

#### Enable Connection

```lua
<void> enableconnection(<RBXScriptConnection> Connection)
```

* Enables `Connection`.

***

#### Fire Signal

```lua
<void> firesignal(<RBXScriptSignal> Signal, <variant?> Args...)
```

* Fires all signals connected to the `signal`. If given, the arguments will be used to call the function.

***

#### Get All Replicate Signals

```lua
<table> getallreplicatesignals(<void>)
```

* Returns a table containing all `RBXScriptSignal` objects in the game that are capable of replication.

***

#### Get Connections

```lua
<table> getconnections(<RBXScriptSignal> Signal)
```

* Returns a `table` with all connections to the given `signal`.

**Connections**

| Connection  | Description                               |
| ----------- | ----------------------------------------- |
| `.Function` | The function connected to the connection. |
| `:Enable`   | Enables the connection.                   |
| `:Disable`  | Disables the connection.                  |
| `:Fire`     | Fires the connection.                     |

***

#### Get Signal Arguments

```lua
<table> getsignalarguments(<RBXScriptConnection conn>)
```

* Retrieves the arguments passed to a specific `RBXScriptConnection` when it was last fired.

***

#### Hook Signal

```lua
<void> hooksignal(<RBXScriptSignal> Signal, <function> callback)
```

* Intercepts signal invocations. When the `Signal` is fired, the `callback` is called for each Lua connection with an info table and arguments. Returning `true`from the callback triggers the original connection.

> Note: `hooksignal` cannot intercept C connections or CoreScript Lua connections.

***

#### Is Connection Enabled

```lua
<bool> isconnectionenabled(<RBXScriptConnection> Connection)
```

* Returns `true` if a connection is enabled.

***

#### Is Signal Hooked

```lua
<void> issignalhooked(<RBXScriptSignal> Signal)
```

* Returns `true` if `Signal` is hooked.

***

#### Replicate Signal

```lua
<void> replicatesignal(<RBXScriptSignal signal>, <var ...args>)
```

* Fires a `RBXScriptSignal` locally, simulating its activation with the provided arguments.

***

#### Unhook Signal

```lua
<void> unhooksignal(<RBXScriptSignal> Signal)
```

* Unhooks a signal hooked with `hooksignal`.
