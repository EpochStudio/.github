# Sticky Message System Explained
Before we start, huge thanks to the following people for their help during the development of this feature:
- [aniket091](https://discord.com/users/474255126228500480)
- [sujal1048d](https://discord.com/users/668090704601415691)

Documentation Guide By: chrissch.dev

## [SubGroup - AddRemove]
 
### [Group - Add]:
    First checks if a Sticky Message exists in a channel. If exists, return an error message;
    If not exist, create a Message Collector, that collects the next message of the user (This message will be what's displayed on the Sticky Message)
    If the message is, longer than 900 characters, or equal to the word 'cancel', returns an error message.
    If the message passes all checks above, attempts to send the Sticky Message to the requested channel, if the bot does not have permission to send messages in that channel, automatically returns an error message.
    If successfully sent, the bot will try to save the data in the database, if something went wrong in saving the new data in the Database, the sticky message that was sent previously will be deleted.
 
### [Group - Remove]
    First checks for if a Sticky Message exists in a channel, if not exist, return an error message;
    Removes the sticky message entry from the database
 
## [SubGroup - Edit]
 
### [Applies for all of the following Group Commands]: 
    First checks for if a Sticky Message exists in a channel, if not exist, return an error message;
 
### [Group - Status]
    Enables/Disables the Sticky Messages in that channel (if its currently enabled, disables it, vice-versa)
 
### [Group - Content]
    Creates a Message Collector, that collects the next message of the user (This message will be what's displayed on the Sticky Message)
    If the message is, longer than 900 characters, or equal to the word 'cancel', returns an error message.
    If the message passes all checks above, attempt to delete the old Sticky Message, once done, send the new Sticky Message version to the channel.
    If sending the new Sticky Message to the channel is successful, immediately tries to save Data to the database, if fails, it will not delete the sticky message, or do anything, it will just return an error message. And the Sticky Message will continue posting Old Content.
    if successfully saved, reset the counter to 1
### [Group - Text Amount]
    Checks if the integer entered is lower than 2 or higher than 20, if yes, returns an error message
    Saves data to Database, if failed, return error message only
 
### [Group - Attachment Amount]
    Checks if the integer entered is lower than 1 or higher than 5, if yes, returns an error message
    Saves data to Database, if failed, return error message only
 
## [SubGroup - View]
 
### [Group - Edit]
	Loads all configured Sticky Messages inside the guild. Checks if a Sticky Message exists for a channel that no longer exists,
	if found, delete the said Sticky Message config.
	Once done with the checks (and actions, if any), lists all Sticky Messages configured inside a pagination embed.
