# RebornBuddy

## Regarding Installation:

The GitHub is structured exactly as it should be inside your RebornBuddy Folder.

###### Want Artemis?
Make a folder called Artemis in your BotBases folder, and SVN Checkout to 
https://github.com/sodimm/RebornBuddy/trunk/BotBases/Artemis

###### Want Cyril?
Make a folder called Cyril in your Plugins folder, and SVN Checkout to
https://github.com/sodimm/RebornBuddy/trunk/Plugins/Cyril

###### Want Sparrow?
Make a folder called Sparrow in your Plugins folder, and SVN Checkout to
https://github.com/sodimm/RebornBuddy/trunk/Plugins/Sparrow

###### Want the Behaviors?
Make a folder called Sodimm in your Plugins folder, and SVN Checkout to
https://github.com/sodimm/RebornBuddy/trunk/Plugins/Sodimm

###### Want the Profiles?
Make a folder called Sodimm in your Profiles folder, and SVN Checkout to
https://github.com/sodimm/RebornBuddy/trunk/Profiles

The Alternative to multiple checkouts, is to download or checkout the entire repo, and manually move them yourself. But if you're unsure as to where things go, just navigate to the GitHub Page. It's layout is exaclty as it should be in your local folder.
If done correctly, a simple batch file will have them updated in a few seconds.

###### Batch file?
Make a new text document. Name it whatever you like. Then open it up for editing.

Make it look like this (thanks to @Nab on the HonorBuddy forums):

```

@echo off
SET A=""
FOR %%A IN (
"C:\XXXX\XXXX\XXXX\RebornBuddy\BotBases\Artemis"
"C:\XXXX\XXXX\XXXX\RebornBuddy\BotBases\ExFateBot"
"C:\XXXX\XXXX\XXXX\RebornBuddy\Plugins\Cyril"
"C:\XXXX\XXXX\XXXX\RebornBuddy\Plugins\ExBuddy"
"C:\XXXX\XXXX\XXXX\RebornBuddy\Plugins\Sodimm"
"C:\XXXX\XXXX\XXXX\RebornBuddy\Plugins\Sparrow"
"C:\XXXX\XXXX\XXXX\RebornBuddy\Profiles\Sodimm"
) DO CALL :CONCAT %%A
TortoiseProc.exe /command:update /path:"%A:"=%" /closeonend:1;
goto :eof

:CONCAT
set A=%A%%1*
goto :eof

```

Wherein the Drive and folders reflect where you have the individual checkouts. Once you're done, save and rename the file to .bat, instead of .txt. And that's it. Double click the file and it'll update all the folders (assuming you have TortoiseSvn of course).

## Notes

All my profiles (bar Ixal; for now) require the custom behaviors. 

These behaviors will work on both x86 and x64 versions of RebornBuddy.

A Realm Reborn based profiles (2.0 & Ixal Dailies) should be, for the most part. AFKable. There are some tasks that the bot has trouble with, but I am working on trying to solve them within the custom behaviors.

Heavensward based profiles (3.0 & Moogle Dailies) Require ExMatts ExBuddy to function. Please be advised that ExBuddy can get stuck, and will get stuck. This is not an issue that is easily solved, and ExMatt should be praised for his amazing work. Until official flying support is released, these profiles will continue to require ExBuddy. As such, with the intermittent issues with RayCasting the profiles should not be AFKed. For the most part, they will do their job just fine, but on the odd occasion that Exbuddy gets stuck, it will require human intervention.

Its worth noting that; Yes, I could add custom hops for the flight to be more smooth in the Heavensward profiles; yet,  without knowing the exact combination or 3 quests you're likely to get, ExFlight will still run into problems. Please be mindful when submitting bugs, that anything involving the flight is beyond my control. Also please understand that although every effort is made to ensure a good experience, there are some things RebornBuddy just can not do. Without ExMatts efforts these profiles wouldn't even exsist, please respect that.

###### What is Cyril Plugin?

Cyril is a Repair Plugin, enable and it will run to a vendor and repair when your gear gets below 5%. There is an option to self repair, but this is in testing. Cyril will only work on Autonomous BotBases i.e OrderBot or FateBot.

###### What is Sparrow Plugin?

Sparrow is a Companion plugin. Specify your Stance and Feed requirements in settings, and Sparrow will keep your companion summoned, in the correct stance, and fed your chosen feed if available. I will be adding an automatic stance selection at a later date. Please disable any UseChocobo features of your Combat Routines when using Sparrow, as this  will intefere. Sparrow will only work on Autonomous BotBases i.e OrderBot or FateBot.

###### What is Artemis?

Artemis is a Hunt Bill BotBase. Specify your marks via the UI, and amount required, and hit start, and Artemis will Hunt them down for you. Please note that Artemis does use ExBuddy, so please be mindful when submitting errors that ExFlight can and will crash from time to time. But's it's what's available, see above. The Botbase still has a few bugs, with 3 mobs omitted due to pathing issues, and it will stop, regardless of combat when the marks are complete, but these are being worked on.

Any issues, please raise Pull Requests or Issues via GIT, DM via Discord, or PM me via the Official Forum.
