### Speed Test

**Speed Test 80N Limit, 10% Override or 50 mm/s:**
- LH:
	- From Home to pre-pos LH force exceeded limit 
	- From screw 12 to screw 13 force exceeded limit 
	- From screw 15 to screw 16 force exceeded limit 
	- From screw 18 to pre-pos
- RH:
	- From pre-pos to 11 force exceeded limit (just before reaching measuring position)
	- From screw 12 to screw 13 force exceeded limit (during collision avoidance motion)

**Speed Test 80N Limit, 100% Override or 500mm/s:**
- For both LH and RH not possible

### Cycle Time

**150N Limit, 10% Override or 50mm/s:**
- LH:
	- TIMER[1] = 231,34 s
	- TIMER[5] = 281,76 s
	- **TIMER[6] = 25,31 s**
	- TIMER[7] = 24,66 s
	- TIMER[8] = -
- RH:
	- TIMER[1] = 244,48 s
	- TIMER[5] = 294,47 s
	- TIMER[6] = 25,78 s
	- TIMER[7] = -
	- TIMER[8] = 24,21 s

**150N Limit, 100% Override or 500mm/s:**
- LH:
	- TIMER[1] = 70,82 s
	- TIMER[5] = 77,54 s
	- TIMER[6] = 3,39 s
	- TIMER[7] = 3,33 s
	- TIMER[8] = -
- RH:
	- TIMER[1] = 71,25 s
	- TIMER[5] = 77,57 s
	- TIMER[6] = 3,40 s
	- TIMER[7] = -
	- TIMER[8] = 2,92 s


### Cycle Time Schwenkbewegung

**150N Limit, 10% Override or 50mm/s:**

|                      | Test Run 1 | Test Run 2 | Test Run 3 |   Average   |
| :------------------: | :--------: | :--------: | :--------: | :---------: |
| **HOME -> PREPOSLH** |  25,31 s   |  25,30 s   |  25,30 s   | **25,30 s** |
| **PREPOSLH -> HOME** |  25,38 s   |  25,30 s   |  25,30 s   | **25,33 s** |
| **HOME -> PREPOSRH** |  25,38 s   |  25,30 s   |  25,30 s   | **25,33 s** |
| **PREPOSRH -> HOME** |  25,30 s   |  25,30 s   |  25,30 s   | **25,30 s** |

**150N Limit, 100% Override or 500mm/s:**

|                      | Test Run 1 | Test Run 2 | Test Run 3 |  Average   |
| :------------------: | :--------: | :--------: | :--------: | :--------: |
| **HOME -> PREPOSLH** |   2,95 s   |   2,94 s   |   2,94 s   | **2,94 s** |
| **PREPOSLH -> HOME** |   2,94 s   |   2,94 s   |   2,94 s   | **2,94 s** |
| **HOME -> PREPOSRH** |   2,94 s   |   2,94 s   |   2,94 s   | **2,94 s** |
| **PREPOSRH -> HOME** |   2,94 s   |   2,94 s   |   2,94 s   | **2,94 s** |

### Tact Time Test

**150N, 1000 mm/s (NSI[3] as disabling input for SIR[2]):**
- No stops between each screwing process

| Process | Swivel Movement | Screwing Process | Swivel to Home |
| ------- | --------------- | ---------------- | -------------- |
| **LH**  | 1.72 s          | 71.92 s          | 1.74 s         |
| **RH**  | 1.73 s          | 72.11 s          | 1.74 s         |




