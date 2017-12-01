# Analysis of maternal mortality data

This repo contains data, code and analyis supporting the Texas Tribune's maternal mortality project. We used two main analysis in the story:
  
  * The mortality and prenatal rates in rural counties v. urban counties in Texas for 2010-14.
  * The mortality and prenatal rate for counties with at least one hospital with an obstetric bed v. those that did not have one. This was for 2014.

## Installation

This project uses [pipenv](http://docs.pipenv.org/en/latest/) to manage dependencies. Once you have that set up, install the dependencies.

```sh
pipenv install --three
```

Optional: Install extensions

```sh
jupyter contrib nbextension install --user
```

Optional: Activate extensions

```sh
jupyter nbextensions_configurator enable --user
```

Then you can run Jupyter notebooks.

```sh
pipenv run jupyter notebook
```

## Notebooks
Several Juypter notebooks were used to run the analysis. Here's a breakdown of each one:

01-population:
  * This is used to convert race data for each county into usable csv files. Race data probably won't be used in the initial story.

01-prenatal:

  * This first takes prenatal data, which is broken down by year for 2010 to 2014 and sums it all. It also calculates how many eligible pregnant women there are for each county because all that is provided is the number of women who received and what percentage they were of all women.
  * It then merges that data with race data, which probably won't be used in the initial story.
  * Finally, sums all the race data, which probably won't be used.

01-prenatal-race:

  * This combines prenatal data broken down by race with each county's urban/rural designation. Race data probably won't be used in the initial story.

02-mortality-race:

  * This merges five years of mortality and race data into one csv, with a row for each county. Race data probably won't be used in the initial story.
  * It then merges the mortalty rates for each county with race data, which probably won't be used in the initial story.
  * It then sums up each race and calculates the rate for each race, which probably won't be used in the initial story.
  * Those files now have maternal rates and race information for each county. It is combined with the county's urban/rural designation to determine if the county is rural or urban. It's also combined with border information to determine if the county is on the border or not.

03-ob-hospitals:

  * This first joins hospital obstetric data with the spreadsheet that has the mortality rate, race data and urban/rural designation for each county. The hosital obstetric data is a spreadsheet that has each county listed and whether or not they have a hospital with an obstetric bed in the county. This sheet was created by hand, using the 2014 hospital obstetric reports. 
  * Prenatal data is then added to the sheet that was just created.

04-output:

  * This is where the actual calculations are run. We combine the urban and rural counties together and figure out mortality and prenatal rates, as well as race data, for each. We do the same for counties that have hospitals that have obstetric beds to those that don't. The final files are put in the input directory.
    * NOTE: There was an issue with calculating prenatal rates for counties with OB hospitals v. counties without these hospitals. This incorrect prenatal data is the output/mortality-prenatal-ob-hospitals-14-population-split.csv file. To rectify this, the prenatal rate was calculated manually using Excel. This correct data is in the output/prenatal-ob-hospitals-excel.xlsx file.

## Data

#### Texas maternal mortality task force
The task force studied maternality mortality across the state and put together a [report](https://www.dshs.texas.gov/mch/maternal_mortality_and_morbidity.shtm). Data is current as of 2014. We were also emailed a new report in October 2017 that includes 2012-15 mortality rates, as well as causes of death and more.

#### Texas vital statistics
Every year, Texas DSHS puts out [vital statistics](https://www.dshs.texas.gov/chs/vstat/annrpts.shtm), which includes maternal mortality rates, prenatal care numbers, etc. Data is current as of 2014. Additionally, we were emailed some 2015 data, including prenatal rates.

#### County designations
Texas DSHS [classifies counties](https://www.dshs.texas.gov/chs/hprc/counties.shtm) based on whether they are rural or urban and border or non-border. Data is current as of 2013.

#### Hospital obstetric reports
Every year, DSHS puts out a hospital obstetric report, which tracks how many obstetric beds each hospital in Texas has. The 2014 report was emailed to us.

#### PRAMS
This [survey](https://www.dshs.texas.gov/mch/PRAMS.aspx) gives us postpartum care numbers for Texas. Data is current as of 2014.

#### American Fact Finder
This [tool](https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml) from the US Census Bureau provides demographic data. We're using 2015 ACS 5-year estimates.


## Associated Reporters

- Marissa Evans <mevans@texastribune.org>
- Chris Essig <cessig@texastribune.org>
- Benjamin Din <bdin@texastribune.org>
