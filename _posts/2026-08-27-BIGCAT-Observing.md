---
title: Observing project C3772 on ATCA
tags:
  - physics
  - radio
  - pulsar
  - astronomy
layout: post
---
A LaTeX document of this information is available [here as a pdf](assets/pdf/jsalis_observing_c3772_atca.pdf).
# 1. Load the schedule file 
- `set file c3772_psr`
	- Do this in the black window in the first desktop (top right)
	- This window is where most commands are ran from.

# 2. Observe the calibrator (J1934)  
- **2.1**: `start 1-1/1`
	- This performs a 10min observation of the primary calibrator. It will automatically stop once it has completed.

- **2.2**: To check that everything is working:
	- Go to NSPD (window 3).
	- The right hand window shows amplitudes or phases for each baseline. Use the below commands in the left window to ensure everything looks nominal.
		- `sel <f1, f2, f3, f4>` for frequency subbands
		- `am` for amplitudes
		- `ph -200 200` for phases
	- Go to NVIS (window 2)
		- Ensure that phases are not drifting around like crazy. They should be roughly straight lines.

- **2.3**: `corr closef`
	- Make sure to save the calibration observation once it has completed

# 3. Observe J1638-4725.
- **3.1**:  `start 3-4/99`
	-  This tells the program to switch between object 3 and 4 for the assigned duration 99 times. There is not enough time in the observation to do it 99 times, and it is our responsibility to shut it off and allow time to slew to the calibrator again at the end of the observation.

- **3.2**: Check everything is working. Refer to 2.2.

- **3.3**: `stop`
	- Leave at least 10-15 minutes at the end of the allocated observing time to allow for slewing and observing the primary calibrator.

- **3.4**: `corr closef`
# 4. Observe the calibrator (J1934)  
- **4.1**: Refer to step 2.
	- Remember to perform `corr closef`

# 5. Cleanup
- **5.1**: `corr stop`
	- Stop the correlator. It will automatically restart for the next observer.

- **5.2**: Convert observation files (window 5)
	- `ls 2026*C3772`
	- `cd <dir>`
	- `convert_asdm.py raw/`
	- For each observation file created (should be 3, one for each `corr closef`), go inside and perform the above commands

- **5.3**: You may wish to `stow` the dish(es)
- **5.3:** You are now ready to hand over to the next observer via the portal



# Appendix A:
Table 1: Sources for schedule `c3772_psr.json`, and their durations

| Source Number | Name             | Duration (s) |
| ------------- | ---------------- | ------------ |
| 0001          | `1934-638`       | 600          |
| 0002          | `0823-500`       | 600          |
| 0003          | `J1631-4345`     | 300          |
| 0004          | `PSR_J1638-4725` | 1200         |
