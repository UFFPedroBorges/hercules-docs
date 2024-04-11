## Quest Log System

#### Basic Structure of NPC

First of all you must have a knowledge on basic scripting, if not please kindly Click
[Here!](Basic_Scripting "wikilink").

#### Quest Window

The Quest Window or Quest Journal (Opened via Alt+U) allows the player to view all quests their character has started
but not yet completed (Except for instance dungeon quests and Battlegrounds instances, which always remain once
started). To place a quest in the Inactive tab, right click once on it and the name will turn gray. It will then appear
on the Inactive tab instead of Active. Right clicking the name again will bring it back to the Active tab. Moving the
quest back and forth has no effect on whether you can continue it or not. Not every quest has a quest window component.
Those quests who have quest window walkthroughs can be found in this category as well as by having their infobox in
gold. Additionally, the Quest Window guides are not comprehensive, and do not specify the exact coordinates of the next
NPC or location the player must visit. It is highly recommended to continue using the wiki guides along with the in-game
walkthroughs.

<figure>
<img src="QWindow.jpg" title="caption" />
<figcaption>caption</figcaption>
</figure>

## Quest Database - Adding Quest

### Structure

    {
    	Id: Quest ID
    	Name: "Quest Name"
    	TimeLimit: seconds
    	Targets: (
    	{
    		MobId: Mob_ID
    		Count: number
    	},
    	)
    	Drops: (
    	{
    		ItemId: item_to_drop
    		Rate: Drop_Rate
    		MobId: Mob_ID_to_match
    	},
    	)
    },

Quest ID - ID of the quest, must increment and should not be duplicated.  
Name - The title of the Quest you made.  
Time Limit - Time limit for the quest to be finish in seconds.  
Targets - Monsters killing list contain mob ids and count.  
Drops - Item id to drop.

### Example

For this example I will make a quest that will require to kill 10 Poring's.

    {
    	Id: 65000
    	Name: "Quest - Poring Hunt"
    	Targets: (
    	{
    		MobId: 1002
    		Count: 10
    	},
    	)
    },

#### Client Side Editing

You have to edit your questid2display.txt

#### Structure

    QUESTID#Quest Name#FILENAME#LOG_FILENAME#
    Summary description#
    Objective description#

### Example

    65000#Quest - Poring Hunt#SG_FEEL#QUE_NOIMAGE#
    Find the monster named Poring and kill 10#
    Hunting 10 Poring#

## Quest Log Commands

### Set Quest

    *setquest <ID>;

Place quest of <ID> in the users quest log, the state of which is "active".

### Example

    prontera,xx,xx,4	script	SetQuest	51,{
    setquest 65000;	// This will add the Quest ID 65000 to your Quest Window.
    }

This sample will add the quest "Quest - Poring Hunt" which I stated on the Adding Quest. **Note**: The example is just a
simple NPC that will add Quest ID 65000 every time you click it, You can add conditions so that it can only be taken
once.

### Complete Quest

    *completequest <ID>{,<ID2>};

Change the state for the given quest <ID> to "complete" and remove from the users quest log.  
  
If a second quest id of greater value is specified, all quests between the two will be completed.

### Example

    prontera,xx,xx,4	script	CompleteQuest	51,{
    completequest 65000;	// This will change the state of the quest to "complete"
    set zeny,zeny + 100;   //just add line like this if you want to give zeny reward if a player finish the quest.
    getitem 501,1;         //just add line like this if you want to give item reward if a player finish the quest.
    }

### Erase Quest

    *erasequest <ID>{,<ID2>};

Remove the quest of the given <ID> from the user's quest log.  
  
If a second quest id of greater value is specified, all quests between the two will be erased.

### Example

    prontera,xx,xx,4	script	EraseQuest	51,{
    erasequest 65000;	// This will remove the quest to your Quest Window.
    }

### Change Quest

    *changequest <ID>,<ID2>;

Remove quest of the given <ID> from the user's quest log. Add quest of the <ID2> to the the quest log, and the state is
"active".

### Example

    prontera,xx,xx,4	script	ChangeQuest	51,{
    changequest 65000,65001; // This will remove the quest ID 65000 and change it to 65001 with the state "active".
    }

### Check Quest Progress

    *questprogress(<ID>{,PLAYTIME|HUNTING})

If no additional argument supplied, return the state of the quest:

    0 = Quest not started (not in quest log)
    1  = Quest has been given
    2  = Quest completed

    *questactive(<ID>)

Check whether the given quest is in its active state. Returns true if the quest is active, false otherwise (quest not
started, inactive or completed)

### Example

    prontera,xx,xx,4	script	CheckQuest	51,{

    if(!questactive(65000)) { //Quest is Inactive
    mes "[Jelly]";
    mes "Quest is Inactive";
    close;
    } else if(!questprogress(65000)) { //Quest Not started yet 
    mes "[Jelly]";
    mes "Quest Not Started";
    close;
    } else if(questactive(65000)) { //Quest is Active
    mes "[Jelly]";
    mes "Quest is Active!";
    close;
    } else if(questprogress(65000) == 2) {	// Quest finished.
    mes "[Jelly]";
    mes "Quest Finished!";
    completequest 65000;
    close;
    } 
    }

If parameter "PLAYTIME" is supplied:

    0 = Quest not started (not in quest log)
    1  = the time limit has not yet been reached
    2  = the time limit has been reached

If parameter "HUNTING" is supplied:

    0 = Quest not started (not in quest log)
    1 = Player hasn't killed all of the target monsters
    2 = Player has killed all of the target monsters

### Example \| Hunting

    prontera,xx,xx,4	script	CheckQuest	51,{

    if (!questprogress(65000,HUNTING)) {
    mes "[Jelly]";
    mes "Quest not Started",
    close;
    } else if (questprogress(65000,HUNTING) == 1) {
    mes "[Jelly]";
    mes "You haven't killed all of the target monsters.";
    close;
    } else if (questprogress(65000,HUNTING) == 2) {
    completequest 65000;
    set zeny,zeny+100;      //Zeny Reward
    getitem 501,1;          // Item Reward
    mes "[Jelly]";
    mes "Quest Finished";
    close;
    }
    }

### Show Event

    *showevent <state>, <color>;

    Show a colored mark in the mini-map like "viewpoint" and an emotion on top 
    of a NPC. This is used to indicate that a NPC has a quest or an event to 
    certain player/s. 

    state can be:
    	0 = disable ( Used to disable and remove the mark and the emotion from 
    		the NPC. )
    	1 = exclamation emotion ( Used to show an important quest event to 
    		certain player. )
    	2 = interrogation emotion ( Used to show an non-important quest event 
    		to certain player. )
    Other value may cause client crashes.

    color can be:
    	0 = yellow "Quest"
    	1 = orange "Job"
    	2 = green "Event"
    	3 = an MVP flag
    Other values show a transparent mark in the mini-map.

### Increasing Max Quest DB

    trunk/src/map/quest.h 

Find this line and increase the value.

    #define MAX_QUEST_DB (60355+1) // Highest quest ID + 1

Recompile, Cheers!

(If you don't know how to recompile click [Here!](Compiling "wikilink"))
