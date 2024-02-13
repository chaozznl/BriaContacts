# Bria Softphone Contacts
Import global contacts into the Bria Softphone client using an `XML source URL`.

# Usecase
Bria Softphone client does not (yet) facilitate the option to automatically import a centralized contact list. This Python script fixes that shortcoming.

# Parameter
BriaImportContacts.exe [url]   
Example: `BriaImportContacts.exe https://example.com/folder/contacts.xml`

# How it works
The Python script will read the contents of an XML file from a URL (parameter) and import it into the contact list of the local Bria user. The contacts file is an `SQL Lite` file which we can freely interact with.

The script also changes two settings in the `user.config` XML file:
- `ContactPanelShowGroups` is set to `False`
- `ContactPanelSortByPresence` is set to `False`
- `LoginRememberDetails` is set to `True`

You can comment this out, or add your own centralized settings.

The script creates a log.txt file that you can use to debug any potential issues.

# XML format
The script uses a slightly modified version of the `CiscoIPPhoneDirectory XML format`. Check the example in the project folder.

# Limitations
- This version will not let you remove or modify already added contacts.
- Only tested on Windows 11.
- User needs to at least log into the Bria client once for the correct folders and files to be created which this script can modify.
- All contacts added by this script are readonly by design. They can not be changed, but can be deleted by the end-user. Running the script again will restore the deleted contact.
- This script is only ever tested on a single Bria environment. Use at your own risk! If for some reason the contacts database does get corrupted, deleting `contacts.db` and restarting the Bria client will create a new database.
