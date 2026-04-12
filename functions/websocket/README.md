---
description: >-
  The WebSocket library provides functions for creating WebSocket connections
  for real-time bidirectional communication.
icon: network-wired
---

# Websocket



## Overview

WebSockets allow you to:

* Establish persistent connections to servers
* Send and receive messages in real-time

## Constructor

| Function                          | Description                       |
| --------------------------------- | --------------------------------- |
| [`WebSocket.connect`](connect.md) | Create a new WebSocket connection |

## Properties

| Property                    | Type     | Description                      |
| --------------------------- | -------- | -------------------------------- |
| [`OnMessage`](onmessage.md) | `Signal` | Fired when a message is received |
| [`OnClose`](onclose.md)     | `Signal` | Fired when the connection closes |

## Methods

| Method                        | Description           |
| ----------------------------- | --------------------- |
| [`WebSocket:Send`](send.md)   | Send a string message |
| [`WebSocket:Close`](close.md) | Close the connection  |
