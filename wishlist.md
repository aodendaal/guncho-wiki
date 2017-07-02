# Wish list

## Realm Code

tell [text] to everyone in the [location/region]. --Matthius
Ability to customise the message given when another player enters or leaves the location. --PaulDV 15:20, 5 September 2008 (UTC)
Ability to print a pre-amble when a player enters the world before the first room description is printed. --PaulDV 16:00, 27 August 2008 (UTC)
Write a player joinging rule to do this. --Peskie 01:46, 8 May 2009 (UTC)
Alternatives to the ', except the actor' option on the tell phrase so that we can specify who not to tell. e.g. tell "[The noun] has woken up." to everyone who can see the noun, except the noun. This would allow the reporting of something happening to a person to everyone who can see that person, leaving out the person themselves.
Try "tell [msg] to everyone else near [person]" --Vaporware
Achievements and gunchopoints for each realm
Show a message like "Vapsy appears, victorious from Closet" when kicking winning/losing players back to the outer realm
Let realms choose where to send the players (winners and losers separately?)
Generally, give more control over the messages that appear when sending players away
Hierarchical realms
A "realm leader" who has access to all the source in a given hierarchy
Sub-realm chapters: Each player owns a chapter, it's all compiled into a single realm when one chapter is edited
Let realms edit their own source, by printing text to be inserted at a marked point in the file, e.g. for link hubs
This seems like a very bad idea to me. Note link hubs can be done without this, the send the player to ... phrase takes a string which be generated at run-time. --Peskie 01:46, 8 May 2009 (UTC)
A realm setting for debug mode (so >actions and >rules will work)
Include (- Constant DEBUG; -) after "Definitions.i6t". accomplishes this. --Peskie 01:46, 8 May 2009 (UTC)
Timed real-time events ("the bridge collapses in 5 ticks from now")
Make it easier to define PC roles as objects instead of global variables
Compatible extensions installed on Guncho so that "Include" phrases work instead of having to paste in extension code.
Would need to be careful when updating installed extensions so as to not break realms. But since realms are manually re-compiled perhaps this isn't a big issue.
Realms are recompiled automatically once in a while, so version compatibility is something to watch out for. Add to the list of compatible extensions and I'll install the ones that are known to work. --Vaporware
Let users upload their own extensions
I second this. I'm working on a bunch of little improvements that would be be implemented as a series of Guncho specific extensions that any realm could include. --Peskie 01:46, 8 May 2009 (UTC)
Put a basic "help" command in the library, so lost players can find their way back
A server register that returns the date and time as seconds since a defined epoch ala time(3) on Posix/UNIX. --Peskie 01:46, 8 May 2009 (UTC)
A player attribute that returns the connect time of the player as shown in the who command. --Peskie 04:58, 18 May 2009 (UTC)

## Crossing Realms

Items specially marked can be carried among specified realms
Each realm has its own VM instance, so objects can't actually be moved between them. They'd have to be defined in every realm and tied together somehow.
Method to send messages between realms
A realm that needs more players can ask the robot to guide people there
Bots running in their own VMs and interacting with realms, able to move between realms like a player
Possibly reading text and sending commands like a player, or possibly exchanging messages as I7 actions
Exchanging messages is probably faster and leads to more natural, less redundant code, but may expose too much about realm internals to an untrusted bot

## Control Panel and Editing Interface

Ability to duplicate a realm so as to modify it
Ability to perform diffs of modified realms and merge back into parent
Make the realm editing experience more like I7 IDE
Word wrapping
Show the index in another frame or panel
Make the source links in compiler errors jump to the right line
Make source links in the index work too
Player signup should request an email address for password recovery.
Keep a log for each realm, visible to the owner, showing when it was restarted and why
Include "say" output that wasn't directed to any player, including error messages from the realm (runtime problems), and terp exceptions with stack trace
Keep past revisions of realms so changes can be reverted (necessary for publicly editable realms)
Diffs between revisions a la wiki
Ability to upload cover art and make Inform's "published" source text visible to the public
Allow players to be combined into groups, and ACL entries to be set per-group?
Allow Invited access to be given to other realms in addition to specific players. This would allow for a Hidden or Visible realm to only be accessible via link(s) from the named realms.
Make saving not cause the editing box to automatically revert to source highlighting
Have an 'Upload' button that allows you to upload a complete source file from your PC, replacing any existing code in the editor. This saves having to cut and paste changes made offline for those who prefer to edit within the Inform 7 IDE. --PaulDV 13:12, 13 August 2008 (UTC)
I second this. I'd love a way to update my realm(s) from my own command line.
Per-account setting to always use the plain editor (e.g. for screen readers)
On the list of realms separate out the "Other Realms" section with those that can be teleported to ("Realms You Can Visit"?) and those that can't (e.g. "Visible" vs "Invited" access).

## Layout

Automatic line breaks before the printing of room name+room description, to make that text more readable when moving into a new room, etc.
Translate Inform text attributes to ANSI colors?
Pueblo support

## Communication

Global chat
Channels
Realm chat (heard by anyone in the realm)
Global chat channel available for anyone to talk to everyone else connected, no matter what realm they're in. Also, a way for realms to disable this channel. It should be made clear that this global chat channel is an out-of-character, out-of-realm, out-of-world, etc. chat channel. Shouldn't be used for realm-specific chat.
A way to turn off sending pages from inside certain realms (to discourage collusion)
Also a way for games to hide idle time from the "who" listing (e.g. for Werewolf where it can be advantageous to know who hasn't moved yet)
Can we have a forum associated with the guncho.com site (forum.guncho.com perhaps?) so that we can discuss things properly and post questions/problems and hints and tips as necessary? I know there's a Guncho channel in ifMUD but having something permanent for all to see (and contribute to) would be a great help. This would also be a good driver for the wiki as people could add to the wiki once common problems/misunderstandings become apparent. Thanks.
How about discussions in-wiki? There's Talk about Guncho and the community portal. I'm not deep enough into wiki culture to know the best way to facilitate discussions here, but I'd rather not set up yet another web site until the level of traffic really demands it. (There's also rec.arts.int-fiction.) --Vaporware
I must confess to being new to the ways of wiki as well, so I'm not too sure how good a medium this is with regards to emulating a forum. Certainly posting (and formatting) requires some knowledge, and it's quite easy for someone to mess things up inadvertantly, so I feel a simple forum would be a better vehicle for discussions, with the wiki being more of a manual-cum-howto-cum-knowledge-base - just my opinion. Likewise, raif is great for general discussion, but it's primarily a newsgroup which, again, I feel is not as good a medium as a forum which can be split in to subject areas. But I'll go with what we've got for now and see how it pans out.
There is now a forum. --Vaporware
"saymode" - the ability to see your own chat in the third person

## Misc

Implement real-time events processing within the Guncho Mockup extension. It would be great to be able to test real-time events off-line. --PaulDV 13:18, 13 August 2008 (UTC)
Give Guncho Real-time Mockup by Dave Chapeskie a try. --Peskie 02:54, 8 May 2009 (UTC)
(Discussion on this moved to Peskie's talk page) --Peskie 19:06, 8 May 2009 (UTC)
IF Whispers support (ideas to come later, I guess)
A realm "intro" page where imps can submit artwork and have some sort of teaser text to give people an idea of what the realm is about.
For 'in-game' text use a player joining rule. For images or more information make a wiki page for your realm in the realms category. --Peskie 03:02, 8 May 2009 (UTC)
Make control panel login work with Firefox stored passwords. Somehow the currently page defeats Firefox's ability to recognize the form as a login form and offer to remember the password.
I believe I was the one that requested this ages ago. With Firefox 3.x this is no longer an issue. -- Peskie 05:12, 15 April 2009 (UTC)
Support other IF languages. Inform 6 is a likely candidate.
Open source the server so that others can run their own. --morbus@disobey.com
Not likely to happen anytime soon for various reasons, one of which is that the Glulx interpreter used in Guncho is a commercial product.
Hrm. Perhaps instructions, then, on how to purchase and then setup your own? --morbus@disobey.com
This would be cool. Also, it would incentive people into finding an OSS alternative to FyreVM and replace FyreVM with it...
So, FyreVM's source has been made public with no license. How about now? --morbus@disobey.com
As I said, the FyreVM licensing situation was only one of the reasons. I will consider it, but don't hold your breath. (Also, FyreVM is still subject to a license, which is described in the "COPYRIGHT" file in the repository - the only public domain part is the sample application.) --Vaporware
A player option to use ASCII or Latin-1 encoding instead of UTF-8?
Support for telnet-ssl
https on the website (at least in auth)