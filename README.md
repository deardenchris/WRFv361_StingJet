# WRFv361_StingJet
WRF files used to perform a case study from 3rd December 2012 (potential sting jet over Romania)

This repository contains files used to perform a WRFv3.6.1 simulation of an intense European cyclone over Romania on 3rd December 2012, for Mihaela Brancus.

The simulation was originally performed in March 2017 on a 48-core Linux machine running Scientific Linux. The configure.wps and configure.wrf files contain the exact settings used to compile the model. The WRF code was also modified to enable tendency terms from the horizontal momentum equations to be output by the model.   

The simulation was initialised using the ECMWF operational analysis from 0000 UTC 2nd December 2012 on a 0.25 x 0.25 degree grid, with boundary conditions provided by the 6-hourly analyses up until 1200 UTC 3rd December. 

Details of the files are as follows:

namelist.wps : The namelist file used to run WPS, which generates the initial conditions and boundary conditions for the chosen domain. 

namelist.input.from_00UTC_12th : used to run WRF for the period 0000 UTC 2nd December 2012 to 1200 UTC 3rd December 2012, with diagnostic output produced every hour. 

namelist.input.restart_15min_3rd_00UTC : used to re-start the model from the 0000 UTC 3rd December checkpoint restart file, in order to produce additional output every 15 minutes until 0900 UTC. 

momentum_tendency_code : directory containing code modifications to enable terms from the horizontal momentum equations to be included in the model output files. These files are intended to work with WRFv3.6.1. Specifically, the files solve_em.F and module_em.F should be copied to the WRFV3/dyn_em directory, and Registry.EM_COMMON to WRFV3/Registry before attempting to compile the model.  

Chris Dearden.
