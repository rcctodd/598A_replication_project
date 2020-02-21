# Shape as a Measure of Weapon Standardisation: A Replication
 
## Contributors

[__Corey Christopherson__](https://github.com/chrico7 "Corey Christopherson on Github") ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0001-6470-1146)), [__Thomas Winegarden__](https://github.com/ThomasWinegarden "Thomas Winegarden on Github")  ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0003-1912-1964)), [__Richard Todd__](https://github.com/rcctodd)  ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0003-2083-9631)), [__Zack Garcia__](https://github.com/zacharyfgarcia)  ([![](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0002-6538-5592))


## Contents

The purpose of this repo is to provide a complete workflow record of our attempt to replicate Figure 8 in the paper _Shape as a measure of weapon standardisation: From metric to geometric morphometric analysis of the Iron Age ‘Havor’ lance from Southern Scandinavia_ by Birch and Martinon-Torres. This figure shows the pair-wise correlation of all lance dimensions across the three underlying datasets next to bivariate plots and distributions of each single dimension with kernel density approximation.  We attempt to verify whether these calculations and smoothed distributions look similar upon replication, and also are interested how close we can get to the correct style without any of the actual original figure code. 

Below is a citation of the study we are trying to replicate:

Birch, T., & Martinon-Torres, M. (2018). Shape as a measure of weapon standardisation: From 
    metric to geometric morphometric analysis of the Iron Age ‘Havor’ lance from Southern
    Scandinavia. Journal of Archaeological Science, 101, 34-51. doi: 
    https://doi.org/10.1016/j.jas.2018.11.002


## Data (Extended) Datasets

Included Files:
- mmc2.csv: Contains dimensionality information about 123 different lances. These are the following fields: 

	site: Where the lance was found. This can be Ejsbol, Nydam, or Illerup. 
	ID: Unique ID for each lance
	point: Boolean, whether it has a point
	socket: Boolean, whether it has a socket 
	total_length: Total lance length in cm
	blade_length: Blade's length in cm
	socket_length: Just the socket of the lance's length in cm
	sock_bdiam: Maximum socket diameter in cm
	sock_sdiam: Minimum socket diameter in cm
	width: Blade width in cm
	thickness: Blade thickness in cm
	rdist: Distance between rivets in cm
	
- mmc3.csv: Contains normalized coordinates for the seven main "landmark" points defining the shape of 78 different lances,
	site_lance-id: site and ID from mmc2.csv for the lance, concatenated
	x1: x-coordinate of point 1
	y1: y-coordinate of point 1
	...
	x7: x-coordinate of point 7
	y7: y-coordinate of point 7

- yjasc_4911_Appendix_A.R: Source R script for analysis and figure generation done in the paper. 

These data were gathered from ____. 

## Dependencies

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
 
 ## Contributing
 
We welcome contributions from everyone. Before you get started, please see our [contributor guidelines](https://github.com/rcctodd/598A_replication_project/blob/master/CONTRIBUTING.md). Please note that this project is released with a [Contributor Code of Conduct](https://github.com/rcctodd/598A_replication_project/blob/master/CODE_OF_CONDUCT.md). By participating in this project you agree to abide by its terms.
