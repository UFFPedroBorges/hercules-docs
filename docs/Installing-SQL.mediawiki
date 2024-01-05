= Introduction =
This article will guide you through the installation and configuration stages of MySQL for your particular Operating System. What is a MySQL database? [[wikipedia:MySQL|MySQL]] is a multi-user access database that stores a number of different kinds of information in scaleable tables. In layman's terms, it puts a bunch of stuff in charts for your server to read. Hercules no longer supports text based save files (for Accounts, Characters, etc.) and requires a MySQL database to create these save files.

== Windows ==
This guide will instruct you on installing MySQL on Windows Vista/7, although it should work relatively the same with Windows XP. This guide also assumes you have already [[Installation_on_Windows|installed your Hercules server]].<br />
<br />
'''<big>Uninstallation Note</big>'''<br />
Before continuing, it is important to note that if you make an error and decide to start again by uninstalling the MySQL database and software, that you make sure you do a ''thorough'' uninstallation, and then reboot Windows before trying again. A couple tips to make sure your uninstallation is thorough:
* Uninstall Workbench first
* Remove the MySQL database folders in your user folder. This is generally in: 
 C:\Users\<YOUR_USER_NAME>\AppData\Roaming\MySQL 
:Just delete the whole folder.
* Run Administrative Tools -> Services and look to make sure nothing MySQL related is running or set to run (because it shouldn't exist anymore)
* Go to the location on your hard drive you installed MySQL5 and Workbench and ensure everything is deleted.
* Make sure you reboot.
* There is a Oracle made guide [http://dev.mysql.com/doc/refman/5.1/en/windows-installer-uninstalling.html here], but it isn't necessarily thorough.
* If you still have hanging and crashing during the configuration wizard, you may have to create your root account manually. Do an internet search for this, as it varies by system. And continue afterwards at the "MySQL Workbench" section.

=== Download ===
To install MySQL Server you will first need to download the package corresponding to your version of Windows. [http://dev.mysql.com/downloads/mysql/ MySQL Community Server] is available for free and is exactly what is needed. Version 5.5 currently works well with Hercules and is recommended. '''ENSURE''' that you download the appropriate bit version (32 or 64) for your system, if you do not, you will receive errors during the execution wizard. This software installs the server on your computer that stores the data files and tables. Although alone, without prior knowledge of MySQL it is very difficult to operate and configure your servers data. That is why you will need MySQL Workbench.<br />
<br />
[http://dev.mysql.com/downloads/workbench/5.2.html MySQL Workbench] is a tool for viewing your MySQL database in a GUI environment. As said, it is not required but very beneficial; in addition, it is required by this guide. To be able to install and run MySQL Workbench 5.2 your System also needs to have the libraries listed below installed. The listed items are provided as links to the corresponding download pages where you can fetch the necessary files.

[http://www.microsoft.com/download/en/details.aspx?id=17113 Microsoft .NET Framework 4 Client Profile] <br />
[http://www.microsoft.com/download/en/details.aspx?id=5555 Microsoft Visual C++ 2010 Redistributable Package (x86)]

=== Configure Hercules Files ===
Before you begin with your MySQL installation, you need to setup your server conf files to be ready for the database you are about to install. I choose to do this in advance, because it allows you to have the usernames and passwords ready for use so you don't have to go back and set them, and you can just run your server afterwards with everything all ready.
* Open "inter-server.conf", and change sql.db_password, char_server_pw, map_server_pw and log_db_pw to a password of your choice. For this guide we will use the password "Fish". Passwords are case sensitive. This is not a strong password, and you should use a better one, this is just an example. Also change log_db_db to "log". All other fields should be let alone, the default username and port functions fine. ([http://imageshack.us/a/img546/9444/interathena.jpg Image])
* Open "map-server.conf" and "char-server.conf" and locate the server communication passwords:
 userid: s1
 passwd: p1
Change these to whatever you want, but something secure. For this guide we will use "FishUser" and "FishPassword"
 userid: FishUser
 passwd: FishPassword
<br />
Make sure these are the same in both map-server and char-server otherwise you will have errors.
* There are additional SQL configuration features in "login-server.conf" that you should take a look at now, to enable for use (such as IPban features).
* Write all these passwords down or keep the files open for reference and continue to your MySQL installation!

=== Install MySQL ===
First, you will need to install the MySQL server where all the data will be stored. After downloading the [http://dev.mysql.com/downloads/mysql/ MySQL Community Server], run the installer and use the following steps (''for this installation version 5.5.28 was used'').
# Click next and accept the license agreement.
# Click "Typical" for Setup Type; then click "Install" (you may have to allow UAC control from windows).
# Click "Next" when the MySQL Enterprise tool pops up, this is a simple advertisement.
# After installation is finished the completion screen with a "Finish" button will show, make sure you have "Launch the MySQL Instance Configuration Wizard" '''CHECKED'''! The configuration wizard will allow you to setup the server to accept the kind of data you want and by setting it up now you will most likely never have to configure it again.
# Click "Next" at the first screen, and then click "[http://imageshack.us/a/img90/1771/standardconfig.jpg Standard Configuration]" and hit "Next".
# Check both "Install As Windows Service" and "Include Bin Directory in Windows PATH" for the Service Name, name it "''MySQL5''" and ensure "Launch the MySQL Server Automatically is '''CHECKED'''. ([http://imageshack.us/a/img685/3323/serverinstance.jpg Image])
# On the next screen, you will need to select the root password. This password is very important as you will '''never be able to retrieve it''' so make sure you write it down somewhere safe. The "root" access to your MySQL database can pretty much do anything to your data, so make sure you keep this information safe. If you want to enable root access from a remote machine, check the included box. You probably won't need to enable that unless you know what you're doing. Keep the password you selected available for now.
# On the next screen just click "Execute" to run the configuration unless you want to go back and change something.
# Once it is finished, hit "Finish" to close the wizard. It will report if there are any errors (there shouldn't be).

=== MySQL Workbench ===
Next it is time to install the MySQL Workbench application. This application will allow you to edit your database and prepare it for Hercules, as well as perform maintenance in the future.
# Run the MySQL Workbench installer and click "Next" on the first screen.
# Choose your installation directory. The default directory should be fine. Click "Next" to proceed.
# Select "Complete" and click "Next", and then install, granting permissions when prompted.
# Once the wizard is completed, hit "Finish" and the default Workbench screen will come up.
# This is called the Home Screen and should look like [http://imageshack.us/a/img571/3885/workbenchhome.jpg this].
# You need to create a new server instance to host your files for Hercules to access. Select "New Server Instance" under the "Server Administration" section.
# A window will pop up, select "localhost" and click "Next". This installs the instance on the localhost, which is your computer.
# On the next screen, leave everything the default. Where it says "Username" leave that at root, so you have root access. Under that, click "[http://imageshack.us/a/img845/4056/storeinvault.jpg Store in Vault]" and enter the root password from earlier (it's alright to copy/paste the password if you put it in a text file).
# After it has successfully tested the database connection, click "Next"
# On the next screen, leave the configuration settings defaulted. It should point to the existing service (MySQL5 from earlier) and the default path is fine. ([http://imageshack.us/a/img600/1089/defaultwindowsconfig.jpg Image])
# On the next screen hit "Next" and then "Continue" on the popup. Leave the Server Instance with the default name of
 mysqld@localhost
You are now ready to install your Hercules databases.

=== Database Installation ===
It is now time to install the pre-installed database files that will allow your Hercules server to connect to your MySQL database and properly store data, such as characters, items, and guilds. Open up MySQL Workbench to the home screen.
# Double click "localhost" on the left under the "SQL Development" section. ([http://imageshack.us/a/img337/8550/localhostdoubleclick.jpg Image])
# On the next screen (after a small loading bubble pops up), you will have access to the specific tables that were mentioned earlier. You will enter this screen in the future when you want to edit accounts and other things directly (not common).
# We need to install a new "Schema", this is like a folder where all the database tables are stored. [http://imageshack.us/a/img194/2897/newschema.jpg Click the yellow cylinder looking thing in the upper left to create a new Schema]. Name it "ragnarok" - '''NOTE!''' Lower case is important here, make sure it is exactly "ragnarok". The server collation should be "Server Default". 
# Click "Apply" to create the Schema. A window will pop up with the actual commands that are going to take place; click "Apply" again to finalize your order.
# Now right click 'ragnarok' under "Object Browser" and click "Set as default schema", a line will appear through it telling the browser that any commands you make now will be ordered to that Schema.
# Next, [http://imageshack.us/a/img571/205/opensqlscript.png click the button directly to the left of the one you just did], it says "SQL" with a tiny folder. Navigate to your Hercules/sql-files/ folder, and open the sql script file "main.sql".
# You'll see a bunch of code appear, these are commands that will tell the browser to create plain databases for your Hercules server. Click the yellow lightning bolt in the upper left hand corner to execute it and allow it to finish (ensure you click the first lightning bolt, the one without a cursor symbol or a magnifying glass over it).
# After it finishes, a bunch of executed commands will appear on the bottom of the screen. You can now expand the ragnarok schema to see a bunch of tables. ([http://imageshack.us/a/img72/1450/ragnaroktables.jpg Image])
# Now, do the same thing for a schema called "log", but open and execute logs.sql instead of main.sql. Ensure the tables are there as well.
# Close the existing query tabs by hitting the "X" in the upper right of the tab. With the ragnarok tables still open, scroll down to the "login" table and '''RIGHT click''' it, then select "Edit Table Data".
# Here you'll see existing account information that players can log in with to make characters. If you remember, the first account is the server communication account and it has the default password that you were asked to reset earlier. For our example we chose "FishUser" and "FishPassword". Enter these in the "username" and "password" field. And then create your first GM account by clicking where the word "null" is on the row with a ' * ' and enter "2000000" for the "account_id" field, with a username and password that you like. For this guide we chose a username of "HercGM" and a password of "12345" and a sex of "M". To enable full administrator GM, just set the "group_id" to "99". Zero out everything else. [http://imageshack.us/a/img411/5976/logintables.jpg When you are finished it should look like THIS].
# Hit the "Apply" button in the corner and then again when the code prompt appears. This should modify your tables. After it is done, you may close the SQL Editor by clicking the "X" on the tab at upper left corner. Hitting the "X" in the upper right closes the whole workbench. If you accidentally close it, just open it again.
# On the Workbench Home Screen, click "Manage Security" under Server Administration. Select "mysqld@localhost" and then click "OK".
# The next screen is the security window. You want to add an account that your server can use to access the databases that is NOT the root account, for enhanced security. Click "Add Account" in the lower left of the default screen.
# The login name needs to be "ragnarok", and the password we selected earlier for this guide is "Fish". The system will tell you how strong your password is... Fish is a very weak password. Leave the connectivity limit box defaulted and then hit "Apply" in the lower right. ([http://imageshack.us/a/img59/2025/newsecurityaccount.jpg Image])
# You'll see the account show up in the left above root. Select it and then click the "Administrative Roles" tab.
# Ensure that the "MonitorAdmin", "DBManager", "DBDesigner" and "BackupAdmin" are checked. Some of these will select themselves based on what you click. Then click "Apply". As a note, this step isn't entirely necessary but provides increased security. The simpler step is to just give the user all privileges by clicking the "DBA" option at the top. ([http://imageshack.us/a/img266/5876/useradministrativeroles.png Image]) 
# Click the "Schema Privileges" tab.
# In this tab, click "ragnarok" and then click the only available button, which is "Add Entry...".
# Leave "Any Host" selected and change Schema to "Selected Schemas". Then select the "ragnarok" schema and hit OK.
# At the bottom, hit "Select 'ALL'" to enable all database privileges for this Schema. This allows your ''ragnarok'' user to have access to all the tables in the schema of the same name. In other words, it allows your server to read/write the tables in the database you made. Make sure you click "Save Changes".
# Do the same for the "log" schema you made. When you are [http://imageshack.us/a/img89/1509/userschemaprivileges.jpg done it should look like this].
<br />
'''Congratulations!''' You have successful installed the MySQL database and are ready to run your server! See below for further adjustments.

==== Additional Configurations ====
===== Enabling Logging =====
Simply open logs.conf in your conf folder, and look for:
 // Use MySQL Logs? (SQL Version Only)
 sql_logs: 0
Change 0 to 1. You can also go through and change logging options. Your logs will be stored within your log schema. To view IPs in loginlog, you must click it, then right click it and choose alter table, then click on the columns tab. For the PK row, check all of the boxes, then apply it. Now you can double click on the loginlog and view the IPs, though after you are done alter the table again and uncheck all the boxes, this helps insure security. This should only be done for IP bans.

===== Increasing Security =====
'''Use MD5 to encrypt your password'''<br />
** '''WARNING:''' This will turn your passwords gibberish, just numbers and letters, making them unreadable so be sure to note down your password, either in a text file on your C drive, or on a piece of paper. In MySQL Workbench, click edit, then preferences, then click the SQL Queries tab. Uncheck "(Safe Updates) Forbid UPDATE and DELETE statements without a WHERE clause...", then click OK. Make ragnarok your default schema, by right clicking its name and clicking "Set as Default Schema", now click File, then Open SQL script, and open convert_passwords.sql. Then click the execute icon.

== Linux ==
To Install the Mysql Server there is really only a few things that you have to do.

=== Installing MySQL ===
From your terminal, type
 sudo yum install mysql-server*
- OR -
 sudo apt-get install mysql-server

After your Operating System downloaded and installed MySQL, you will see your terminal window changed and you will be prompted to provide the root password for the MySQL server

=== Setting up your own user ===
Once the server has been installed you will need to call the server from terminal with this command.
 mysql -u root
or
 mysql -u root -p
then, type in your password.

You are now logged into the MySQL server as root. The best way to use your own SQL server is to have a username of your own control with your own password. The next command will create your own user. The <code>IDENTIFIED BY</code> clause defines the password.
 CREATE USER 'ragnarok'@'%' IDENTIFIED BY 'ragnarok';
 GRANT ALL PRIVILEGES ON 'ragnarok'.* to 'ragnarok'@'%' IDENTIFIED BY 'ragnarok';
 flush privileges;

If that doesn't work it my be due to a version syntax error, try the following. 

<pre>
  CREATE USER 'ragnarok'@'%' IDENTIFIED BY 'ragnarok';
  GRANT ALL PRIVILEGES ON ragnarok.* to 'ragnarok'@'%' IDENTIFIED BY 'ragnarok';
</pre>

=== Installing the Tables ===

<pre>
  cd /path/to/Hercules/
</pre>

Note: Afterwards issue this command lines, please have your password prepared since every after command lines issued you will be prompted for it.

# Change directory to the '''sql-files''' folder.
#: <pre>cd sql-files/</pre>
# Execute these commands: 
#: ''When prompted, enter your MySQL root password.''
#: <pre>mysql -u root -prootpassword hercuser_rodb < main.sql</pre>
#: <pre>mysql -u root -prootpassword hercuser_rodblog < logs.sql</pre>
# If your Control Panel software or website requires it, you may also import the item, monster and monster skill databases (not necessary for the correct operation of Hercules)
#: (pre-renewal)
#: <pre>mysql -u root -prootpassword hercuser_rodb < item_db.sql</pre>
#: <pre>mysql -u root -prootpassword hercuser_rodb < mob_db.sql</pre>
#: <pre>mysql -u root -prootpassword hercuser_rodb < mob_skill_db.sql</pre>
#: (renewal)
#: <pre>mysql -u root -prootpassword hercuser_rodb < item_db_re.sql</pre>
#: <pre>mysql -u root -prootpassword hercuser_rodb < mob_db_re.sql</pre>
#: <pre>mysql -u root -prootpassword hercuser_rodb < mob_skill_db_re.sql</pre>
#: (common to renewal and pre-renewal)
#: <pre>mysql -u root -prootpassword hercuser_rodb < item_db2.sql</pre>
#: <pre>mysql -u root -prootpassword hercuser_rodb < mob_db2.sql</pre>
#: <pre>mysql -u root -prootpassword hercuser_rodb < mob_skill_db2.sql</pre>

NOTE: if you want to use different SQL DBs for login/char/map servers this is the list of databases each server use:
#login-server: global_acc_reg_num_db, global_acc_reg_str_db, ipbanlist, login, loginlog
#map-server: autotrade_data, autotrade_merchants, mapreg, npc_market_data
#char-server: everything else
Note that the sql_updates table is needed by all three servers.

[[Category:Installation]]