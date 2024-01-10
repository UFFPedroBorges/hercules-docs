# `setmount()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setmount({<flag>});
```

## Description

If `flag` is `MOUNT_NONE` (or 0) this command will remove the mount from the
character.

Otherwise it gives the invoking character the desired combat mount, where
allowed by their class and skills.

If no `flag` is specified, the mount is automatically chosen according to the
character's class and skills.

The following flag values are accepted:

- `MOUNT_NONE`:
    - Dismount
- `MOUNT_PECO`:
    - PecoPeco (Knight series class)
    - GrandPeco (Crusader series class)
    - Gryphon (Royal Guard)
- `MOUNT_WUG`:
    - Warg (Ranger)
- `MOUNT_MADO`:
    - Mado Gear (Mechanic)
- `MOUNT_DRAGON`, `MOUNT_DRAGON_GREEN`, `MOUNT_DRAGON_BROWN`, `MOUNT_DRAGON_GRAY`, `MOUNT_DRAGON_BLUE`, `MOUNT_DRAGON_RED`:
    - Dragon (Rune Knight)

if `MOUNT_DRAGON` is specified, a the default (green) dragon will be used.

Unlike [`setfalcon()`](setfalcon.md) and [`setcart()`](setcart.md) this will not work at all if they aren't of a
class which can ride a mount.

## Example

```c
if (checkmount())
	mes("Leave your mount outside! No riding mounts on the floor here!");
```

```c
if (checkmount() == MOUNT_DRAGON)
    mes("Wow, your dragon is cool! Can I pet it?");
```
