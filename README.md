# BriaContacts
Import global contacts into the Bria Softphone client using an XML source url.

# Usecase
Bria Softphone client does not (yet) facilitate the option to automatically import a centralized contact list. This Python script fixes that.

# How it works
The Python script will read the contents of an XML file from a URl and import it into the contact list of the local Bria user. You need to change the URL to a URL pointing to your own XML file. For this, find the variable 'url'.

# XML format
The script uses a slightly modified version of the CiscoIPPhoneDirectory XML format. Check the example in the project folder.

# Limitations
This version will not let you remove or modify already added contacts.
Only tested on Windows 11.
User needs to at least log into the Bria client once.
