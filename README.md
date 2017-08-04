Baseball GDT Bot by Matt Bullock
=====================================

### Current Version: 3.0.2
	
The point of this project is to create a bot that will generate a
	game discussion thread that contains live linescore and boxscore,
	post it in the correct subreddit for that team, and keep it
	updated throughout the game.
	
Version 1.0 was written in a mix of Python and Java, and has been
	completely ported to Python for v2.0 and v3.0 (this version).

---

### Set Up OAuth

Go to reddit.com’s app page, click on the “are you a developer? create an app” button. Fill out the name, description and about url. Name must be filled out, but the rest doesn’t. Write whatever you please. For redirect uri set it to `http://127.0.0.1:65010/authorize_callback`. All four variables can be changed later.

Next, open setup.py, fill in the client_id, client_secret and redirect_uri fields and run the script. Your browser will open. Click allow on the displayed web page. 

Enter the uniqueKey&code from the URL into the console -- wrapped in single quotes -- and the access information will be printed. This includes the final bit of info you need, the refresh token.

Finally, Copy sample_settings.json to the src folder and rename it to settings.json. Fill in the CLIENT_ID, CLIENT_SECRET, REDIRECT_URI and REFRESH_TOKEN fields in the settings.json file and save. 

### Configuration

To use the default settings, copy `sample_settings.json` into `src/settings.json`.

#### Descriptions of Settings

* `BOT_TIME_ZONE` - time zone of the computer running the bot, uncomment the line that you want to use

* `TIME_ZONE` - time zone of the team. uncomment the line that you want to use

* `POST_TIME` - bot posts the thread POST_TIME hours before the game

* `SUBREDDIT` - subreddit that you want the threads posted to

* `TEAM_CODE` - three letter code that represents team, look this up

* `PREGAME_THREAD` - do you want a pre game thread?

* `POST_GAME_THREAD` - do you want a post game thread?

* `SUGGESTED_SORT` - what do you want the suggested sort to be? ("confidence", "top", "new", "controversial", "old", "random", "qa", "")

* `STICKY` - do you want the thread stickied? (mod only)

* `MESSAGE` - send submission shortlink to /u/baseballbot

* `PRE_THREAD_SETTINGS` - what to include in the pregame threads

* `THREAD_SETTINGS` - what to include in game threads

* `POST_THREAD_SETTINGS` - what to include in postgame threads
	
---	

If something doesn't seem right, feel free to message me or post it as a bug here.
	
This was written in Python 2.7, so beware if you are running Python 3 or
	above that it may not work correctly. Also make sure you install
	praw and simplejson before running!
	
Modules being used:

	praw - interfacing reddit
	simplejson - JSON parsing
	urllib2 - pulling data from MLB servers
	ElementTree - XML parsing

### Updates

#### v3.0.2
* GUI added. 

#### v3.0.1
* Now uses OAuth!

#### v3.0.0
* Modular - If you want a certain feature, just change a variable at the top!
* Easier to read - Cleaned up some code, started using more OOP.

#### v2.0.4
* Fixed crash caused by game not being aired on TV.
* Fixed another crash related to scoring plays.

#### v2.0.3
* Fixed the Diamondbacks' subreddit not working properly.
* Fixed crash related to scoring plays.

#### v2.0.2

* Fixed random crashing.
* Fixed bug where some teams names were not displayed correctly. (Though Chi White Sox White Sox is a great name...)

#### v2.0.1

* Fixed gamecheck not always working correctly.
* Fixed the TV media showing the same for both home and away.
* Fixed the timestamp on the game/time checks not displaying correctly.
