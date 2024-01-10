# `min()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
min(<number>{,<number>...<number>});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
Returns the smallest (or biggest) from the set of given numbers.

== Example ==
<pre>	.@minimum = min(1, -6, -2, 8, 2); // .@minimum will be equal to -6
	.@maximum = max(0, 5, 10, 4); // .@maximum will be equal to 10
	.@level = min(BaseLevel, 70); // .@level will be the character's base level, capped to 70
</pre>
