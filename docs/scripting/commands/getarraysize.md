# `getarraysize()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getarraysize(<array name>);
```

## Description

This function returns the number of values that are contained inside the specified array. Notice that zeros and empty strings at the end of this array are not counted towards this number.

## Examples

```c
setarray(@array[0], 100, 200, 300, 400, 500, 600);
set(@arraysize, getarraysize(@array));
```

!!! info
	This will make `@arraysize == 6`. But if you try this:

```c
setarray(@array[0], 100, 200, 300, 400, 500, 600, 0);
set(@arraysize, getarraysize(@array));
```

!!! remark
	`@arraysize` will still equal 6, even though you've set 7 values.
