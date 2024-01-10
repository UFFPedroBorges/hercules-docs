# `deletearray()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
deletearray(<array>, <amount of elements to delete>);
```

## Description

This command deletes a range of values within given array and shifts remaining values to fill the deletion gap.

!!! bug
	Currently (r14395) the command uses [`getarraysize()`](getarraysize.md) internally, which leads to unpredictable results with arrays, that contain empty elements. It is recommended to use a combination of [`copyarray()`](copyarray.md) and [`cleararray()`](cleararray.md) instead.

## Examples

```c
deletearray(@array, 10);
```

!!! info
	Deletes the first 10 elements of the array and shifts all other values by one to the left.

```c
copyarray(@array[0], @array[10], 90);
cleararray(@array[90], 0, 10);
```

!!! info
	Assuming `@array` has 100 elements, this achieves the same effect as the example above, but works properly even if `@array` has empty element(s).
