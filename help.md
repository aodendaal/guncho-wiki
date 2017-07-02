# How can I help?
__How can I help__ is a place for you to offer your services or post help requests.

## Help the Guncho project

### Application programming
* __Guncho inside I7, part 1__: The [Inform 7](inform7.md) IDE is open source software. You could modify the [IDE source code](http://www.inform-fiction.org/I7/Download.html) and add a panel that connects to Guncho. Make every I7 user a potential player instead of having to install a separate client.
* __Guncho inside I7, part 2__: Add a simple way to download, edit, test, and upload realms using the Inform 7 IDE, without pasting code in and out of a web browser.

### Inform testing
* __Extensions__: Go through the I7 extensions list, test some of them with Guncho, and make a list of compatible extensions. You can test an extension by pasting everything between the "Extension Name starts here" and "Extension Name ends here" lines (but not those two lines) into a realm, and adding some sample code at the bottom to make sure it works.

## Web site
* Refine the Guncho logo
* Create artwork for The Outer Realm or other realm pages
* Hack the fancy code editor ([EditArea](http://www.cdolivet.net/editarea/)) to provide word-wrapping

## Help with a Realm

### Player Fades In/Out
* How can I change the default message that appears when a player connects in to my realm? I would like to be able to have messages like: newbie has just come out of the lift or newbie falls through the gaping hole in the ceiling.

### MUD2.5
* I need help to find a way of tailoring the 'tell' phrase so that it checks to see if the PC it is about to send the message to can actually 'see' something. (e.g. I have a PC who is asleep and should not receive any messages about other PCs and NPCs arriving or leaving). Can you help please?

### Test
* Can anyone tell me how I can set up a class system in my game? (ex. Warrior, Mage, etc.) I also would like to know if I can make it so different classes have different permissions (ex. only warriors can go here, only mages can pick up this object.) Help will be very appreciated. Thank you PaulDV.
  * Yes, you can do this. There are many ways in which it can be done though. None of them the "right" way, but each way would have its pros and cons. I would probably have the classes in a table. Coding permissions for areas shouldn't be too much of a problem using 'before' rules and a couple of linked tables defining which rooms are class-specific. The main problem would be making the denial of access appear reasonable. The same would be true of weapons or objects: a table of class-specific objects along with the 'denial text' (i.e. the response if the player could not pick up/wield/use that object) should be easy to code up, again using rules to do the checking. I suggest you have a look through the Inform Recipe Book and the examples on the main I7 website: you will glean alot from these. Regards, --PaulDV 14:47, 18 September 2008 (UTC)