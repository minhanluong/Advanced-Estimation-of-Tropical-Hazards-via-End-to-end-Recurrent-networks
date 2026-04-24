=========================================================
Introductory Information
=========================================================

Title: STORM tropical cyclone wind speed return periods

Description: Each dataset contains information on wind speeds per fixed return period or vice versa (see file description for more information). The netCDF4-files give these values at
10 km resolution for every basin, the .xlsx-files give this information for tropical cyclone-events occurring within 100 km from either 18 pre-defined cities or 63 islands.

Format: The STORM_FIXED_RETURN_PERIODS and STORM_FIXED_WIND_SPEEDS - datasets are netCDF4 (.nc)-files. The STORM_CITIES and STORM_ISLANDS datasets are excel (.xlsx)-files.

File naming: The .nc-files have the general format STORM_FIXED_(variable)_(basin).nc, where variable represents the variable held fixed (either RETURN_PERIOD or WIND_SPEEDS). The Basin IDs
can be found in the description. The .xlsx-files have the general format STORM_(location)_WIND_SPEED_RETURN_PERIODS.xlsx, where location is either CITIES or ISLANDS.  

Contact Information: nadia.bloemendaal@vu.nl

=========================================================
Methodological Information
=========================================================
Method description: the synthetic tracks were generated using the fully statistical STORM algorithm (see Bloemendaal, N., Haigh, I.D., de Moel, H. et al. Generation of a global synthetic tropical cyclone hazard dataset using STORM.
Sci Data 7, 40 (2020). for more information on the article). For the datasets at 10 km resolution (.nc files), we first applied a 2D-parametric wind model (Lin and Chavas 2012)
to each of the synthetic tracks, after which we used Weibull's plotting formula to empirically derive the return periods at each 10 km grid cell. For the datasets using the 100 km radius (.xlsx-files), 
we directly calculated return periods from the STORM dataset using Weibull's plotting formula. 

Software: All data was produced in Python 3.6.1 on the SURFsara Lisa Computer Cluster. The file format of the datasets has been chosen such that they can be opened and 
analyzed in a wide variety of computer programs.

Validation: Our findings at different spatial scales have been validated against other literature in the manuscript. 

=========================================================
Data Specific Information
=========================================================
The Basin IDs are:
EP = Eastern Pacific
NA = North Atlantic
NI = North Indian
SI = South Indian
SP = South Pacific
WP = Western Pacific

The entries of STORM_FIXED_RETURN_PERIODS_(basin).nc is as follows: (copied from Bloemendaal et al - Estimation of global tropical cyclone wind probabilities using the STORM dataset)

				Parameters
Name					Unit			Notes
Longitude (lon)				Degrees			Ranges from 0-360°, with prime meridian at Greenwich
Latitude (lat)				Degrees	
Return period (rp)			Year			Given at 10, 20, 30 … 100, 200, 300 … 1,000, 2,000, 3,000 … 10,000-yr return period

				Variables
Name (dependency)			Unit			Notes
Mean (lat, lon, rp)			m/s			Mean wind speed of 1,000 random realizations, at each return period
Standard deviation (lat, lon, rp)	m/s			Standard deviation in wind speeds of 1,000 random realizations, at each return period
5% confidence interval (lat, lon, u)	m/s			5% confidence interval value derived from 1,000 random realizations, at each return period
95% confidence interval (lat, lon, u)	m/s			95% confidence interval value derived from 1,000 random realizations, at each return period

The entries of STORM_FIXED_WIND_SPEEDS_(basin).nc is as follows:

				Parameters
Name					Unit			Notes
Longitude (lon)				Degrees			Ranges from 0-360°, with prime meridian at Greenwich.
Latitude (lat)				Degrees	
Wind speed (u)				m/s			Given at 20, 25, 30 .. 75 m/s, and at 18, 33, 42 and 58 m/s to comply with the category thresholds on the Saffir-Simpson scale27

				Variables
Name (dependency)			Unit			Notes
Mean (lat, lon, u)			year			Mean return period of 1,000 random realizations, at each wind speed
Standard deviation (lat, lon, u)	year			Standard deviation in return periods of 1,000 random realizations, at each wind speed
5% confidence interval (lat, lon, u)	year			5% confidence interval value derived from 1,000 random realizations, at each wind speed
95% confidence interval (lat, lon, u)	year			95% confidence interval value derived from 1,000 random realizations, at each wind speed

The entries of STORM_CITIES_RETURN_PERIODS_WIND_SPEEDS.xlsx is as follows:

Entry		Column name		Notes
1		City			Name of city
2		Country			Name of country
3		Latitude		Latitudinal coordinates of capital city as given in Google Maps (maps.google.com).
4		Longitude		Longitudinal coordinates of capital city as given in Google Maps (maps.google.com), ranging from 0-360° with prime meridian at Greenwich.
5-31		Return period		On “Fixed return periods”-tab: maximum wind speed (m/s) at given return period
5-20		Wind speed		On “Fixed wind speeds”-tab: return period (yr) at given wind speed. Wind speeds are given at 5 m/s intervals and at values corresponding to Category thresholds on the Saffir-Simpson Scale.

The entries of the STORM_ISLANDS_RETURN_PERIODS_WIND_SPEEDS.xlsx is as follows:

Entry		Column name		Notes
1		City			Name of capital city
2		Country			Name of Island Country
3		Latitude		Latitudinal coordinates of capital city as given in Google Maps (maps.google.com).
4		Longitude		Longitudinal coordinates of capital city as given in Google Maps (maps.google.com), ranging from 0-360° with prime meridian at Greenwich.
5-31		Return period		On “Fixed return periods”-tab: maximum wind speed (m/s) at given return period
5-20		Wind speed		On “Fixed wind speeds”-tab: return period (yr) at given wind speed. Wind speeds are given at 5 m/s intervals and at values corresponding to Category thresholds on the Saffir-Simpson Scale.
			