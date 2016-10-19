==Syntax==
 int '''clif_displaymessage'''(const int fd, const char* mes);

==Parameters==
* '''fd''' - Socket descriptor (connection handle) for the connection to send the text to.
* '''mes''' - Text to send to the client.

==Description==
Sends a text to the client, which is displayed like normal self-chat (green font in chat and above characters head. Message is only visible to the client, it was sent to. Usually this function is used for at-command output.

==Example==
 clif->displaymessage(sd->fd, "Character not found.");
Would display "Character not found." above sd's head. Same thing can also be accomplished (and preferred) by using [[msg_txt]] function:
 clif->displaymessage(sd->fd, msg_txt(3));

[[Category:Source Functions]]