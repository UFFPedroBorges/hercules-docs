== Set player integer variable from source ==

 #define pc_setglobalreg(sd,reg,val) [[pc_setregistry]](sd,reg,val,3)

 pc_setglobalreg(sd,"VARIABLE_NAME", VALUE);

This only works for numeric variables, strings check [[pc_setglobalreg_str]].




[[Category:Source_Functions]]