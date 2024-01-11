== Define a string variable in the source ==

 #define pc_setglobalreg_str(sd,reg,val) [[pc_setregistry_str]](sd,reg,val,3)

 pc_setglobalreg(sd,"VARIABLE_NAME", "VALUE");

This only works for string variables, for numbers check [[PC_Setglobalreg]].




[[Category:Source_Functions]]