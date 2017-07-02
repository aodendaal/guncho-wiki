# Player attributes
__Player attributes__ are named bits of information about particular players. Some attributes are used internally; the ones listed below are meant for public use.
```
[ To read... ]
let val be player attribute "name" of a connected PC;
```
If an attribute is not present, attempts to read it will return an empty string ("").
* __accesslevel__: Gets the level of freedom that the player has to play or modify the current realm. See access levels for a list of possible values.
* __description__: Gets the customized description that the player has set in their profile.
* __gender__: Gets the gender that the player has set in their profile: "m" for male, "f" for female, or "n" for neuter.
* __idletime__: Gets the length of time since the player last typed a command, in the same format used by the who command: for example, "01m05s", "02h30m", or "01d12h".