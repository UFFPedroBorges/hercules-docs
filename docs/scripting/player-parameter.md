**Player Parameters**, in [scripting](scripting "wikilink"), are a set of params that look like [character
variables](Variables#Player_Variables "wikilink"), they exist during runtime only and make certain information regarding
the character available to scripts for read (and write depending on the variable), they're the following (most of them
are self-explanatory):

- StatusPoint
  - Number of remaining Status Points the character has
- BaseLevel
- SkillPoint
  - Number of remaining Skill Points the character has
- Class
- Upper
  - \(0\) if the character is normal class, (1) if advanced, (2) if baby.
- Zeny
- Sex
  - Whether the character is male (1) or female (0)
- Weight
- MaxWeight
- JobLevel
- BaseExp
- JobExp
- Karma
  - Not officially in use. You can use this param however you want.
- Manner
- NextBaseExp
- NextJobExp
- Hp
- MaxHp
- Sp
- MaxSp
- BaseJob
- BaseClass
- killerrid
  - The [RID](RID "wikilink") of the game object that last killed the character.
- killedrid
  - The [RID](RID "wikilink") of the game object that was last killed by the character.
- SlotChange
  - Stores the number of times this character may use the 'slot change' function in char select
  - Can be modified
- CharRename
  - Stores the number of times this character may use the 'char name change' function in char select
  - Can be modified
