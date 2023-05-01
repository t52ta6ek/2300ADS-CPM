Contains the contents of the "58kCPMv1.85_work" folder prepacked with Z80-SIM to
allow you to experiment and rebuild the system under Windows. Descriptions of the
content can be found there.

The Z80-SIM CP/M 2.2 emulator is a minimal implementation of CP/M and does allow DO.COM
to run properly, so building the system differs just slightly to how I would have built
natively under ADS CP/M itself.

Instructions:

1. Extract the contents of the DSDD_WORK.zip file into a folder in Windows called DSDD_WORK.<br>
Right-click DSDD_WORK.zip and "Extract All..." and a new folder DSDD_WORK will be created.<br>
(SHA-1 of DSDD_WORK.zip is 36183d244df1d3cca08a4cafd9e93b9043dbd5f2)

2. In the DSDD_WORK folder, run the "run.bat" file, you will see Z80-SIM boot up.<br>
Drive A: contains the Z80-SIM CP/M system.<br>
Drive B: contains a copy of my working directory for building the sources.<br>
Drive C: contains WordStar that will run on Z80-SIM<br>

3. Build the sources, type:<br>
<b>b:<br>
submit asm b b</b><br>

4. Perform the link and creation of ACOPYSYS.COM:<br>
<b>plink @cpm58k</b><br>

Now that you've created the system generation utility, the question of course, is how do
you actually generate an 8" CP/M boot floppy for your system?

Some thoughts...

It should be possible to extract a memory image of my running system with ACOPYSYS still in
memory of 0100H. The 2300 ADS boot EPROM could be modifed to accept, say Intel HEX from SIO1
write that to memory. Control could then be passed off to CP/M itself, i.e. getting the CP/M
image from the RS-232 port rather from floppy.

The ACOPSYS.MAP file describes where in memory each of the sections should be loaded. If you
have the means, you could also create your own boot EPROM as described above, then extact
the binary sections from ACOPYSYS.COM, get those into memory, then cold boot to CP/M. The
BOOTPROM.MAC file shows a minimal bootloader (booting from floppy) that you can use as an
an example boot EPROM. The trick is to also load ACOPYSYS.COM also into memory starting at
0100H, then once you get to the CP/M command promt, type:<br>
<b>X 0 A</b><br>

This will instruct ZCPR to run the current program from memory (ACOPYSYS), then create a CP/M
boot floppy on your floppy in Drive A:. Put the original boot EPROM back into the system.

At the bootprom's promt, the \<C\>\<RETURN\> to boot CP/M.
