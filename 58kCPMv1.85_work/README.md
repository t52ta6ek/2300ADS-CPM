2300 ADS 58k CP/M 2.2 v1.85

Copy of the CP/M directory that I used for development of the CP/M system for the
FutureData 2300 ADS. FutureData was sold to GenRad, and this division was ultimately
sold to Kontron in the early 80's where I worked for many years.

This was the lastest version of CP/M I had developed for this machine.

Contains not only source code to the system, but also the various system utilities
used for editing code, performing the build, formatting disks and other various
system generation tools I used at that time.

Some of the utilities were developed in assembly, others I developed using Turbo Pascal.
When I locate the sources to these utilties, they will be posted as well.

The original 2300 ADS system was delivered with two 8" SSDD floppies. It was possible
to swap these out for DSDD floppies. Additionally, this CP/M supports the Memory
Expansion Unit (MEU) RAM disk, both in its 512k and 1024k configurations. The 35mb
expansion hard drive with it's single 8" drive are also supported as local drives. This
CP/M uses cursor and screen control codes similar to the ADDS Viewpoint terminal.

On the original system, I used the following commands to perform the build:<br>
<b>DO ASM</b><br>

Then performed the link and creation of ACOPYSYS.COM:<br>
<b>PLINK @CPM58K</b><br>

To copy the system to the boot sector, I'd put a formatted floppy into drive B:,
fill memory free memory with 00H using the ZAP command, then use ACOPSYS to copy
from its memory ("0") to drive B. ZAP is optional. It simply cleans memory so that
whatever random memory content does not also get put into the boot sector. Just to
be tidy.<br>
<b>ZAP</b><br>
<b>ACOPYSYS 0 B</b><br>

Then, hit the \<RESET\> key. Place the newly created bootfloppy from drive B: into the
boot drive. At the bootprom's promt, the \<C\>\<RETURN\> to boot CP/M.

The "winbuild" folder under the 2300ADS-CPM github contains the same files, but pre-packed
with the Z80-SIM CP/M emulator which runs on Windows. Z80-SIM is just enough CP/M to
allow you to rebuild the the system, and product the ACOPYSYS.COM system generation
tool. See that folder for specific instruction to perform the build.
