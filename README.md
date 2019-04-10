# RenumKiCadPCB0400
This is a GUI version of RenumKiCadPCB which renumbers components on a KiCad PCB and back-annotates the schematic. This version also 
provides some limited text manipulation like orient all reference on F.Silks to 45 degrees, etc..

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

Note that there is a known issues with KiCad which makes it a lot easier to run RenumKiCadPCB before you do your copper pours. 

A bug in KiCad PCBNew ([Bug 1609401] Re: PCBnew fails to properly import netlist after changing annotation with pours see https://bugs.launchpad.net/kicad/+bug/1609401). If RenumKiCadPCB is run on a project with copper pours and a schematic netlist is created and imported into PCBNew errors can occur in the netlist import and subsequent DRC. This happens even without using RenumKiCadPCB: sometimes after changing reference designations on PCB and eeSchema if you then generate a netlist and re-import it into PCBNew there may be netlist errors and DRC errors if the board has copper pours.
The fix is simple. Type 'B' and the pours will regenerate except where there are errors where they appear hatched. Note the ratsnest netlist name in the hatched error zone. Edit the zone (hit 'E' near a zone edge) and change the pour net to the ratsnet netlist name. (the ratsnest name is usually near the top of the selection window). Type 'B' again, and the pour will fill. Run DRC and the errors are gone.


Contact brian@documenteddesigns.com with any bu reports or feature requests.


