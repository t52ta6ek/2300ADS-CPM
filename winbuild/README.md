Contains the contents of the "58kCPMv1.85_work" folder prepacked with Z80-SIM to
allow you to experiment and rebuild the system under Windows.

The Z80-SIM emulator is a minimal implementation of CP/M and does allow DO.COM to run
properly, so building the system differs just slightly to how it would be build natively
under ADS CP/M itself.

Instructions:

1. Extract the contents of the DSDD_WORK.zip file into a directory in Windows called DSDD_WORK.

2. Run the "run.bat" file, you will see Z80-SIM boot up.<br>
Drive A: contains the Z80-SIM CP/M system.<br>
Drive B: contains a copy of the working directory for building the sources.<br>
Drive C: contains WordStar that will run on Z80-SIM<br>

3. Build the sources, type:<br>
<b>b:<br>
submit asm b b</b><br>

4. Perform the link and creation of ACOPYSYS.COM:<br>
<b>plink @cpm58k</b><br>

Now that you've created the system generation utility, the question of course, is how do
you actually generate an 8" CP/M boot floppy for your system?

It should be possible to extract a memory image of my running system. The 2300 ADS boot EPROM
could be modifed to accept, say Intel HEX from SIO1 write that to memory. Control could then
be passed off to CP/M itself, i.e. getting the CP/M image from the RS-232 port rather from
floppy.
