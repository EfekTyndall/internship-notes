1. **Try Speed Check Settings.**
	- SIR[4] : Disable von CSC = FSI 1 OR  SIR[5]
	- SIR[5] : In working Area = CPC 1 OR CPC 2
2. **Optimize screwing position and reteach it.**
3. **Update code with tact timer.**
	- ISRA_MAIN_ZAVIER
	- ISRA_LH_SCREWING
	- ISRA_RH_SCREWING
	- SAFEMOVE_CHECK_HOME
	- SAFEMOVE_CHECK LEFT
	- SAFEMOVE_CHECK_RIGHT
4. **Run Test and document with different conditions.**

| Process        | Time [s] |
| -------------- | -------- |
| MAIN           |          |
| SAFEMOVE HOME  |          |
| SAFEMOVE LEFT  |          |
| SAFEMOVE RIGHT |          |
| LH SCREWING    |          |
| RG SCREWING    |          |

5. **Create Documentation on DCS Settings**