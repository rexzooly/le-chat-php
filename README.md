The Cat PHP - General Information:
--------------------
[![Original](https://img.shields.io/badge/Forked-LE--CHAT--PHP-green)](https://github.com/DanWin/le-chat-php/)<br/>
This script is a fork of **LE CHAT PHP** by **DanWin** An up-to-date copy of his script can be found here https://github.com/DanWin/le-chat-php
<br/>
<br/>
[![Fork](https://img.shields.io/badge/Based-Fork-green)](#) DanWin Le Chat PHP 1.24.1<br/>
<br/>
[![Original](https://img.shields.io/badge/Original-LE--CHAT-green)](https://4fvfamdpoulu2nms.onion.to/lechat/)<br/>
The original perl **LE CHAT** script by **Lucky Eddie** can be found at [![History](https://img.shields.io/badge/Onion-green?logo=tor)](http://4fvfamdpoulu2nms.onion/lechat/) [his site](http://4fvfamdpoulu2nms.onion/lechat/) or via a tor2web proxy like [this one](https://4fvfamdpoulu2nms.onion.to/lechat/) if you don't have Tor installed.
<br/>
<br/>
![Please Note:](https://img.shields.io/badge/Note-Warning-red?logo=AdBlock)<br/>
Please use the **Tor** links with care, people are able to do illegal activities within the **Tor** network, we are not hold responsible for their's/your actions, please use with care. Also Note: **Tor** is not the most stable or fast so these links might be slow or down at any given time.
<br/>
<br/>
[![Tipbit](https://img.shields.io/badge/Tipbit-LE-informational)](#)<br/>
Now a piece of information about the origin of the name **"LE CHAT"** copied from the original script:
The **"LE"** in the name you can take as  **"Lucky Eddie"**, or since the script was meant to be lean and easy on server resources, as **"Light Edition"**.
It may even be the French word for **"the"** if you prefer. Translated from *French* to *English*, **"le chat"** means: **"the cat"**.
<br/>
<br/>

Key Features:
---------

* ![[**Onion**:]](https://img.shields.io/badge/Onion:-green?logo=tor&logoColor=white) Optimized for Tor
* ![[**JS**:]](https://img.shields.io/badge/JS:-green?logo=JavaScript&logoColor=white) No JavaScript needed
* ![[**Cookies**:]](https://img.shields.io/badge/Cookies:-green) Supported, but not needed
* ![[**Stop Bots**:]](https://img.shields.io/badge/Stop%20Bots:-green) Captcha
* ![[**Language**:]](https://img.shields.io/badge/Dialect-green?logo=Google%20Translate&logoColor=white) Multiple languages
* ![[**Users**:]](https://img.shields.io/badge/Users-green?logo=Opsgenie&logoColor=white) Staff, Members and guests
* ![[**Guests:**:]](https://img.shields.io/badge/Guests-green?logo=Google%20Classroom&logoColor=white) Waiting room for guests
* ![[**Moderatoral:**:]](https://img.shields.io/badge/AdGuard-green?logo=Mixcloud&logoColor=white) Moderatoral approval of new guests
* ![[**Chat:**:]](https://img.shields.io/badge/Chat-green?logo=ProtonMail&logoColor=white) Public, member, moderator and admin only chats
* ![[**Private:**:]](https://img.shields.io/badge/Private-green?logo=GUN%20Privacy%20Guard&logoColor=white) Private messages
* ![[**More:**:]](https://img.shields.io/badge/Writen-green?logo=Stack%20Exchange&logoColor=white) Multi-line messages
* ![[**Custom:**:]](https://img.shields.io/badge/Custom-green) Change font, colour and refresh rate in profile settings
* ![[**Inactive:**:]](https://img.shields.io/badge/Inactive-green) Autologout when inactive for some time
* ![[**Images:**:]](https://img.shields.io/badge/Images-green?logo=Imgur&logoColor=white) Image embedding
* ![[**Notes:**:]](https://img.shields.io/badge/Notes-green) Notes for admins and moderators
* ![[**Browser:**:]](https://img.shields.io/badge/FireFox-green?logo=FireFox&logoColor=white) Clone the chat to have multiple tabs
* ![[**Kick:**:]](https://img.shields.io/badge/Kick-green?logo=AdBlock&logoColor=white) Kick chatters
* ![[**Clean:**:]](https://img.shields.io/badge/Clean-green) Clean selected messages or the whole room
* ![[**Filter:**:]](https://img.shields.io/badge/Filter-green) Plain text & Regex message filtering
* ![[**More:**:]](https://img.shields.io/badge/More-green) And more

Installation Instructions:
--------------------------
You'll need to have **php** with **pdo**, **pcre**, **mbstring** and **date** extension and a web-server installed.
You will also need the **pdo_sqlite**, **pdo_mysql** or **pdo_pgsql** extension, depending on which database you choose.

**Optionally**, you can install:
* The **gd** extension for the captcha feature
* The **json** extension for save/restore
* A **memcached** server and the **memcached** extension and change the configuaration to use memcached. This will lessen the database load a bit.
* A **MySQL** or **PostgreSQL** server to use as an external database instead of **SQLite**
* The **libsodium** extension needs (PHP >= 7.2) for encryption of messages and notes in the database

When you have everything installed and use MySQL or PostgreSQL, you'll have to create a database and a user for the chat.
Then edit the configuration at the bottom of the script to reflect the appropriate database settings and to modify the chat settings the way you like them.
Then copy the script to your web-server directory and call the script in your browser with a parameter like this:
	http://(server)/(script-name).php?action=setup
Now you can create the Superadmin account. With this account you can administer the chat and add new members and set the guest access.
As soon as you are done with the setup, all necessary database tables will be created and the chat can be used.
Note: If you updated the script, please visit http://(server)/(script-name).php?action=setup again, to make sure, that any database changes are applied and no errors occure.
<br/>
<br/>

Translating:
------------

Copy **lang_en.php** and rename it to **lang_YOUR_LANGCODE**.php
Then edit the file and translate the messages into your language and change **$I** to **$T** at the top.
If you ever use a **`'`** character, you have to escape it by using **`\'`** instead or the script will fail.
When you are done, you have to edit the chat script, to include your translation. Simply add a line with
```php
'lang_code' => 'Language name'
```
to the **$L** array in the **load_lang()** function at the bottom, similar to what I did for the German translation.
Please share your translation with me, so I can add it to the official version.
To update your translation, you can copy each new string to your translation file or edit the automated **lang_update.php** script to reflect you language and run it.
<br/>
<br/>

Regex:
------

Yes, the chat supports regular expression filtering of messages. As regex tends to be difficult for most people, I decided to give it an extra section here.
Regex is very powerful and can be used to filter messages that contain certain expressions and replace them with something else.
It can be used e.g. to turn BB Code into html, so it is possible to use BB Code in the chat to format messages.
To do this, use this Regex-Match `\[(u|b)\](.*?)\[\/\1\]` and this Regex-Replace `<$1>$2</$1>` and your text will be `[b]bold[/b]` or `[u]underlined[/u]`.
You can also use smilies by using this Regex-Match `(?-i::(cry|eek|lol|sad|smile|surprised|wink):)` and this Regex-Replace `<img src="/pictures/$1.gif" alt=":$1:">`
And now if you enter `:smile:` an image with the smiley will be loaded from your server at `/pictures/smile.gif`.
The following should be escaped by putting `\` in front of it, if you are trying to match one of these characters `/ \ ^ . $ | ( ) [ ] * + ? { } ,`.
I used `/` as delimiter, so you will have to escape that, too. The only options I used is `i` to make the regex case insensitive.
If you want to test your regex, before applying you can use [this site](http://www.phpliveregex.com/) and enter your Regex and Replacement there and click on preg_replace.
If you never used regex before, check out [this starting guide](http://docs.activestate.com/komodo/4.4/regex-intro.html) to begin with regular expressions.
<br/>
<br/>

Live demo:
----------
This live demo is not created by ***Rexzooly*** and accepts no responsibility for you using these services, the service is active so please use with care.


If you want to see the script in action, you can visit DanWin's [Tor hidden service](http://danschat356lctri3zavzh6fbxg2a7lo6z3etgkctzzpspewu7zdsaqd.onion/chat.php) or via his own tor2web proxy [DanWin Clean Web](https://chat.danwin1210.me/chat.php) if you don't have Tor installed.


![Please Note](https://img.shields.io/badge/Note-Warning-red?logo=AdBlock)
Considering this is a hidden service, you should be prepared for the worst case, as people are able to do illegal activities within the Tor network, we are not hold responsible for their's/your actions, please use with care.
