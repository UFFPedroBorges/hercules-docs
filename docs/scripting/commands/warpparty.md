# `warpparty()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
warpparty("<to_mapname>", <x>, <y>, <party_id>, {"<from_mapname>"});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
Warps a party to specified map and coordinate given the party ID, which you can get with [[getcharid]](1).<br/>
You can also request another party id, given a member's name with [[getcharid]](1,<player_name>).<br/>
<br/>
You can use the following "map names" for special warping behavior:<br/>

'''Random''':    ''All party members are randomly warped in their current map (as if they all used a fly wing).<br/>''
'''SavePointAll''':    ''All party members are warped to their respective save point.<br/>''
'''SavePoint''':    ''All party members are warped to the save point of the currently attached player (will fail if there's no playerattached).''<br/>
'''Leader''':    ''All party members are warped to the leader's position. The leader must be online and in the current map-server for this to work.''<br/>
<br/>
If you specify a from_mapname, warpparty will only affect those on that map

==Example==
<pre>
mes "[Party Warper]";
mes "Here you go!";
close2;
set @id,getcharid(1);
warpparty "prontera",150,100,@id;
close;
</pre>
