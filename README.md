# wade-landsubsidence
Data repository for "Policy targeting to reduce economic damages from land subsidence," by C.M. Wade, K.M. Cobourn, G.S. Amacher, and E.T. Hester.

All data files are stored as STATA datasets (.dta). In all data files oid is the unique identifier assigned to each 300 square meter model cell in the study region. The identifier j reorders cells such that the first 10 observations are the pumping sites used in the simulation; j links data observations to the GAMS simulation code. 

Input data files:
aquiferdata.dta - Spatially interpolated values for aquifer attributes. Variables include confining unit thickness (cthick, in meters), transmissivity (tr, in square meters/day), and storativity (s, unitless).
distonly.dta - Distance between each pumping cell and each receiving cell. 
fzdata.dta - Variables used in the logistic regression analysis. Variables include 100-year FEMA flood zone classification (fz0, binary), elevation (elev, in meters), percent slope (pctslope), distance to water (distwater in meters; distwaterkm in kilometers), NLCD land cover classification (forest, water, wetland, other), and dummy variables for low elevation (loelev) and moderate elevation (modelev). 
censusdata.dta - Census variables. Variables include percent area of the census tract in a model cell (pctarea), average home value within a census tract (homes), and number of homes within a census tract (nhomes). 
fishnettracts.dta - Links model cell identifier with census tract identifiers. Variables include the first five digits of the census identifier (tract 5) and the subsequent 6 digits of the census identifier (tract 6). 

Output data files: 
results_lsfz10yr.dta - output data from 10-year simulation for each pumping and receiving site combination. Pumpsite is pumping site j, cell is receiving cell j, subm is predicted land subsidence (in meters), and fzloss is predicted property value losses from flood zone redesignation (in $ per 1 mgd of continuous pumping at the pumping site). 
