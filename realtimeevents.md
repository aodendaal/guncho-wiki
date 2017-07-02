# Real-time events
__Real-time events__ let you schedule to happen in your realm at a regular pace, no matter how many players are connected or how quickly they're typing commands.
Real-time events work by triggering a special rulebook periodically. They are off by default, but you can freely turn them on and off in your realm and change the length of time between events.

## How to use real-time events

* __request real-time events every _N_ seconds__
This phrase turns real-time events on and sets the interval between events to the given number of seconds. Note that the interval is only accurate to about ± 1.25 seconds, and cannot be set lower than 3 seconds.
If you want to use the same event interval for the entire time your game is running, set it in a "when play begins" rule:
```
When play begins, request real-time events every 30 seconds.
```

* __stop real-time events__
This phrase turns real-time events off.
If you only want real-time events to happen while players are connected to your realm, [use player joining and leaving]() rules to turn them on when the first player joins and off when the last player leaves:
```
A player joining rule: if exactly one PC is connected, request real-time events every 30 seconds.
A player leaving rule: if exactly one PC is connected, stop real-time events.
```

* __A real-time event rule: _do whatever___
This is how you put your code into the real-time event rulebook. Every time your chosen event interval passes, the entire real-time event rulebook will run.
If you have events that need to run on different schedules (e.g., if your event interval is 30 seconds but you want something to happen every 5 minutes), you can either use a variable to count the number of real-time events that have happened, or check the [server clock](serverregisters.md) and keep track of what time the next event should happen.

## When to use real-time events

Generally, real-time events should be used instead of "every turn" rules for controlling NPC behavior. Otherwise, the NPCs will speed up and slow down depending on how many players are in the realm and how quickly they're typing.

## When not to use real-time events

Real-time events should usually be avoided for making general rules about player behavior or abilities, for example making players periodically drop heavy objects when they're carrying too many. Players who type faster will have a serious advantage in such cases.
There are alternatives to using real-time events for NPC behavior as well. For example, for "flavor text" that just describes what an NPC is doing at the moment, you might choose to use an "every turn" rule that describes the NPC's behavior to the player who acted (but not to anyone else who's nearby).

## Pitfalls

Real-time events take place outside of any player action, which means some code that works in an action rule won't work in a real-time event rule:
* "Say" phrases used within real-time events will not be seen by anyone. Use "tell" or "announce" instead.
* I7's normal "end the game" phrases will not work within a real-time event. If you need to end the game from within a real-time event, you will have to use a custom phrase that calls a little I6 code. First do an "announce" with whatever game won/lost text you need, then use your custom phrase, for example "stop game abruptly", which needs to be defined like so:
```
To stop game abruptly: (- quit; -).
```