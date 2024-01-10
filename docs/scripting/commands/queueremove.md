# `queueremove()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
queueremove(<queue_id>, <account_id>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
Removes <account_id> from queue of <queue_id>, returns 1 if <account_id> is not
present in the queue, otherwise returns 0.
== Example ==
  if ('''queueremove'''(.@id,[[getcharid]](3))==1){;
    [[mes]] "You were not in the queue";
    [[close]];
  }
  //Rest Script code Below
  ......
