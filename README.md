# Analysis of maternal mortality data

This repo contains data, code and explanations supporting the Texas Tribune's maternal mortality project.

## Installation

This project uses [pipenv](http://docs.pipenv.org/en/latest/) to manage dependencies. Once you have that set up, install the dependencies.

```sh
pipenv install --three
```

Run this if you want to active extentions:

```sh
jupyter contrib nbextension install --user
```

```sh
jupyter nbextensions_configurator enable --user
```

Then you can run Jupyter notebooks.

```sh
pipenv run jupyter notebook
```

## Data

#### State Comptroller's Fired With Cause dataset
A listing of all employees who have been fired with cause by the state. Each row represents a terminated employment, meaning if someone has been fired multiple times, they will be represented by multiple rows.

#### State Comptroller Payroll database
This is what the Tribune uses to update the [Salaries Explorer](https://salaries.texastribune.org/state-comptroller-payroll/). Because this data is requested from the same source as the fired with cause data, they both contain common identifiers.

## Associated Reporters

- Marissa Evans <mevans@texastribune.org>
- Chris Essig <cessig@texastribune.org>
- Benjamin Din <bdin@texastribune.org>
