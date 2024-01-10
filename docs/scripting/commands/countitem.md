# `countitem()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
countitem(<itemid>);
countitem("Itemname");
```

## Description

`countitem()` will return the number of items of `itemid` the invoking player holds in his inventory.

Like in [`getitem()`](getitem.md), you can also write the name of the item ("Name"-column in ItemDB).

## Example

```c
mes("You have " + countitem(501) + "Apples!");
close();
```

!!! info
	Will print out the number of Apples the char holds...

```c
if (countitem("Apple") >= 5) {
	mes("This will only print if you have 5 or more Apples!");
	close();
}
```
