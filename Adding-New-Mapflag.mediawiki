== Introduction ==

When scripting, or creating custom automated events, you may wish to add your own custom mapflags. In order to do so, you'll need to complete some source edits. This article will explain how.

----

This article was originally created by [http://www.eathena.ws/board/index.php?showuser=273955 TecnoCronus] on the eAthena forums.

== Adding your mapflag ==

=== Open /src/map/map.h ===
----
'''Find:'''
 unsigned src4instance : 1; // To flag this map when it's used as a src map for instances

'''Add below:'''
 unsigned mymapflag : 1;

=== Open /src/map/map.c ===
----
'''Find:'''
    } else if (!strcmpi(flag,"nocashshop")) {
        if( state && map->list[m].flag.nocashshop )
            ;/* nothing to do */
        else {
            if( state )
                map_zone_mf_cache_add(m,"nocashshop\toff");
            else if( map->list[m].flag.nocashshop )
                map_zone_mf_cache_add(m,"nocashshop");
        }
    }

'''Add below:'''
  else if( !strcmpi(flag,"mymapflag")) {
        if( state && map->list[m].flag.mymapflag )
            ; /* nothing to do */
        else {
            if( state )
                map_zone_mf_cache_add(m,"mymapflag\toff");
            else if( map->list[m].flag.mymapflag )
                map_zone_mf_cache_add(m,"mymapflag");
        }
    }

=== Open /src/map/script.h ===
----
'''Find:'''
 MF_NOCASHSHOP

'''Replace with:'''
 MF_NOCASHSHOP,
 MF_MYMAPFLAG

=== Open /src/map/script.c ===
----
'''Find:'''
 case MF_GUILDLOCK:        script_pushint(st,map->list[m].flag.guildlock); break;

'''Below add:'''
 case MF_MYMAPFLAG:        script_pushint(st,map->list[m].flag.mymapflag); break;

----

'''Find:'''
 case MF_GUILDLOCK:     map->list[m].flag.guildlock=1; break;

'''Below add:'''
 case MF_MYMAPFLAG:     map->list[m].flag.mymapflag=1; break;

----

'''Find:'''
 case MF_GUILDLOCK:     map->list[m].flag.guildlock=0; break;

'''Below add:'''
 case MF_MYMAPFLAG:     map->list[m].flag.mymapflag=0; break;

=== Open /src/map/npc.c ===
----
'''Find:'''
 else if (!strcmpi(w3,"guildlock"))
 	map->list[m].flag.guildlock=state;

'''Below add:'''
 else if (!strcmpi(w3,"mymapflag"))
 	map->list[m].flag.mymapflag=state;

=== Open /db/const.txt ===
----
'''Find:'''
 mf_guildlock<tab>45

'''Below add:'''
 mf_mymapflag<tab>46

== Listing your mapflag in atcommands ==

=== Open /src/map/atcommand.c ===
----
'''Find:'''
    if (map->list[m_id].flag.nomemo)
        strcat(atcmd_output, msg_txt(1064)); // NoMemo |

'''Below add:'''
    if (map->list[m_id].flag.mymapflag)
        strcat(atcmd_output, "mymapflag |");

'''Find:'''
 CHECKFLAG(nocashshop);

'''Below add:'''
 CHECKFLAG(mymapflag);

'''Find:'''
 SETFLAG(nocashshop);

'''Below add:'''
 SETFLAG(mymapflag);

'''Find:'''
 clif->message(sd->fd,"guildlock, src4instance, notomb, nocashshop");

'''Replace it with:'''
 clif->message(sd->fd,"guildlock, src4instance, notomb, nocashshop, mymapflag");

== Conclusion ==

Recompile and you can now set "mymapflag" to any value. Remember, you can rename the mapflag to whatever, and later use the flag option anywhere else in your source code.

[[Category:Source Snippets]]