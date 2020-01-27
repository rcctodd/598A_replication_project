# Effect  of Uber on Transit Ridership: A Replication
 
## Contributors

__Corey Christopherson__   ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0001-6470-1146)), [__Thomas Winegarden__](https://github.com/ThomasWinegarden "Thomas Winegarden on Github")  ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0003-1912-1964))

## Contents

The purprose of this repo is to provide a complete workflow record of our attempt to replicate Figure 6  in the paper _Is Uber a Substitute or Complement for Public Transit_ by Hall, Palsson, and Price. This figure, titled "Effect of Uber on log transit ridership before and after entry", shows the coefficients of a regression of log transit ridership on the months before and after Uber entered a market.

<enter claim here>

Hall, J. D. Palsson C. & Price, J (2018). Is Uber a substitute or complement for public transit? Journal of Urban Economics, 108, 36-50. https://doi.org/10.1016/j.jue.2018.09.003.


## Data
The data for this replication can be found in an Open ICPSR project found by following the DOI link: https://doi.org/10.3886/E115490V2.

## Data (Extended) Datasets
Dataset defitions are provided by the Principal Investigators via [this text file](https://www.openicpsr.org/openicpsr/project/115490/version/V2/view?path=/openicpsr/115490/fcr:versions/V2/build/code/Dataset-definition.txt&type=file). and we have included them below to illustrate the input datasets.

Data:
- Uber entry and exit dates by market
	- uberMarketName
	- State
	- For X in {Any, Fancy, X} and Y in {1, 2}:
		- dateEntered`Y'Uber`X'
		- dateExitedUber`Y'`X'
  
- Lyft entry and exit dates by market
	- lyftMarketName
	- State
	- For Y in {1,2}:
		- dateEntered`Y'Lyft
		- dateExited`Y'Lyft
  
- Google trends data
	- dateSurvey
	- google_trends
	- City
	- State
 
- Monthly NTD data
	- NTDID
	- dateSurvey
	- For X in {UPT, VOMS, VRM, VRH} and Y in {Bus, Rail, Other, Total}
		- `X'`Y'
	- Notes:
		- UPT: Unlinked passenger trips
		- VOMS: Vehicles operated in maximum service
		- VRM: Vehicle revenue miles
		- VRH: Vehicle revenue hours
  
- Annual NTD data 
	- NTDID
	- dateSurvey
	- For Y in {Bus, Rail, Other, Total} and X in
		- capEx`Y' - capital expenditures
		- annualUPT
		- passMiles - passenger miles
		- opEx - operating expenses
		- routeMiles 
		- fares
		- aveFares
		- aveTripLength
		- aveOpExTrip - operating expenses per trip
  
- MSA controls (probably annual)--Such as census division and census region

- Agency level constants
	- NTDID
	- is HQ in principle city of MSA or not (ie, suburban vs urban agency)
	- Agency name
	- UZA name
	- UZA Number
	- MSA Name
	- State
- UA to MSA crosswalk

- Define treatment variables
- Collapse to agency level
- Generate percentiles

## Dependencies
