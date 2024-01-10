# `sc_start2()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
sc_start2(<effect type>, <ticks>, <extra argument>, <percent chance>{, <target ID number>});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
These command bestow a status effect on the invoking character. This command is 
used a lot in the item scripts.

Effect type is a number of effect, [`db/constants.conf`](https://github.com/HerculesWS/Hercules/blob/stable/db/constants.conf) lists the common (mostly 
negative) status effect types as constants, starting with 'SC_'. You can also 
use this to give someone an effect of a player-cast spell.

Extra argument's meaning differs depending on the effect type, for most effects 
caused by a player skill the extra argument means the level of the skill that 
would have been used to create that effect, for others it might have no meaning 
whatsoever. You can actually bless someone with a 0 bless spell level this way, 
which is fun, but weird.

The target ID number, if given, will cause the status effect to appear on a 
specified character, instead of the one attached to the running script. This has 
not been properly tested.

'[[sc_start2]]' is perfectly equivalent, but unlike '[[sc_start]]', a status change 
effect will only occur with a specified percentage chance. 10000 given as the 
chance is equivalent to a 100% chance, 0 is a zero.

'[[sc_start4]]' is just like '[[sc_start]]', however it takes four parameters for the
status change instead of one. What these values are depends on the status
change in question. For example, elemental armor defense takes the following
four values:
- val1 is the first element, val2 is the resistance to the element val1.
- val3 is the second element, val4 is the resistance to said element.
eg: [[sc_start4]] SC_ARMOR_ELEMENT,60000,Ele_Fire,20,Ele_Water,-15;

'[[sc_end]]' will remove a specified status effect. If SC_All is used (-1), it will
do a complete removal of all statuses (although permanent ones will re-apply).

You can see the full list of status effects caused by skills in 
[`src/map/status.h`](https://github.com/HerculesWS/Hercules/blob/stable/src/map/status.h) - they are currently not fully documented, but most of that 
should be rather obvious.

==Examples==
<pre>
    // This would poison them for 10 minutes
    sc_start SC_POISON,600000,0;

    // This will bless someone as if with Bless 10:
    sc_start 10,240000,10;
</pre>
