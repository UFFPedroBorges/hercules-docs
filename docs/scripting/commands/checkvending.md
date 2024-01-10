# `checkvending()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
checkvending({"<player name>"});
```

## Description

Checks if the player is vending or in a chatroom.

Name is optional, and defaults to the attached player if omitted.

| Value | Description |
| ----- | ----------- |
| 0 | The player is not chatting/vending. |
| 1 | The player is chatting/vending. |
| 2 | The player is vending using @autotrade. |

## Examples

```c
// This will check if Aaron is vending, and if so, put a message in front
// of the attached player saying Aaron is vending.
if (checkvending("Aaron"))
	mes("Aaron is currently vending!");
```
