# `getmapguildusers()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getmapguildusers("<map name>");
```

## Description

Returns the amount of persons from the given guild that are on the given map.

## Example

```c
//Will set the @persons variable to the amount of persons from the guild
//which ID's = 10 and are at prontera.
set(@persons, getmapguildusers("prontera", 10));
```
