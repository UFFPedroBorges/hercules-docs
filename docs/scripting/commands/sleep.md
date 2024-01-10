# `sleep()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
sleep(<milliseconds>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
These commands are used to control the pause of a NPC.
Commands [[sleep]] and [[sleep2]] will pause the script for the given amount of milliseconds.
Awake is used to cancel a sleep. When awake is called on a NPC it will run as
if the sleep timer ran out, and thus making the script continue. Sleep and sleep2
basically do the same, but the main difference is that sleep will not keep the [[RID]],
while sleep2 does.

==Examples==
<pre>
sleep 10000; //pause the script for 10 seconds and ditch the RID (so no player is attached anymore)
sleep2 5000; //pause the script for 5 seconds, and continue with the RID attached.
awake "NPC"; //Cancels any running sleep timers on the NPC 'NPC'.
</pre>
