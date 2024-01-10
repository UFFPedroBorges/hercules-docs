# `bindatcmd()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
bindatcmd("command", "<NPC object name>::<event label>"{, <atcommand level>, <charcommand level>});
```

## Description

This command will bind a NPC event label to an [atcommand](../../atcommand.md). Upon execution of the atcommand, the user will invoke the NPC event label. Each atcommand is only allowed one binding. If you rebind, it will override the original binding.

The following variables are created upon execution:
- `.@atcmd_command$`: The atcmd used.
- `.@atcmd_numparameters`: The number of parameters defined.
- `.@atcmd_parameters$[]`: Array containing the given parameters, starting from an index of 0.

## Example

```c

-	script	atcmd_example	-1,{
OnInit:
	bindatcmd("test", strnpcinfo(3) + "::OnAtcommand");
	end;

OnAtcommand:
	specialeffect2(338);
	end;
}
```

!!! info
	When a user types the command `@test`, an angel effect will be shown.

For another good usage example of this command, see [`changelook()`](changelook.md).
