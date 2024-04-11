## Map Flags are used to set serval permissions on maps.

  
  
  

1.  Battleground
2.  GvG
3.  Nightenabled
4.  Nightmare
5.  Nobranch
6.  Noexp
7.  Noicewall
8.  Noloot
9.  Nomemo
10. Nopenalty
11. Nopvp
12. Noreturn
13. Nosave
14. Noskill
15. Noteleport
16. Novending
17. Nowarp
18. Nowarpto
19. Partylock
20. Pvp
21. Pvpnoguild
22. Pvpnoparty
23. Reset
24. Skillduration
25. Skillmodifier
26. Town
27. Zone

Battleground  
**Description:** Defines the Map as Battleground.  
**File:** npc/mapflag/battleground.txt  
**Parameter:** 2 ( Activate Scoreboard )  
`usage: `<map>` mapflag battleground <parameter(Optional)>`  
  
  
Gvg  
**Description:** Defines the Map as Guild Vs. Guild Map, so Guilds can Fight each other.  
**File:** npc/mapflag/gvg.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag gvg`  
  
  
Nightenabled  
**Description:** Nightmode Effects on defined Maps.  
**File:** npc/mapflag/night.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag nightenabled`  
  
  

Nightmare  
**Description:** Drops Player Items or Equipments on player death.  
**File:** npc/mapflag/nightmare.txt  
**ID:** ItemID,random  
**Type:** inventory, equip, all  
**Percent:** Droprate  
`usage: `<map>` mapflag pvpnightmaredrop `<id>`,`<type>`,`<percent>  
  
  
Nobranch  
**Description:** Disables Dead Branch / Bloody Brunch / Red Brunch and Porinx Box.  
**File:** npc/mapflag/nobranch.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag nobranch`  
  
  

Noexp  
**Description:** Disable Exp gain for Players.  
**File:**npc/mapflag/noexp.php  
**Parameter:** <none>  
`usage: `<map>` mapflag noexp`  
  
  

Noicewall  
**Description:** Disable Icewall on a Map.  
**File:** npc/mapflag/noicewall.txt  
**Parameter:**  
`usage: `<map>` mapflag noicewall`  
  
  
Noloot  
**Description:** Disable loot on a Map.  
**File:** npc/mapflag/noloot.txt  
**Parameter:** <map> mapflag noloot  
`usage: `<map>` mapflag noloot`  
  
  

Nomemo  
**Description:** Disable /memo on a Map  
**File:** npc/mapflag/nomemo.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag nomemo`  
  
  
Nopenalty  
**Description:** Disable death penalty.  
**File:** npc/mapflag/nopenalty.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag nopenalty`  
  
  

Nopvp  
**Description:** Disable PvP (Player vs. Player) on a Map  
**File:** npc/mapflag/nopvp.txt  
**Parameter:** off  
`usage: `<map>` mapflag pvp `<parameter>  
  
  
Noreturn  
**Description:** Disables the Return Warp.  
**File:** npc/mapflag/noreturn.php  
**Parameter:** <none>  
`usage: `<map>` mapflag noreturn`  
  
  
Nosave  
**Description:** Disables Autosave on a Map, if the Parameter isnt defined, Warp to the last field.  
**File:** npc/mapflag/nosave.txt  
**Parameter:** SavePoint  
`usage: `<map>` mapflag nosave <parameter(Optional)>`  
  
  
Noskill  
**Description:** Disable Skills  
**File:** npc/mapflag/noskill.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag noskill`  
  
  

Noteleport  
**Description:** Disable all kinds of Teleport.  
**File:** npc/mapflag/noteleport.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag noteleport`  
  
  
Novending  
**Description:** Disable Vending  
**File:** npc/mapflag/novending.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag novending`  
  
  
Nowarp  
**Description:** Disable @GO  
**File:** npc/mapflag/nowarp.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag nowarp`  
  
  
Nowarpto  
**Description:** Disable Warp to  
**File:** npc/mapflag/nowarpto.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag nowarpto`  
  
  
Partylock  
**Description:** Disables Party modifications  
**File:** npc/mapflag/partylock.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag partylock`  
  
  
Pvp  
**Description:** Defines the Map as Player vs Player Map  
**File:** npc/mapflag/pvp.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag pvp`  
  
  
Pvpnoguild  
**Description:** Ignore Aliances on Guild vs Guild Maps  
**File:** npc/mapflag/pvpnoguild.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag pvpnoguild`  
  
  
Pvpnoparty  
**Description:** Ignore Party on Player vs Player Maps  
**File:** npc/mapflag/pvpnoparty.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag pvpnoparty`  
  
  
Reset  
**Description:** Disable Neuralizer Item(12213) usage  
**File:** npc/mapflag/reset.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag reset`  
  
  
Skillduration  
**Description:** Set Duration for a Skill on a Map  
**File:** npc/mapflag/skillduration.txt  
**Parameter:** 0-...(?)  
`usage: `<map>` mapflag skillduration `<parameter>  
  
  
Skillmodifier  
**Description:** Set the Damage for a Skill on a Map  
**File:** npc/mapflag/skillmodifier.txt  
**Parameter:**0-...(?)  
`usage: `<map>` mapflag skillmodifier `<parameter>  
  
  
Town  
**Description:** Defines a Map as a Town.  
**File:** npc/mapflag/town.txt  
**Parameter:** <none>  
`usage: `<map>` mapflag town`  
  
  
Zone  
**Description:** Flags maps as part of zones  
**File:** npc/mapflag/zone.txt  
**Parameter:** see mapzonedb.txt  
`usage: (?) mapflag zone Aldebaran Turbo Track (?)`  
  
  

[Category:incomplete](Category:incomplete "wikilink")
