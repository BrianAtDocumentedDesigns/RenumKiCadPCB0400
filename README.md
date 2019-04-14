# RenumKiCadPCB0400
This is a GUI version of RenumKiCadPCB which renumbers components on a KiCad PCB and back-annotates the schematic

v1 fixed an issue whereby it woudl try and write the parameters file to Program Files (x86) which can only be done by an Administrator. 
I fiexed that by writing to user data (C:\Users\USER\AppData\Roaming\RenumKiCadPCB. 

Unfortunately, Microsoft Visual Studio seems to behave randomly when creating an MSI file so it woudl either include the icon or not, 
include the required dependencies (DLLs) or not, and install into Program File (x86) or a user directory. I spend a few days wrestling with
these issues and decided to just set it aside. I do include the Icon if you want to add it so a shortcut.
