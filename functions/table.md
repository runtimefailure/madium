---
description: >-
  Here you can see a description and use of the functions related to our Tables
  library.
icon: layer-plus
---

# Table

#### Get Raw Metatable

```lua
<table> getrawmetatable(<table> a1)
```

* Returns the `__metatable` of `a1`.

***

#### Is Read Only

```lua
<bool> isreadonly(<table> a1)
```

* Returns if `a1` is read-only.

***

#### Is Writable

```lua
<bool> iswritable(<table tbl>)
```

* Checks if `tbl` is writable, i.e., if its fields can be modified.

> Alternative: `iswriteable`

***

#### Make Read Only

```lua
<void> makereadonly(<table tbl>)
```

* Makes `tbl` read-only, preventing modifications to its fields.

> Alternative: `make_readonly`

***

#### Make Writable

```lua
<void> makewritable(<table tbl>)
```

* Makes `tbl` writable, allowing its fields to be modified.

> Alternative: `make_writable`, `make_writeable`, `makewriteable`

***

#### Set Raw Metatable

```lua
<bool> setrawmetatable(<table> a1, <table> a2)
```

* Sets the `__metatable` of `a1` to `a2`.

***

#### Set Read Only

```lua
<void> setreadonly(<table> a1, <bool> a2)
```

* Sets the read-only value of `a1` to `a2`.
