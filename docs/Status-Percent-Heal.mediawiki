==Heals the target in a percentage.==
 
 #define status_percent_heal(bl, hp_rate, sp_rate) [[status_percent_change]](NULL, bl, -(hp_rate), -(sp_rate), 3)

 status_percent_heal(Target, X, Y);
* Target:
** src = User
** bl  = Skill Target
* X = Amount healed in HP (in % , 100 = 100%, full recovery)
* Y = Amount healed in SP (in % , 100 = 100%, full recovery)











[[Category:Source_Functions]]