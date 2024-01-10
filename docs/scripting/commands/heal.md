# `heal()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
heal(<hp>, <sp>);
```

## Description

This command will heal a set amount of HP and/or SP on the invoking character.

## Examples

```c
heal(30000, 0); // This will heal 30,000 HP
heal(0, 30000); // This will heal 30,000 SP
heal(300, 300); // This will heal 300 HP and 300 SP
```
