# `getd()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getd("<variable name>");
```

## Description

Returns a reference to a variable, the name can be constructed dynamically.

Refer to [`setd()`](setd.md) for usage.

This can also be used to set an array dynamically:

```c
setarray(getd(".array[0]"), 1, 2, 3, 4, 5);
```

## Examples

```c
set(.@mob_id, 1002);
dispbottom(getd(".prize_" + .@mob_id)); // displays the value of .prize_1002
```
