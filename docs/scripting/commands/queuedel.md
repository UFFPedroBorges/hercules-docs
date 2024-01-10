# `queuedel()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
queuedel(<queue_id>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
Deletes queue of <queue_id> id.
Script returns 1 if <queue_id> was not found, if <queue_id> was found and deleted, it returns 0.
== Example ==
  if (queuedel(.@queueid)){
    [[mes]] "Queue was not deleted";
  }
