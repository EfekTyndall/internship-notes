1. **DIOCFGSV.IO** = All I/O Information setup
2. **NUMREG.VR** = Data register information
3. **POSREG.VR** = Position register information
4. **FRAMEVAR.VR** = Frame setup information
5. **SYSFRAME.SV** = Tool frames and user frames
6. **XXX.TP** = Any Teach Pendant program

### DCS Settings

Most commonly, it would be **DCSPOS.SV**, **DCSIOC.SV**, and **SYSVARS.SV**

1. **DCSPOS.SV** = Position/Speed Check function (Includes user setting of Stop Position Prediction)
2. **DCSIOC.SV** = Safe I/O Connect function and user comments of the Safe I/O signals
3. **SYSCIPS.SV** = DeviceNet Safety or EtherNet/IP Safety (Items in DCS CIP safety menu)  
	NOTE - DCS parameters set by an external configuration tool are not included.
4. **SYSPASS.SV** = Code numbers
5. **SYSPNSF.SV** PROFINET Safety (Items in DCS PROFINET safety menu)  
	NOTE - F-Parameter is not included.
6. **SYSMAST.SV** Mastering parameters
7. **SYSVARS.SV** Robot setup data, Robot model, Defaults for Stop Position Prediction, Safe I/O device, Auxiliary axis servo off (local stop).
8. **LADDERS.PMC** Safety PMC program.
9. **SYSFLSF.SV** Safety function by FL-net (Items in DCS Safety function by FL-net menu)

NOTE  
1. When DeviceNet Safety function is used, basic devicenet settings (such as Mac   Id, baud rate) are held in SYSDNET.SV. Backup/restore SYSDNET.SV with SYSCIPS.SV if required.  
2. If EtherNet/IP Safety is used, standard settings such as IP address and subnet  mask will be saved in SYSHOSV.SV. If necessary, SYSHOSV.SV must also be saved with SYSCIPS.SV.  
3. In both DeviceNet Safety and EtherNet/IP Safety function, the Safety PLC data set in the robot (eg. SNN) is not included in any application backup. It must be explicitly set on a robot from the Safety PLC configuration software.  
4. When PROFINET Safety function is used, basic PROFINET settings (such as I/O Device configuration) are held in PNIO.SV in A05B-2600-J930, or in PMIO.SV in A05B-2600-R834. Backup/restore PNIO.SV or PMIO.SV with SYSPNSF.SV if required.  
5. In PROFIsafe, F-Host is supposed to send F-Parameter to F-Device. F-Parameter is not stored in any application backup.  
6. When Safety function by FL-net is used, basic FL-net settings (such as area 1/2 configuration) are held in FLNET.SV. Backup/restore FLNET.SV with SYSFLSF.SV if required.