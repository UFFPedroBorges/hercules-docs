== Files Converted ==
* [`db/pre-re/item_db.conf`](https://github.com/HerculesWS/Hercules/blob/stable/db/pre-re/item_db.conf) (only in pre-renewal mode)
* [`db/re/item_db.conf`](https://github.com/HerculesWS/Hercules/blob/stable/db/re/item_db.conf) (only in renewal mode)
* [`db/item_db2.conf`](https://github.com/HerculesWS/Hercules/blob/stable/db/item_db2.conf)
* [`db/pre-re/mob_db.conf`](https://github.com/HerculesWS/Hercules/blob/stable/db/pre-re/mob_db.conf) (only in pre-renewal mode)
* [`db/re/mob_db.conf`](https://github.com/HerculesWS/Hercules/blob/stable/db/re/mob_db.conf) (only in renewal mode)
* [`db/mob_db2.conf`](https://github.com/HerculesWS/Hercules/blob/stable/db/mob_db2.conf)

== Description ==
This plugin converts the item database configuration files for use with SQL servers.


== Compiling ==
The plugin needs to be compiled. If you've already compiled your server and/or other plugins, input these commands:
 ./configure
 make plugin.db2sql

=== Windows ===
In Windows, compile the '''db2sql''' plugin in Visual Studio.


== Enabling db2sql ==
Next, the plugin needs to be enabled in [`conf/plugins.conf`](https://github.com/HerculesWS/Hercules/blob/stable/conf/plugins.conf):
 plugins_list: [
 	/* Enable HPMHooking when plugins in use rely on Hooking */
 	//"HPMHooking",
 	"db2sql",
 	//"sample",
 	//"other",
 ]


== Usage ==
To use the converter, update your changes in the desired item database (using [`db/item_db2.conf`](https://github.com/HerculesWS/Hercules/blob/stable/db/item_db2.conf) for customisations is recommended); then, run this command:
 ./map-server --db2sql

=== Windows ===
In Windows, run [`db2sql.bat`](db2sql.bat) in the root directory.


== Output ==
The resulting files will be output in the [`sql-files`](https://github.com/HerculesWS/Hercules/tree/stable/sql-files) folder as [`sql-files/item_db.sql`](https://github.com/HerculesWS/Hercules/blob/stable/sql-files/item_db.sql), [`sql-files/item_db_re.sql`](https://github.com/HerculesWS/Hercules/blob/stable/sql-files/item_db_re.sql), and [`sql-files/item_db2.sql`](https://github.com/HerculesWS/Hercules/blob/stable/sql-files/item_db2.sql).


[[Category:Tools]]
