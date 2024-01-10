# `queueadd()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
queueadd(<queue_id>, <account_id>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
Adds <account_id> to queue of <queue_id>, returning 1 if <account_id> is already
present in the queue, if <account_id> was not present in queue, it returns 0.

== Example ==
  if('''queueadd'''(.@id,[[getcharid]](3)) == 1){
    [[mes]] "You are already in the queue.";
    [[close]];
  }
