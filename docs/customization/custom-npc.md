# Custom NPCs

# Client-side

## Adding Sprite

Download the .spr and .act file for the NPC and place them in data/sprite/npc.

## NPCidentity.lub

Add your NPC to NPCidentity.lub. Most recommend adding new NPC's with ID's starting at 1500, so that there is room for
new official sprites without them overlapping your custom ones. The name of the sprite does not have to be capitalized.
If the name of the sprite is lowercase, you can add them to all files as lowercase, such as in the example below, the
sprite can be JT_NPCNAME or JT_npcname. The last line of this file does not need a comma at the end of the line, but any
lines which are not the last line require a comma.

Format:

`JT_NPCNAME = 10500`

## jobname.lub

Exact same rules apply to this file. Can be lowercase or uppercase, last line does not have to have a comma. Slightly
different format is all that differs from NPCidentity.lub.

Format:

`[jobtbl.JT_NPCNAME] = "NPCNAME",`

# Server Side

## constants.conf

Located in your db folder. Find the NPC list and add your NPC to the bottom.

Format:

`NPCNAME:                  10500`

## npc.h

npc.h is located in src/map. Open it in notepad or another text editor.

Find:

`#define MAX_NPC_CLASS2_END 10203`

Change to:

`#define MAX_NPC_CLASS2_END 10800`

You can make the max larger if you feel it is necessary, but this should give you plenty of room. Save and
[recompile](Compiling "wikilink").

[Category:Database](Category:Database "wikilink") [Category:Data](Category:Data "wikilink")
[Category:Customization](Category:Customization "wikilink")
