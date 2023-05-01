# 2300ADS-CPM
CP/M 2.2 for the GenRad 2300 Advanced Development System (aka MicroKit, FutureData, GenRad and Kontron 2300 ADS)

These are the sources to the latest/last version of CP/M 2.2 I developed for this machine back in the day (1980s LOL) while at Kontron Electronics, Inc.

## The 58kCPMv1.85_work folder
This folder contains an image of the working directory taken from a backup of my 35mb hard drive. This contains both sources to the CP/M system and various utilities used to create the CP/M image. Also present are various utilities used for formatting disks, setting serial parameters and such under 2300 ADS CP/M.

## The winbuild folder
This folder contains the various files described above, but pre-packed with the Z80-SIM CP/M emulator. You can download and unpack the .zip file under Windows and perform the build of the entire CP/M 2.2 system for the 2300 ADS.

## Repairs
- Keyboard unit - The Mylar foil can degrade in these Keytronic capacitive keyboards. The result is you may notice some keys work and some do not. The repair is easy with replacement foam from texELEC (link below). I reported back to texELEC success repairing two keyboards with their replacement foam for this system.

- Static RAM - Seems these don't last forever either. Intel P2141-3 4k x 1 static RAMs on the 64k static RAM board may fail with time. If boot prompt appears, but you can't boot RDOS, UDOS, or CP/M, you can use the built-in memory dump in the boot EPROM to try and localize the memory range. Knowing the range, the exact chip can be localized on the board.

- 8" Floppy drive - black sponge foam was used in places for absorbing shock when opening and closing drive doors. If your floppy sticks when attempting to eject, see if your floppy drive has such foam and if it's become a sticky mess.

- Micropolis disk drive controllers - I recall even back then they were somewhat fragile and prone to failure. I will need to debug one totally unresponsive 8" dual-drive unit when I have the chance. After all these years, fired it up and it simply does not work.

Should you have any questions, I can still offer limited assistance with this machine.

## Related sites of interest
http://bitsavers.trailing-edge.com/pdf/futuredata/ <br>
https://texelec.com/product/foam-capacitive-pads-keytronic/ <br>
http://bbslist.textfiles.com/213/oldschool.html (see entry for YARBBS) <br>

### Honorable mention (PolyMorphic Systems 8813 - the other computer)
http://bitsavers.trailing-edge.com/pdf/polyMorphicSystems/ <br>
https://deramp.com/polymorphic-computers/ <br>
