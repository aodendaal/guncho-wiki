# Multiple player objects
Although Inform 7 is designed to have only a single player at a time, its support for NPCs is robust enough that multiple player objects work almost seamlessly in Guncho.

## Action reporting

The built-in actions have NPC report rules, as described in the I7 manual (12.13, Report rules for actions by other people). Guncho automatically runs the PC and NPC report rules as many times as necessary, sending their output to each player who observes an action.
Therefore, if you define new actions, the easiest way to make them look right is to make sure you write report rules like "Report dancing" (for the person doing the action) as well as "Report someone dancing" (for everyone who sees the action happen). This is good practice in I7 anyway if you plan to have NPCs in your game.
Note: report rules should always use "say" to print, not "tell". The text will automatically be sent to the players who need to see it.

## The PC kind

All players belong to a kind called "PC", which is a kind of person. Every PC has an indexed text property called mud-name which stores the name of the player who's controlling it.
Each realm has a fixed number of PCs -- 25 by default. When they're not in use, these PCs are stored in a container called the PC-corral. The adjectives connected and disconnected can be used to check whether a PC is in use. For example, you could check the number of connected players with code like:
```
... the number of connected PCs ...
if at least two PCs are connected, ...
```
If all the PCs in a realm are connected, that realm is full and no one else can enter.

## Players joining and leaving

The player joining and player leaving rulebooks can be used to react when players enter or leave the realm. In your code for these rules, use "the current PC" to refer to whoever's joining or leaving.
For example, you may wish to stop real-time events when the last player disconnects, and start them when a player connects again. Note that the current PC is already connected when your player joining rules run, and still connected when your player leaving rules run. To check whether the PC who's disconnecting is the last one, use code like this:
```
A player leaving rule: if exactly one PC is connected, stop real-time events.
```

## "Say" vs. "tell"

I7's "say" phrase does what you'd expect during action processing rules: it sends text to whoever's performing the action, or in the case of NPC report rules, to whoever's observing the action.
Outside of the action processing rules, however, "say" has no effect, and any text you print with it will be thrown away. For example, in a real-time event rule, you need to use one of the "tell" phrases to tell Guncho exactly which players you want to send the text to.

## Winning and losing

When a game-ending command is executed, whether winning or losing, every player in the realm receives the death or victory message and is sent back to The Outer Realm. The realm is then restarted.
By default, "cooperative" scoring is used, where wins and losses count equally for everyone in the realm: if anyone wins, you all win. This is appropriate for realms with a goal that all players must work together to complete. For realms where players are competing, put the line "Use competitive scoring." at the top, which will cause wins and losses to only count for the one player who wins or loses.

## Killing individual players

Instead of winning or losing an entire game, your realm may well need to be more persistent and allow for the killing off of individual players while letting the rest carry on playing.
Doing this is very simple. Here's the code from MUD2.5 that I use to kill off a player:
```
if <death condition>:
     have the player die.

To have the player die:
     say "You are dead!";
     update the persona for the player;
     send the player to "woods@The Outer Realm".
```
Simply replace the location that you want your players sent to when they die (maybe someone could set up a 'limbo' or 'heaven' realm?). "update the persona" is a routine which saves the player's stats and isn't included here.