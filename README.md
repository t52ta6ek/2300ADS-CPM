# 2300ADS-CPM
CP/M 2.2 for the GenRad 2300 Advanced Development System (aka MicroKit, FutureData, GenRad and Kontron 2300 ADS)

<b>The 58kCPMv1.85_work folder:</b><br>
This folder contains an image of the working directory taken from a backup of my 35mb hard drive. This contains both sources to the CP/M system and various utilities used to create the CP/M image. Also present are various utilities used for formatting disks, setting serial parameters and such under 2300 ADS CP/M.

<b>The winbuild folder:</b><br>
This folder contains the various files described above, but pre-packed with the Z80-SIM CP/M emulator. You can download and unpack the .zip file under Windows and perform the build of the entire CP/M 2.2 system for the 2300 ADS.

<b>Repairs:</b><br>
Keyboard unit - The Mylar foil can degrade in these Keytronic capacitive keyboards. The result is you may notice some keys work and some do not. The repair is easy with replacement foam from texELEC (link below). I reported back to texELEC success repairing two keyboards with their replacement foam for this system.

Static RAM - Seems these don't last forever either. Intel P2141-3 4k x 1 static RAMs on the 64k static RAM board may fail with time. If boot prompt appears, but you can't boot RDOS, UDOS, or CP/M, you can use the built-in memory dump in the boot EPROM to try and localize the memory range. Knowing the range, the exact chip can be localized on the board.

8" Floppy drive - black sponge foam was used in places for absorbing shock when opening and closing drive doors. If your floppy sticks when attempting to eject, see if your floppy drive has such foam and if it's become a sticky mess.

Should you have any, I can still offer limited assistance with any questions about this machine.

<b>Related sites of interest:</b><br>
http://bitsavers.trailing-edge.com/pdf/futuredata/ <br>
https://texelec.com/product/foam-capacitive-pads-keytronic/ <br>
http://bbslist.textfiles.com/213/oldschool.html (see entry for YARBBS) <br>
