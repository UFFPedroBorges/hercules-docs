# `queueopt()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
queueopt(<queue_id>, <optionType>, {Optional <option val>});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
Modifies <queue_id>'s <optionType>. When <option val> is not present(i.e 0),
<optionType> is removed from <queue_id>. When <optionType> present it modifies
<queue_id>'s <optionType> with the new <option val> value.

Currently 3 options are available:
HQO_OnDeath (1), HQO_OnLogout (2), HQO_OnMapChange (3)

Note: The constant names are not final and may change.

== Example ==
  queueopt(.@queue_id,0,"MyNPC::MyOnQueueMemberDeathEventName");
[[Category:Incomplete]]
