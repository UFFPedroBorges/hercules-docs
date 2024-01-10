# `getmobdrops()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getmobdrops(<mob id>);
```

## Description

This command will find all drops of the specified mob and return the item IDs and drop percentages into arrays of temporary global variables.

`getmobdrops()` returns 1 if successful and 0 if the mob ID doesn't exist.

Upon executing this,

| Array | Description |
| ----- | ----------- |
| `$@MobDrop_item[]` | is a global temporary number array which contains the item IDs of the monster's drops. |
| `$@MobDrop_rate[]` | is a global temporary number array which contains the drop percentages of each item. (1 = .01%) |
| `$@MobDrop_count` | is the number of item drops found. |

Be sure to use `$@MobDrop_count` to go through the arrays, and not [`getarraysize()`](getarraysize.md), because the temporary global arrays are not cleared between runs of `getmobdrops()`. If a mob with 7 item drops is looked up, the arrays would have 7 elements. But if another mob is looked up and it only has 5 item drops, the server will not clear the arrays for you, overwriting the values instead. So in addition to returning the 5 item drops, the 6th and 7th elements from the last call remain, and you will get 5+2 item drops, of which the last 2 don't belong to the new mob.

`$@MobDrop_count` will always contain the correct number (5), unlike [getarraysize()`](getarraysize.md) which would return 7 in this case.

## Examples

```c
// get a Mob ID from the user
input(.@mob_id);

if (getmobdrops(.@mob_id)) {	// 'getmobdrops' returns 1 on success
	// immediately copy global temporary variables into scope 
	// variables, since we don't know when 'getmobdrops' will get 
	// called again for another mob, overwriting your global temporary 
	// variables.
	set(.@count, $@MobDrop_count);
	copyarray(.@item[0], $@MobDrop_item[0], .@count);
	copyarray(.@rate[0], $@MobDrop_rate[0], .@count);
	
	mes(getmonsterinfo(.@mob_id, MOB_NAME) + " - " + .@count + " drops found:");
	for (set(.@i, 0); .@i < .@count; set(.@i, .@i +1)) {
		mes(.@item[.@i]
			+ " (" + getitemname(.@item[.@i]) + ") " 
			+ .@rate[.@i] / 100 + ((.@rate[.@i] % 100 < 10) ? ".0" : ".") + .@rate[.@i] % 100 + "%"
		);
	}
} else {
	mes("Unknown monster ID.");
}
close();
```
