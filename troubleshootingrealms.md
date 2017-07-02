#Troubleshooting realms

## Crashing
Symptoms: the realm resets unexpectedly. Players inside are kicked out to The Outer Realm without warning.
A crashing realm is one that terminates its virtual machine even though the game isn't over. Realms that crash are automatically restarted.

## Stuck
_Symptoms: the realm stops responding, and several seconds later it resets. Players inside are kicked out to The Outer Realm without warning._
A realm will be condemned if it gets stuck in a loop, consuming CPU cycles without responding to the server's commands. It will be restarted the first two times, then condemned on the third failure. Condemned realms cannot be entered or edited, and may only be restored by an admin (User:Vaporware).

## Broken
_Symptoms: the realm can't be entered because something "failed mysteriously"._
A broken realm is one that responds to the server, but doesn't respond correctly.
This could happen because of an introduction scene where the game asks questions like "Do you need instructions?" that the server is unprepared to answer.
Or because of menus or some other strange input mode.
Or because you accidentally replaced some of the important rules from Guncho's library.

## How to find the problem

### Trace messages
One way to find the place in your code that's causing trouble is to put in some announcements before or after various important lines. For example:
```
announce "{Running the foo rules}";
follow the foo rulebook;
```
Then teleport into the realm and watch the messages go by. The ones you don't see tell you which part of the code is failing.

### Inform debugging verbs
You can turn on the Inform debugging verbs for your realm like so:
```
Include (- Constant DEBUG; -) after "Definitions.i6t".
```
* TREE
* SHOWME <object>
* RULES
* ACTIONS
* PURLOIN <object>
* ABSTRACT <object> TO <place>
* GONEAR <object>
* TRACE <number>