# `getelemenofarray()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getelementofarray(<array variable>, <index>);
```

## Description

This command retrieves the value of the element of given array at given index. This is equivalent to using:

```c
array[index]
```

The reason for this is, that this short form is internally converted into a call to `getelementofarray()`, when the script is loaded.

## Examples

```c
setarray(@array[0], 1, 2, 3);
set(@varl, getelementofarray(@array, 2));  // retrieves 3
set(@vars, @array[2]);  // retrieves 3 as well

if (@varl != @vars) {
	mes("This will never be shown");
}
```
