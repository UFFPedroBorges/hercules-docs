# `donpcevent()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
donpcevent("<NPC object name>::<event label>");
```

## Description

This command invokes the event label code within an another [NPC](../NPC.md) or NPCs. If `event label` has the form `"NpcName::OnLabel"`, then only given NPC's event label will be invoked (much like [`goto()`](goto.md) into another NPC). If the form is `"::OnLabel"` (`NpcName` ommited), the event code of all NPCs with given label will be invoked, one after another. In both cases the invoked script will run without an attached [RID](../RID.md), whether or not the invoking script was attached to a player. The event label name is required to start with `On`.

This command can be used to make other NPCs act, as if they were responding to the invoking NPC's actions, such as using an [`emotion()`](emotion.md) or [talking](npctalk.md).

## Examples

```c
prontera,150,150,3	script	NPC	53,{
    mes("Hey NPC2 copies what I do.");
    close2();
    set(.@emote, rand(1, 30);
    donpcevent("NPC2::OnEmote");
OnEmote:
    emotion(.@emote);
    end;
}

prontera,152,150,5	script	NPC2	53,{
    mes("Hey NPC copies what I do.");
    close2();
    set(.@emote, rand(1, 30));
    donpcevent("NPC::OnEmote");
OnEmote:
    emotion(.@emote);
    end;
}
```

!!! info
    Whichever of the both NPCs is talked to, both will show a random emotion at the same time.

Command returns 1 or 0 on success and failure. A debug message also shows on the console when no events are triggered.

## See Also

- [`doevent()`](doevent.md)
