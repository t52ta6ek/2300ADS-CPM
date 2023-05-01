# 2300 ADS 58k CP/M 2.2 v1.85 Working Directory

This is the content of the CP/M directory that I used for development of the CP/M system
for the GenRad 2300 Advanced Development System. MicroKit/FutureData was sold to GenRad,
and this division was ultimately sold to Kontron in the early 80's where I worked for
many years.

This was the lastest version of CP/M I had developed for this machine. It was commercially
released by Kontron as an option in addition to RDOS and UDOS operating systems.

These files were pulled off of DSDD 8" floppy disk backups I had made of my 35mb hard drive.
That hard drive has unfortunately disappeared but the backups remain.

Contains not only source code to the system, but also the various system utilities
used for editing code, performing the build, formatting disks and other various
system generation tools I used at that time.

Some of the utilities were developed in assembly, others I developed using Turbo Pascal.
When I locate the sources to these utilities, they will be posted as well.

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

Then, hit the \<LOAD\> key. Place the newly created boot floppy from drive B: into the
boot drive. At the bootprom's promt, type \<C\>\<RETURN\> to boot CP/M.

The "winbuild" folder under the 2300ADS-CPM github contains the same files, but pre-packed
with the Z80-SIM CP/M emulator which runs on Windows. Z80-SIM is just enough CP/M to
allow you to rebuild the the system, and product the ACOPYSYS.COM system generation
tool. See that folder for specific instruction to perform the build.

<b>2300 ADS 58k CP/M 2.2 v1.85</b><br>
ADSCHG.TXT    - ADS CP/M revisions list<br>
ADSBOOT.MAC   - CP/M coldboot loader<br>
BDOS.MAC      - CP/M 2.2 BDOS<br>
EQUATES.LIB   - definitions for BDOS.MAC<br>
BOOTMSG.MAC   - Console boot message after CP/M boots<br>
CBIOS.MAC     - 2300 ADS CBIOS<br>
CRT.MAC       - Console CRT and Keyboard drivers. Nominal emulation of ADDS Viewpoint control codes<br>
DEFAULTS.MAC  - Default serial port and console settings<br>
DHDISK.MAC    - Dummy hard disk - to delete hard disk support<br>
FLOPPY.MAC    - Micropolis floppy disk controller<br>
HDISK.MAC     - Local NCP Hard disk drivers. Micropolis controller and 8" hard drive unit.<br>
LPT.MAC       - LPT device (parallel port)<br>
MEU.MAC       - Memory Expansion Unit RAM disk driver<br>
PTP.MAC       - Paper tape punch (serial port 2)<br>
PTR.MAC       - Paper tape reader (serial port 2)<br>
REINIT.MAC    - Reinitialize peripherals that were reset by \<RESET\><br>
TABLES.MAC    - Used by REINIT.MAC to reload console and serial settings<br>
TTY.MAC       - Serial TTY (serial port 1)<br>
UL1.MAC       - Serial printer (serial port 2)<br>
UP1.MAC       - Serial port 3 output support<br>
UP2.MAC       - Serial port 4 output support<br>
UR1.MAC       - Serial port 3 input support<br>
UR2.MAC       - Serial port 4 input support<br>
ZCPR.MAC      - ZCPR 4.0 shell<br>

<b>Assemble and Link to produce ACOPYSYS.COM sysgen utility</b><br> 
ASM.SUB       - Batch file for performing the assembly builds<br>
CPM58K.LNK    - PLinkII linker command file for creating the sysgen utility ACOPYSYS.COM<br>
ACOPYSYS.MAC  - Sources for system boot disk creation utility<br>
ACOPYSYS.COM  - The end product of the build is the ADS CPM's "sysgen" utility<br>
ACOPYSYS.MAP  - Plink linker-created MAP file<br>

<b>Experimental boot EPROM</b><br>
This can be used to turn an NCP control unit into a headless CP/M system.<br>
BOOTPROM.MAC  - Experimental boot EPROM for Network Control Processor. 
BOOTPROM.LNK  - PLinkII linker command file for BOOTPROM.MAC<br>

<b>Utilities required to build 2300 ADS CP/M</b><br>
DO.COM        - DO 1.5<br>
M80.COM       - Microsoft M80 Macro Assembler<br>
PLINK.COM     - PSA Linkage Editor II<br>
ZAP.COM       - Zero unused memory<br>

<b>Utilities specifically created for 2300 58k ADS CP/M 2.2 v1.85</b><br>
Most of these utilities were implemented in Turbo Pascal. The source code for these will be forthcoming. The utilities only work with this specific version of the operating system as they access CBIOS internal data structures.<br> 
AAUTOST.COM   - Utility to set initial command to run after CP/M boots<br>
AFORMAT.MAC   - 8" floppy disk formatter source<br>
AFORMAT.COM   - Disk format utility<br>
AFORMAT2.COM  - Alternate disk format utility implemented in Turbo Pascal<br>
AMODEM7.COM   - Original implementation of Modem7 for ADS CP/M.<br>
ASETDRV.COM   - Utility to allow custom associations of CP/M drive letters to specific controllers/drive units<br>
ASETDSK.COM   - Utility to set which drives are SSDD and DSDD<br>
ASETIO.COM    - Utility to set the CP/M I/O byte<br>
ASETSIO.MAC   - Source code for utility for setting RS-232 serial parameters<br>
ASETSIO.COM   - Utility to set serial port parameters<br>
NCPINIT.COM   - Utility to format local 35mb NCP hard disk drive<br>

<b>Programs configured for 2300 ADS CP/M</b><br>
MDM7.COM      - MDM7 I used for most day to day activities, calling BBSes, uploads/downloads<br>
WASH.COM      - WASH v3.6 for ADS CP/M<br>
WS.COM        - WordStar 3.30 configured for ADS CP/M and NEC Spinwriter printer which I used at that time<br>
WSMSGS.OVR    - WordStar 3.30<br>
WSOVLY1.OVR   - WordStar 3.30<br>

<b>Other off-the-shelf utilities</b><br>
ARK.COM       - ARK v1.1<br>
CRCK.COM      - CRCK v5.1<br>
DU.COM        - DU2 v1.7<br>
DUMP.COM      - DUMP v1.0<br>
FBAD.COM      - FBAD57<br>
MEMR.COM      - Memory test program<br>
NULU.COM      - NULU v1.0<br>
PIP.COM       - PIP v1.5 as delivered with 2300 ADS CP/M<br>
RECLAIM.COM   - RECLAIM v2.1<br>
SAP.COM       - SAP v4.2<br>
STAT.COM      - CP/M STAT as delivered with 2300 ADS CP/M<br>
UNARC.COM     - UNARC v1.6<br>
UNERA.COM     - UNERA v2.2<br>
USQ.COM       - USQ v1.18<br>
XOUT.COM      - XOUT for XSUB as delivered with 2300 ADS CP/M<br>
XSUB.COM      - XSUB v1.4 as delivered with 2300 ADS CP/M<br>
ZSID.COM      - ZSID v1.4 as delivered with 2300 ADS CP/M<br>
