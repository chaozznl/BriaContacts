# BriaContacts
Import global contacts into the Bria Softphone client using *an XML source url*.

# Usecase
Bria Softphone client does not (yet) facilitate the option to automatically import a centralized contact list. This Python script fixes that shortcoming.

# How it works
The Python script will read the contents of an XML file from a URl and import it into the contact list of the local Bria user. You need to change the URL to a URL pointing to your own XML file. For this, find the variable 'url'.

The script also changes two settings in the **user.config** file:
- **ContactPanelShowGroups** is set to *False*
- **ContactPanelSortByPresence** is set to *False*

You can comment this out, or add your own centralized settings.

# XML format
The script uses a slightly modified version of the *CiscoIPPhoneDirectory XML format*. Check the example in the project folder.

# Limitations
- This version will not let you remove or modify already added contacts.
- Only tested on Windows 11.
- User needs to at least log into the Bria client once for the correct folders and files to be created which this script can modify.
- All contacts added by this script are readonly by design. They can not be changed, but can be deleted by the end-user. Running the script again will restore the deleted contact.
