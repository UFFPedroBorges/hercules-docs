==Syntax==
 char* '''msg_txt'''(int msg_number);

==Parameters==
* '''msg_number''' - Message ID of the requested message.

==Description==
This function retrieves a pointer to a message string, which was loaded from [`conf/messages.conf`](https://github.com/HerculesWS/Hercules/blob/stable/conf/messages.conf). Although the return value is not typed as '''const''', it should be handled as such and the contents pointed to by the pointer should be only read.

==Example==
 '''[[Clif Displaymessage|clif->displaymessage]]'''(sd->fd, msg_txt(3));
This would pass pointer to the message "Character not found." to the function [[Clif Displaymessage]].

[[Category:Source Functions]]
