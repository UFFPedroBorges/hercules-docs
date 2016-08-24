# Basic Requirements

[[Hercules]] works off of the [[wikipedia:Client–server_model|client-server model]]. The player, usually using a [[Hexing|hexed]] kRO [[Renewal|RE]] client, first connects to the [[Login Server]]. When the client enters their login information, it is given the list of available char-servers, which the player chooses from. After the server has been chosen, the client connects to the selected [[Character Server]], which displays the characters on that player's account. After selecting a character, the client is directed to the [[Map Server]], which maintains maps and the character positions on the server and relays this information to the client.

Hercules is designed to run on a machine that is designated as a Server, either Dedicated or VPS. It can run on a workstation, but using that workstation for other tasks (including playing on the same machine that is running the server) will reduce performance.

# Hardware Requirements
Hercules requires the following resources from the machine in order to function without problems or the common "Lag":

* 1.5 GHz or faster CPU, either Intel or AMD is acceptable. Some members have reported that they have gotten Hercules to run on other processors.
* 128 MB of RAM, MINIMUM. The map server in an idle state consumes about 76MB of RAM, depending on how many maps and [[NPC|NPCs]] are loaded (41mb when no NPCs are in use).
* A video card powerful enough to run the Operating System of your choice (or no video card at all). Hercules is a console based software, which means that all that is required to run it is a console or command access.
* Fast internet or network connection. This is very hard to predict. A lot of questions arise that ask 'how much bandwidth does Hercules need?'. There is no answer to that. It is all depending on how many characters are connected, from where, and what they do while connected to the server.
* 250MB of Hard Drive space or better, up-to gigabytes depending on how big the database may get.

# Software Requirements
Hercules, depending on what you plan to do with it and what platform you run it on, will require, at a minimum, the following:

* GCC compatible compiler
* GNU Make
* zlib
* MySQL server and libraries
* Git
* pcre

# Supported Operating Systems
The following operating systems have been tested and are known to work:

## [[wikipedia:Linux|Linux]]
* Debian Based: [Debian](http://www.debian.org/), [Knoppix](http://www.knoppix.net), [Ubuntu Server & Desktop](http://www.ubuntu.com/)
* RPM Based: [CentOS](http://www.centos.org), [Fedora Core](http://fedoraproject.org/), [Mandriva](http://www2.mandriva.com/), [Red Hat Linux](http://www.redhat.com/rhel/), [SUSE Linux](http://www.novell.com/linux/)
* Others: [Gentoo](https://www.gentoo.org), [Slackware](http://www.slackware.com/)

## [[wikipedia:Unix|Unix]]
* BSD Based: [FreeBSD](http://www.freebsd.org/), [OpenBSD](http://www.openbsd.org/)

## [[wikipedia:Microsoft_Windows|Windows]]
* [[wikipedia:Windows_Server|Server Versions]]: Windows Server 2008, Windows Server 2008 R2, Windows Server 2012
* Home Versions: Windows Vista, Windows 7, Windows 8, Windows 8.1
