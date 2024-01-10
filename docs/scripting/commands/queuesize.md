# `queuesize()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
queuesize(<Queue ID>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
queuesize returns the amount of entries in specific QueueID
== Example ==
  .@id = [[queue]]();
  mes queuesize(.@id);    //Returns 0
  [[queueadd]](.@id,[[getcharid]](3));
  mes queuesize(.@id);    //Returns 1
