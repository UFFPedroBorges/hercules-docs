# `agitstart()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
agitstart();
```

## Description
These two commands will start and end the [War of Emperium](../../war-of-emperium.md).

This is a bit more complex than it sounds, since the commands themselves won't actually do anything interesting, except causing all [`OnAgitStart`](../events/OnAgitStart.md) and [`OnAgitEnd`](../events/OnAgitEnd.md) events to run everywhere. They are used as simple triggers to run a lot of complex scripts in [npc/guild](https://github.com/HerculesWS/Hercules/tree/stable/npc/guild), which are responsible for the actual starting and ending of the guild siege. `agitstart()` and [`agitend()`](agitend.md) are usually triggered by clock with an [`OnClock`](../events/OnClock.md)`<time>` labels.

## Example

```c
OnAgitInit:
	if (gettime(3) >= 19 && gettime(3) < 21) {
		agitstart();
	}
	end;

OnClock1900:
	agitstart();
	end;
OnClock2100:
	agitend();
	end;
```

!!! info
	A basic WoE controller script, which resumes the siege, even when the server is started during the WoE period.
