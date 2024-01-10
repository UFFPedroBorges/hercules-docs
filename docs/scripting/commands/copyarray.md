# `copyarray()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
copyarray(<destination array>, <source array>, <amount of elements to copy>);
```

## Description

This command copies a range of values from given source array to given destination array. If you specify an index for either or both, the data will be copied string from or to the given index.

If copying would add more than 128 elements to the destination array, the remaining elements are cut off. If a combination of index and amount of elements to copy go beyond the 127th element, empty values, 0 or "" depending on array type, are assumed.

Note, that destination array and source array can point to the same variable, where the indexes differ.

Avoid use of script command [`getarraysize()`](getarraysize.md) for the third parameter, if the array in question contains empty values, otherwise `copyarray()` might not copy as many elements, as intended.

## Examples

```c
cleararray(@arrayl[0], 100, 6);  // { 100, 100, 100, 100, 100, 100 }
setarray(@arrays[0], 200, 300, 400, 500);
copyarray(@arrayl[2], @arrays, 4);
```

!!! info
	Copies the first 3 elements of `@arrays` to `@arrayl` starting at index 2, resulting in `@arrayl` being `{ 100, 100, 200, 300, 400, 100 }`.

```c
copyarray(@array[0], @array[1], 99);  // assuming @array has 100 elements
set(@array[99], 0);  // wipe last element
```

!!! info
	This shifts all elements inside ''@array'' by one towards index 0, effectively removing the first element.

```c
setarray(@array[0], 100, 200, 0, 300, 400, 500, 600);
copyarray(@array[0], @array[1], getarraysize(@array) - 1);  // hidden bug
```

!!! warning
	Will result in `@array` being `{ 200, 0, 300, 400, 500, 500, 600 }` rather than intended `{ 200, 0, 300, 400, 500, 600, 600 }`, because `getarraysize()` returns 6, instead of 7.
