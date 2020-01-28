# Effect  of Uber on Transit Ridership: A Replication
 
## Contributors

[__Corey Christopherson__](https://github.com/chrico7 "Corey Christopherson on Github") ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0001-6470-1146)), [__Thomas Winegarden__](https://github.com/ThomasWinegarden "Thomas Winegarden on Github")  ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0003-1912-1964)), [__Richard Todd__](https://github.com/rcctodd)  ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0003-2083-9631)), [__Zack Garcia__](https://github.com/zacharyfgarcia)  ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0002-6538-5592))


## Contents

The purprose of this repo is to provide a complete workflow record of our attempt to replicate Figure 6  in the paper _Is Uber a Substitute or Complement for Public Transit_ by Hall, Palsson, and Price. This figure, titled "Effect of Uber on log transit ridership before and after entry", shows the coefficients of a regression of log transit ridership on the months before and after Uber entered a market. We attempt to verify whether the effect is indeed significant and whether the effect is indeed close to a 5% increase.  If we can't replicate this effect, it would reduce the impact of the central claim of the paper, as well as draw further importance to the fact that Uber ridership increases generally in larger cities and cities with small public transit anyways. 

Below is a citation of the study we are trying to replicate:

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

Analysis reported in the paper was conducted in [__Stata__](https://www.stata.com/), a proprietary statistical analysis software. In the intererests of furthering reproducibility, we were intrigued by this project; an opportunity to bridge the gap between the dominant tools of academic econometrics (Stata) and the open source community.

As we explored a replication project in R, we identified two alternatives:

* Call Stata commands from R. A package - [__RStata__](https://cran.r-project.org/web/packages/RStata/index.html) - is available to run Stata commands from R, but this requires a licensed version of Stata which is available to only one member of our team. This limitation will hamper our ability to collaborate.
* Manually convert Stata commands into R. We have examined the structure of the replication code. It is built for wholesale paper replication across 15 code files. Translating the Stata code to R to replicate a single figure would be a significant undertaking that we judge to be outside of and beyond the scope of this assignment.

Seeing a viable path forward in neither of these alternatives, we have elected to change our paper selection for future assignments.

- Session info ---------------------------------------------------------------------------------
 setting  value                       
 version  R version 3.6.2 (2019-12-12)
 os       Windows >= 8 x64            
 system   x86_64, mingw32             
 ui       RStudio                     
 language (EN)                        
 collate  English_United States.1252  
 ctype    English_United States.1252  
 tz       America/Los_Angeles         
 date     2020-01-26                  

- Packages -------------------------------------------------------------------------------------
 package     * version date       lib source        
 assertthat    0.2.1   2019-03-21 [1] CRAN (R 3.6.2)
 backports     1.1.5   2019-10-02 [1] CRAN (R 3.6.1)
 callr         3.4.0   2019-12-09 [1] CRAN (R 3.6.2)
 cli           2.0.1   2020-01-08 [1] CRAN (R 3.6.2)
 crayon        1.3.4   2017-09-16 [1] CRAN (R 3.6.2)
 desc          1.2.0   2018-05-01 [1] CRAN (R 3.6.2)
 devtools      2.2.1   2019-09-24 [1] CRAN (R 3.6.2)
 digest        0.6.23  2019-11-23 [1] CRAN (R 3.6.2)
 ellipsis      0.3.0   2019-09-20 [1] CRAN (R 3.6.2)
 fansi         0.4.1   2020-01-08 [1] CRAN (R 3.6.2)
 foreign       0.8-72  2019-08-02 [2] CRAN (R 3.6.2)
 fs            1.3.1   2019-05-06 [1] CRAN (R 3.6.2)
 glue          1.3.1   2019-03-12 [1] CRAN (R 3.6.2)
 magrittr      1.5     2014-11-22 [1] CRAN (R 3.6.2)
 memoise       1.1.0   2017-04-21 [1] CRAN (R 3.6.2)
 pkgbuild      1.0.6   2019-10-09 [1] CRAN (R 3.6.2)
 pkgload       1.0.2   2018-10-29 [1] CRAN (R 3.6.2)
 prettyunits   1.1.0   2020-01-09 [1] CRAN (R 3.6.2)
 processx      3.4.1   2019-07-18 [1] CRAN (R 3.6.2)
 ps            1.3.0   2018-12-21 [1] CRAN (R 3.6.2)
 R6            2.4.1   2019-11-12 [1] CRAN (R 3.6.2)
 Rcpp          1.0.3   2019-11-08 [1] CRAN (R 3.6.2)
 remotes       2.1.0   2019-06-24 [1] CRAN (R 3.6.2)
 rlang         0.4.2   2019-11-23 [1] CRAN (R 3.6.2)
 rprojroot     1.3-2   2018-01-03 [1] CRAN (R 3.6.2)
 RStata      * 1.1.1   2016-10-27 [1] CRAN (R 3.6.2)
 rstudioapi    0.10    2019-03-19 [1] CRAN (R 3.6.2)
 sessioninfo   1.1.1   2018-11-05 [1] CRAN (R 3.6.2)
 testthat      2.3.1   2019-12-01 [1] CRAN (R 3.6.2)
 usethis       1.5.1   2019-07-04 [1] CRAN (R 3.6.2)
 withr         2.1.2   2018-03-15 [1] CRAN (R 3.6.2)
 yaml          2.2.0   2018-07-25 [1] CRAN (R 3.6.0)
