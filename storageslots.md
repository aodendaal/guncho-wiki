# Storage slots
__Storage slots__ let realms save data in a persistent form, to prevent it from being lost when the realm is edited or when the server restarts. A slot consists of a name and a value, which are both text. Each realm has its own set of storage slots, which can include both realm slots and player slots.

## Realm slots
```
let the high scorer's name be realm storage slot "high_scorer";
change realm storage slot "high_scorer" to "vaporware";
```
These phrases access the slots that are associated with the realm itself, not any player. If a slot has not been created yet, any attempt to read it will return an empty string.
Since realm storage slots contain text, if you're using a slot to store numbers, you may need to convert its value back to a number:
```
let the high score be the numeric value of realm storage slot "high_score";
```

## Player slots
```
let the personal best be player storage slot "best_score" of the player;
change player storage slot "best_score" of the player to "[current score of the player]";
```
These phrases access the slots for particular players. Note that these are actually per-player-per-realm slots: the data stored by a particular realm is only visible to the same realm. As with the realm slots, reading a nonexistent player slot will return an empty string.

## Saving and restoring state: the realm shutdown rulebook

The "realm shutdown" rulebook allows a realm to react when it's about to be shut down, giving it a chance to save the game state into storage slots. This could happen because the realm has been edited and is about to be restarted, or because the Guncho server is shutting down. The game state can then be restored by a "when play begins" rule the next time the realm starts.
The "entrance path" phrases can be used to save the location of an object. An entrance path translates an object's position into a string describing a series of movements from the closest entrance, which means the path stays valid even when rooms have been renamed or objects have been rearranged in the realm source code (although changing the map layout or renaming a container/supporter can still break the path).
For example, to save the locations of two objects:
```
A realm shutdown rule:
    change realm storage slot "robot" to "[entrance path to the robot]";
    change realm storage slot "hammer" to "[entrance path to the hammer]".

When play begins:
    return the robot via slot "robot";
    return the hammer via slot "hammer".

To return (X - an object) via slot (Y - text):
    let P be realm storage slot Y;
    if P is not "", move X along entrance path P.
```