# RenumKiCadPCB0400
This is a GUI version of RenumKiCadPCB which renumbers components on a KiCad PCB and back-annotates the schematic.

This program automatically renumbers a KiCad PCB according to various rules then back-annotates the renumbering scheme into the
schematic hierarchy. This makes finding components on the PCB very easy. I recommend renumbering early in the layout process 
because the “copper pour” problem (see below) only shows up after updating. Also, RenumKiCadPCB will spot errors early. I have 
stress tested with https://github.com/OLIMEX/DIY-LAPTOP/tree/master/HARDWARE/A64-TERES/TERES-PCB1-A64-MAIN_Rev_C which is the 
most complex KiCad project I have come across. The Rev C files themselves have issues such as ERC and DRC errors, an excess 
#PWR flag, and there are blank reference designations (i.e. "") on the PCB. 

The files includes all the build information for Windows (Microsoft Visual Studio, MSYS2, and Eclipse/MSYS2) and Linux 
(see RenumKiCadPCB Readme.PDF). There is also a Windows 10 RenumKiCadPCB.msi file which does an automated installation.

This project is built on wxWidgets so if you had as much grief as I did getting a wxWidgets project to work from scratch 
you might find the relevant project information for Microsoft Visual Studio and Eclipse helpful.

Contact brian@documenteddesigns.com with any bu reports or feature requests.


