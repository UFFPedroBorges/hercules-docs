==The Pet DB==
The information about pets are stored in the pet_db.txt file in the db folder. Here is a quick 
rundown of what the database contains. We will look at a Poring, as an example.
<pre>
MobID,Name,JName,ItemID,EggID,AcceID,FoodID,
Fullness,HungryDelay,R_Hungry,,R_Full,Intimate,Die,
Capture,Speed,S_Performance,talk_convert_class, 
attack_rate,defence_attack_rate,change_target_rate, pet_script
</pre><br>
<pre>
1002,PORING,Poring,619,9001,10013,531,80,20,50,100,250,20,2000,400,1,0,350,400,800,{ petloot 10; }
</pre><br>
* '''MobID:''' Obvious, check mob_db.txt for a monster's MobID.
* '''Name:''' Again, check mob_db.txt for this value. It is the second value in mob_db.
* '''JName:''' Basically will be the default name for your pet.
* '''ItemID:''' The taming item's ID. In this case, an Unripe Apple(619).
* '''EggID:''' The egg's ID.
* '''AcceID:''' The item ID of the accessory. '''For custom pets, leave this value to be 0.'''
* '''FoodID:''' The food for your pet. In this case, Apple Juice(531).
* '''Fullness:''' No idea, but every pet seems to have a value of 80. Keep it at that.
* '''HungryDelay:''' The rate the pet gets hungry. The lower the number, the faster it will get hungry.
* '''R_Hungry:''' No idea. I made the value for mine 20.
* '''R_Full:''' No idea. I made the value for mine 100.
* '''Intimate:''' No idea. I made the value for mine 250.
* '''Die:''' How much intimacy points you lose when you die. Usually set to 20.
* '''Capture:''' The rate of capture. 1% = 100 and 100% = 10000. Basically, choose your percentage and add two zeroes to the end.
* '''Speed:''' The speed in which the pet will follow you (not sure). I set mine at 200.
* '''S_Performance:''' No idea. I set mine at 1.
* '''talk_convert_class:''' The pet's dialogue used in pettalktable. This will allow your custom pets to talk like certain pets.
* '''attack_rate:''' Chance the pet will attack. Same format as Capture rate.
* '''defence_rate:''' Chance the pet will attack when master is attacked. Same format as Capture rate.
* '''change_target_rate:''' Chance the pet will change targets. Same format as Capture rate.
* '''pet_script:''' The special skill used by the pet.<br>
As to pet skills, pet_db gives an in depth explanation on how to use it. It's quite simple to 
give your custom pet custom skills, so I will not be detailing this in this guide. If you want 
your custom pets to use skills, you may have to change:
<pre>
// Does the pet need its equipment before it does its skill? (Note 1)
pet_equip_required: yes
</pre>
to no, since they will not have equipment

==The Item DB==
Taming items and pet egg information are stored in the item_db.conf file. A taming item format 
is the following, using an Unripe Apple(619) as an example:
<pre>
{
	Id: 619
	AegisName: "Unripe_Apple"
	Name: "Unripe Apple"
	Type: 2
	Buy: 1000
	Weight: 50
	Upper: 63
	Script: <" pet 1002; ">
},
</pre>
Important to note is the part in bold. The ETC item you use for custom taming items will need 
to follow this same format.<br>
A pet egg format is the following, using a Poring Egg(9001) as an example:
<pre>
{
	Id: 9001
	AegisName: "Poring_Egg"
	Name: "Poring Egg"
	Type: 7
	Buy: 20
},
</pre>
This part is very easy, as you can see.<br>
Basically, model your taming items and eggs to these formats, and you will not need to know any specifics.

==Replacing A Pet==
The easiest way to have a custom pet is to replace a current pet. Say you want a Succubus
(1370). Choose a pet that you don't want anymore. For our example, we will replace a Poring. To do this, simply replace the following to get a custom pet that has the exact same status and skills as a Poring.
<pre>
1370,SUCCUBUS,Succubus,619,9001,0,531,80,20,50,100,250,20,2000,400,1,0,350,400,800,{ petloot 10; }
</pre>
You can customize this further by editing the values you wish. Notice that the accessory value has been changed to 0.<br>
Next, you must inherit the item in item_db2.conf for information about the taming item. To do this,  Add the following values, following the format of the Item DB explained above:
<pre>
{
	Id: 619
	Inherit: true
	Script: <" pet 1370; ">
},
</pre>
<small>''Note: Read more information about [https://herc.ws/board/topic/2954-item-db-file-structure-overhaul/ Item DB file structure overhaul]''</small><br>
Now you are done, and have a Succubus instead of a Poring. To catch a Succubus, you will use an Unripe Apple (619). To change the item descriptions and egg sprites, please refer to another section of this guide.

==Adding A New Pet==
I didn't like the idea of replacing an existing pet, so I sought to add in pets. The process is
a little similar to replacing a pet. Instead, you create a new line in pet_db.txt with your 
new pet information. As an example, we will add a Succubus to the pet_db.
<pre>
1370,SUCCUBUS,Succubus,739,9031,0,537,80,20,20,100,250,20,150,200,1,0,800,400,200,
{ petskillbonus bLuk,20,10,90; }
</pre>
I made the Succubus's taming item a Rouge(739), her food Pet Food(537), her capture rate 1.5%, and her pet skill +20 Luck for 10 seconds every 90 seconds.<br>
Add the above line to the end of pet_db, and you are done. Now we have all the original pets AND a Succubus.<br>
The next step is to create a taming item and an egg for this Succubus. To create the taming 
item, go to item_db, and pick an item you want to use for the taming item and add Inherit it on item_db2. I suggest using an ETC item, as they really do not serve much purpose. Edit the values accordingly to follow the pet taming item format. An example of Rouge for the Succubus taming item:
<pre>
{
	Id: 739
	Inherit: true
	Type: 2
	Upper: 63
	Script: <" pet 1370; ">
},
</pre>
Next, we need a pet egg. This, you will have to actually create. Choose an available Item ID. I
suggest starting from 9028, if not already used, and work your way up, for pet eggs. Add a line to item_db2.conf with the values for a pet egg. For example, a Succubus egg:
<pre>
{
	Id: 9031
	AegisName: "Succubus_Egg"
	Name: "Succubus Egg"
	Type: 7
	Buy: 20
},
</pre>
The egg ID is 9031, as you can also see from the entry in pet_db.<br>
After doing this, you now have added a Succubus into the database, with her own taming item and egg. Everything is now ready on the server side.

==Egg Sprites and Item Descriptions==
In order for your client to not crash, you must have information and a sprite for the pet egg.
For old client. Go to your idnum2itemdesctable.txt, idnum2itemdisplaynametable.txt, num2itemdesctable.txt, and num2itemdisplaynametable.txt, and create a new entry for the egg. I will not go into detail on how to do this; there are other guides for this. You may also choose to edit the item 
description of the taming item, though this is not necessary.<br>
Next, you have to give the egg a sprite, or else your client will crash. To do this, edit 
idnum2itemresnametable.txt and num2itemresnametable.txt and add in an entry for the egg. Refer to this topic for what to use for egg sprites. If you have no clue how to work with resnametables, then search the forums.<br>
I will give examples of the values I put in my tables.<br>
idnum2itemdesctable and num2itemdesctable:
<pre>
9031#
An egg in which a Succubus Cute Pet rests. Can be hatched by using a ^33CC33Pet Incubator^000000.
Class :^777777 Monster Egg^000000
#
</pre>
idnum2itemdisplaynametable and num2itemdisplaynametable:
<pre>
9031#Succubus_Egg#
</pre>

idnum2itemresnametable and num2itemresnametable:
<pre>
9031#Áö¼Ó¼º¾Ë#
</pre>
If you use 2013 client, edit your iteminfo.lua\lub. Visit [[Custom_Items#Item_Placement_on_Data_Folder_.28For_New_Clients.29|Item Placement on Data Folder]]<br>
<pre>
	[9031] = {
		unidentifiedDisplayName = "Succubus Egg",
		unidentifiedResourceName = "¾Ï¼Ó¼º¾Ë",
		unidentifiedDescriptionName = {
			"An egg in which a",
			"Succubus Cute Pet rests.",
			"Can be hatched by",
			"using a ^33CC33Pet Incubator^000000.",
			"^33CC33Cordial/Loyal Bonus^000000",
			"When summoned,",
			"Has a chance of draining 2% of enemy's HP while attacking.",
			"Class: ^777777Monster Egg^000000"
		},
		identifiedDisplayName = "Succubus Egg",
		identifiedResourceName = "¾Ï¼Ó¼º¾Ë",
		identifiedDescriptionName = {
			"An egg in which a",
			"Succubus Cute Pet rests.",
			"Can be hatched by",
			"using a ^33CC33Pet Incubator^000000.",
			"^33CC33Cordial/Loyal Bonus^000000",
			"When summoned,",
			"while physically attacking, physical damage done to enemy, 5% will transfer as your HP",
			"Class: ^777777Monster Egg^000000"
		},
		slotCount = 0,
		ClassNum = 0
	},
</pre>

==Pettalktable==
By default, your pet will talk like a Poring. If you wish to change this, edit the 
talk_convert_class value in pet_db to the ID of one of the original pets. For example, to make our Succubus talk like a Zealotus, edit her talk_convert_class to 1200. Now she will talk like a Zealotus.<br>
If you want to edit what she says, then you may. However, note that if you edit this, both the
Zealotus and Succubus will say the same things. It is not currently possibly to add in talk 
for Succubus and not replace anything. I recommend choosing a pet that you or your clients may never use, and replace that pet's dialogue.


==Q&A==
Q. What will the pet portrait be?<br>
A. The pet portrait will be a Poring by default. Customised images should be placed in:
:data\texture\À¯ÀúÀÎÅÍÆäÀÌ½º\illust<br>
<br>
Q. What will the new pet's performance be?<br>
A. Nothing. The sprite will disappear and reappear quickly. Your game won't crash.<br>
<br>
Q. How many pets can I add?<br>
A. Up to 300. I believe that if you change the MAX_PET_DB value in pet.h in the src/map folder, you can add more. Note that you will have to recompile.<br>
<br>
Q. Why does the egg name become red when I try to hatch it and the pet not show up?<br>
A. This is caused by the egg being spawned via an @item command (or equivalent). To create the egg you need to use the @makeegg command.<br>
<br>

[[Category:Customization]]
[[Category:Data]]
[[Category:Database]]