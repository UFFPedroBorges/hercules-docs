# `itemheal()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
itemheal(<hp>, <sp>);
```

## Description

This command heals given absolute amounts of HP and/or SP on the invoking character. Unlike [`heal()`](heal.md), this command is intended for use in item scripts. It applies potion-related bonuses, such as alchemist ranking, cards and status changes. When used inside an NPC script, certain bonuses are omitted.

## Examples

```c
itemheal(rand(100, 150), 0);
```

!!! info
	This heals between 100 and 150 HP and no SP.

## See Also

- [`heal()`](heal.md)
- [`percentheal()`](percentheal.md)
