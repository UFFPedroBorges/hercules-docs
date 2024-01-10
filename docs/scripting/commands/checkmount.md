# `checkmount()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
checkmount();
```

## Description

This function will return 0 if the invoking character is not on a
mount, and a non-zero value (according to the above constants) if they are.

Note: in case of dragons, the returned value will always be `MOUNT_DRAGON`,
regardless of color.

## Example

```c
if (checkmount())
	mes("Leave your mount outside! No riding mounts on the floor here!");

if (checkmount() == MOUNT_DRAGON)
	mes("Wow, your dragon is cool! Can I pet it?");
```
