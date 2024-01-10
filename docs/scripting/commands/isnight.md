# `isnight()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
isnight();
```

## Description

These functions determine whether server day or night cycle is currently in effect or not. If the server night is in effect, `isnight()` will return true, otherwise false.

## Examples

```c
if (!isnight()) {
	mes("I do not work at day, come again tomorrow.");
	close();
}
```

```c
if (isnight()) {
	mes("I do not work at night, come again tomorrow.");
	close();
}
```

!!! info
	These two script fragments achieve the same effect.
