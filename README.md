# PET_CBM_1541_Adapter
This is an adapter for connecting the 1541 (or other IEC floppy disk drives) to the Userport of a CBM8032 etc. It is the reconstruction of a hardware, that fits to an old EPROM, that was found in a CBM8032. Most likely, it works with other BASIC 4.0 CBM/PET computers.

<img src="https://github.com/svenpetersen1965/PET_CBM_1541_Adapter/blob/main/Rev.%200/Pictures/9899_-_CBM1541Ada.JPG" width="300" alt="Setup">

<img src="https://github.com/svenpetersen1965/PET_CBM_1541_Adapter/blob/main/Rev.%200/Pictures/9896_-_installation_CBM1541ada.JPG" width="300" alt="Setup">

<img src="https://github.com/svenpetersen1965/PET_CBM_1541_Adapter/blob/main/Rev.%200/Pictures/0037_-_setup_1541-II.JPG" width="300" alt="Setup">

For communication with the disk drive, a special instruction set is required.

•	each instruction starts with '!'<br> 
•	there are a couple of floppy disk related instructions, that have an alternative representation in the EPROM<br>
•	a !q will deactivate/quite the software<br>
•	a !@ will display the status of the 1541<br>
•	a !@"command" will send a command to the 1541<br>
•	No device number (,8) is required for any of the instructions<br>
•	The instructions are mostly standard BASIC4 instructions and can be short-cut as usually

!load"progname": 	       loads a program from 1541 <br>
!save"progname": 	       saves a program to 1541 <br>
!verify"progname":	       verifies a program <br>
!catalog: 	               displays the driectory of the floppy disk in the 1541 <br>
!open#SA,"file name": 	   it requires a # and after that it is a secondary address* <br>
!print#,"text": 	         prints a texts, also a secondary address after #* <br>
!get#: 	   * <br>
!close#SA: 	               closes a file, also a secondary address after #* <br>
!input#SA...: *<br>  
!cmd...* 	 <br>

The items marked with * require some further investigation. See the test documentation.

The software resides in a 2532 EPROM in UD11 and is started with SYS40960.
