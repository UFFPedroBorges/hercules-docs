# `detachnpctimer()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
detachnpctimer({"<NPC name>"});
```

## Description

Use to remove the RID attached to an NPC used by [`attachnpctimer()`](attachnpctimer.md). You can only use this when the NPC Timer is not running, use [`stopnpctimer()`](stopnpctimer.md) to stop the NPC Timer.

## Examples

```c
<NPC Header> {
	// We need to use attachnpctimer because the mes command below needs RID attach
	attachnpctimer();
	initnpctimer();
	npctalk("I cant talk right now, give me 10 seconds");
	end;
OnTimer5000:
	npctalk("Ok 5 seconds more");
	end;
OnTimer6000:
	npctalk("4");
	end;
OnTimer7000:
	npctalk("3");
	end;
OnTimer8000:
	npctalk("2");
	end;
OnTimer9000:
	npctalk("1");
	end;
OnTimer10000:
	stopnpctimer();
	mes("[Man]");
	mes("Ok we can talk now");
	detachnpctimer();
	// and remember attachnpctimer and detachnpctimer can only use while the NPC timer is not running !
}
```
