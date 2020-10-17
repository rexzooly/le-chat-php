Installation Instructions:	Installation Instructions:
--------------------------	--------------------------


You'll need to have php with pdo, pcre, mbstring and date extension and a web-server installed.	You'll need to have php with pdo, pcre, mbstring and date extension, and a web-server installed.
You will also need the pdo_sqlite, pdo_mysql or pdo_pgsql extension, depending on which database you choose.	You will also need the pdo_sqlite, pdo_mysql or pdo_pgsql extension, depending on which database you choose.
Optionally, you can install:	Optionally, you can install:
- the gd extension for the captcha feature	- the gd extension for the captcha feature
- the json extension for save/restore	- the json extension for save/restore
- a memcached server and the memcached extension and change the configuaration to use memcached. This will lessen the database load a bit.	- a memcached server and the memcached extension and change the configuration to use memcached. This will lessen the database load a bit.
- a MySQL or PostgreSQL server to use as an external database instead of SQLite	- a MySQL or PostgreSQL server to use as an external database instead of SQLite
- the libsodium extension (PHP >= 7.2) for encryption of messages and notes in the database	- the libsodium extension (PHP >= 7.2) for encryption of messages and notes in the database
When you have everything installed and use MySQL or PostgreSQL, you'll have to create a database and a user for the chat.	When you have everything installed and use MySQL or PostgreSQL, you'll have to create a database and a user for the chat.
@@ -52,19 +52,19 @@ Then copy the script to your web-server directory and call the script in your br
	http://(server)/(script-name).php?action=setup		http://(server)/(script-name).php?action=setup
Now you can create the Superadmin account. With this account you can administer the chat and add new members and set the guest access.	Now you can create the Superadmin account. With this account you can administer the chat and add new members and set the guest access.
As soon as you are done with the setup, all necessary database tables will be created and the chat can be used.	As soon as you are done with the setup, all necessary database tables will be created and the chat can be used.
Note: If you updated the script, please visit http://(server)/(script-name).php?action=setup again, to make sure, that any database changes are applied and no errors occure.	Note: If you updated the script, please visit http://(server)/(script-name).php?action=setup again, to make sure, that any database changes are applied and no errors occur.


Translating:	Translating:
------------	------------


Copy lang_en.php and rename it to lang_YOUR_LANGCODE.php	Copy `lang_en.php` and rename it to `lang_YOUR_LANGCODE.php`
Then edit the file and translate the messages into your language and change $I to $T at the top.	Then edit the file and translate the messages into your language and change `$I` to `$T` at the top.
If you ever use a `'` character, you have to escape it by using `\'` instead or the script will fail.	If you ever use a `'` character, you have to escape it by using `\'` instead or the script will fail.
When you are done, you have to edit the chat script, to include your translation. Simply add a line with	When you are done, you have to edit the chat script, to include your translation. Simply add a line with
		'lang_code'	=>'Language name',	`'lang_code'	=>'Language name',`
to the $L array in the load_lang() function at the bottom, similar to what I did for the German translation.	to the `$L` array in the load_lang() function at the bottom, similar to what I did for the German translation.
Please share your translation with me, so I can add it to the official version.	Please share your translation with me, so I can add it to the official version.
To update your translation, you can copy each new string to your translation file or edit the automated lang_update.php script to reflect you language and run it.	To update your translation, you can copy each new string to your translation file or edit the automated `lang_update.php` script to reflect you language and run it.


Regex:	Regex:
------	------
@@ -83,5 +83,5 @@ If you never used regex before, check out [this starting guide](http://docs.acti
Live demo:	Live demo:
----------	----------


If you want to see the script in action, you can visit my [Tor hidden service](http://danschat356lctri3zavzh6fbxg2a7lo6z3etgkctzzpspewu7zdsaqd.onion/chat.php) or via a tor2web proxy like [this one](https://chat.danwin1210.me/chat.php) if you don't have Tor installed.	If you want to see the script in action, you can visit my [Tor hidden service](http://danschat356lctri3zavzh6fbxg2a7lo6z3etgkctzzpspewu7zdsaqd.onion/chat.php) or via [my clearnet proxy](https://chat.danwin1210.me/chat.php) if you don't have Tor installed.
Considering this is a hidden service, you should be prepared for the worst case, as people tend to do illegal activities in the Tor network.
