---
description: >-
  Here you can see a description and use of the functions related to our Console
  library.
icon: rectangle-terminal
---

# Console

#### Clear

```lua
<void> rconsoleclear(<void>)
```

* Clears all text from the console.

***

#### Close

```lua
<void> rconsoleclose(<void>)
```

* Closes the console.

> Alternative: `rconsoledestroy`

***

#### Create

```lua
<void> rconsolecreate(<void>)
```

* Creates a new console window for logging and interaction.

***

#### Debug

```lua
<void> rconsoledebug(<string text>)
```

* Prints a debug message to the console in a distinct debug color/style.

***

#### Error

```lua
<void> rconsoleerr(<string> text)
```

* Prints `text` into the console, with `[ERROR]` written before it.

***

#### Info

```lua
<void> rconsoleinfo(<string> text>)
```

* Prints `text` into the console, with `[INFO]` written before it.

***

#### Input

```lua
<string> rconsoleinput(<void>)
```

* Yields the current thread until the user inputs text and presses `Enter`. Returns the input they put in.

***

#### Name

```lua
<void> rconsolename(<string> title)
```

* Sets the console's title to `title`.

> Alternative: `rconsolesettitle`

***

#### Print

```lua
<void> rconsoleprint(<string> text)
```

* Prints `text` into the console.

***

#### Print Console

```lua
<void> printconsole(<string> message, <byte> red, <byte> green, <byte> blue)
```

* Prints `message` into the internal and integrated console with RGB value.

***

#### Console Colors

| Name          | Type               |
| ------------- | ------------------ |
| Black         | @@BLACK@@          |
| Blue          | @@BLUE@@           |
| Green         | @@GREEN@@          |
| Cyan          | @@CYAN@@           |
| Red           | @@RED@@            |
| Magenta       | @@MAGENTA@@        |
| Light Gray    | @@LIGHT\_GRAY@@    |
| Dark Gray     | @@DARK\_GRAY@@     |
| Light Blue    | @@LIGHT\_BLUE@@    |
| Light Green   | @@LIGHT\_GREEN@@   |
| Light Cyan    | @@LIGHT\_CYAN@@    |
| Light Red     | @@LIGHT\_RED@@     |
| Light Magenta | @@LIGHT\_MAGENTA@@ |
| Yellow        | @@YELLOW@@         |
| White         | @@WHITE@@          |

**Example:**

```lua
rconsolename("console") -- Sets the name of the console to 'console'
rconsoleprint("gamer\n")
rconsoleprint("@@YELLOW@@") -- Changes the text color to Yellow
rconsoleprint("gamer but yellow\n")
rconsoleerr("omg error!")
rconsolewarn("omg warning!")
wait(3)
rconsoleclear() -- Clears all text
wait(1)
rconsoleclose() -- Closes the console
```

You must use `\n` at the end of `rconsoleprint` to make a new line.

`rconsoleinfo`, `rconsolewarn`, and `rconsoleerr` do this automatically.
