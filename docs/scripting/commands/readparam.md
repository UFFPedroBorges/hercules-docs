# `readparam()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
readparam(<parameter number>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
This function will return the basic stats of an invoking character, 
referred to by the parameter number. Instead of a number, you can use a 
parameter name if it is defined in '[https://github.com/HerculesWS/Hercules/blob/master/db/const.txt db/const.txt]'.

Example parameters:

    StatusPoint, BaseLevel, SkillPoint, Class, Upper, Zeny, Sex, Weight, 
    MaxWeight, JobLevel, BaseExp, JobExp, NextBaseExp, NextJobExp, Hp, MaxHp, 
    Sp, MaxSp, BaseJob, Karma, Manner, bVit, bDex, bAgi, bStr, bInt, bLuk

All of these also behave as variables, but don't expect to be able to just 
'set' them - some will not work for various internal reasons.

==Example==
===Example 1:===

    // Returns how many status points you haven't spent yet.
    mes "Unused status points: "+readparam(9);

Using this particular information as a function call is not required. 
Typing this will return the same result:

	mes "Unused status points: "+StatusPoint;

===Example 2:===

You can also use this command to get stat values.

    if (readparam(bVit) > 77)
    	mes "Only people with over 77 Vit are reading this!";


==See Also==
* '[https://github.com/HerculesWS/Hercules/blob/master/db/const.txt db/const.txt]'
