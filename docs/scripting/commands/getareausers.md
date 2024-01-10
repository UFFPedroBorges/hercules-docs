# `getareausers()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getareausers("<map name>", <x1>, <y1>, <x2>, <y2>);
```

## Description

This function will return the count of connected characters which are located
within the specified area - an `x1`/`y1`-`x2`/`y2` square on the specified map.

This is useful for maps that are split into many buildings, such as all the
"*_in" maps, due to all the shops and houses.

## See Also

- [`getmapusers()`](getmapusers.md)
