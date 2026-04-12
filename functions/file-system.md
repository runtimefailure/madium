---
description: >-
  Here you can see a description and use of the functions related to our File
  System library.
icon: file
---

# File System

#### Append File

```lua
<void> appendfile(<string> path, <string> content)
```

Appends `content` to the file contents at `path`.

***

#### Delete File

```lua
<void> delfile(<string> path)
```

* Deletes the file located at `path`.

> Alternative: `deletefile`

***

#### Delete Folder

```lua
<void> delfolder(<string> path)
```

* Deletes the folder located at `path`.

> Alternative: `deletefolder`

***

#### Get Custom Asset

```lua
<string> getcustomasset(<string> path)
```

* Provides a content string suitable for use with GUI elements, sounds, meshes, and other assets to reference an item in the workspace folder.

***

#### Is File

```lua
<bool> isfile(<string> path)
```

* Returns `true` if `path` is a file.

***

#### Is Folder

```lua
<bool> isfolder(<string> path)
```

* Returns `true` if `path` is a folder.

***

#### List Files

```lua
<table> listfiles(<string> folder)
```

* Returns a table of all files in `folder`.

***

#### Load File

```lua
<function> loadfile(<string> path)
```

* Loads the contents of the file located at `path` as a Lua function and returns it.

***

#### Make Folder

```lua
<void> makefolder(<string> path)
```

* Creates a new folder at `path`.

***

#### Read File

```lua
<string> readfile(<string> path)
```

* Returns the contents of the file located at `path`.

***

#### Write Custom Asset

```lua
<string> writecustomasset(<string filename>, <string data>)
```

* Creates a custom asset file that can be loaded into Roblox, writing the given `data` into the specified `filename`.

***

#### Write File

```lua
<void> writefile(<string> path, <string> content)
```

* Writes `content` to the supplied `path`.
