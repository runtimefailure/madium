---
description: >-
  The Actors library provides functions for working with Roblox's parallel Luau
  actors and Lua state management.
icon: user
---

# Actors



## Overview

These functions allow you to:

* Get and manage actors in the game
* Run code on specific actor threads
* Create communication channels between actors
* Check parallel execution state
* Access and control Lua execution states
* Monitor actor state creation

## Available Functions

| Function                                              | Description                             |
| ----------------------------------------------------- | --------------------------------------- |
| [`create_comm_channel`](create_comm_channel.md)       | Create a communication channel          |
| [`get_comm_channel`](get_comm_channel.md)             | Get an existing communication channel   |
| [`getactors`](getactors.md)                           | Get all actors in the game              |
| [`getactorstates`](getactorstates.md)                 | Get all active LuaStateProxy objects    |
| [`getluastate`](getluastate.md)                       | Get LuaStateProxy for actor or script   |
| [`getgamestate`](getgamestate.md)                     | Get the default game Lua state          |
| [`isparallel`](isparallel.md)                         | Check if running in parallel            |
| [`on_actor_added`](on_actor_added.md)                 | Event fired when actor is ready         |
| [`on_actor_state_created`](on_actor_state_created.md) | Event fired when actor state is created |
| [`run_on_actor`](run_on_actor.md)                     | Execute code on an actor                |

## What are Actors?

Actors are Roblox's way of enabling parallel Luau execution. They allow scripts to run concurrently on multiple threads, improving performance for computationally intensive tasks.

## Communication Channels

Communication channels allow actors to send messages to each other. Use `create_comm_channel` to create a channel and `get_comm_channel` to retrieve it from another actor.
