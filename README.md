# Analysis of maternal mortality data

This repo contains data, code and explanations supporting the Texas Tribune's maternal mortality project.

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

## Data

#### Texas maternal mortality task force
The task force studied maternality mortality across the state and put together a [report](https://www.dshs.texas.gov/mch/maternal_mortality_and_morbidity.shtm). Data is current as of 2014.

#### Texas vital statistics
Every year, Texas DSHS puts out [vital statistics](https://www.dshs.texas.gov/chs/vstat/annrpts.shtm), which includes maternal mortality rates, prenatal care numbers, etc. Data is current as of 2014.

#### County designations
Texas DSHS [classifies counties](https://www.dshs.texas.gov/chs/hprc/counties.shtm) based on whether they are rural or urban and border or non-border. Data is current as of 2013.

#### PRAMS
This [survey](https://www.dshs.texas.gov/mch/PRAMS.aspx) gives us postpartum care numbers for Texas. Data is current as of 2014.

#### American Fact Finder
This [tool](https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml) from the US Census Bureau provides demographic data. We're using 2015 ACS 5-year estimates.


## Associated Reporters

- Marissa Evans <mevans@texastribune.org>
- Chris Essig <cessig@texastribune.org>
- Benjamin Din <bdin@texastribune.org>
