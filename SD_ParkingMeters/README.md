### An Analysis of Parking Meter Usage in San Diego

**NOTE:** If the Jupyter notebook does not load in GitHub, please copy and paste its URL to 
[nbviewer](http://nbviewer.jupyter.org/) (or click on the Notebook link below)

#### Introduction
In 2015, the City of San Diego adopted an ambitious Climate Action Plan (CAP) intended to reduce half of all greenhouse gas emissions by 2035. In order to meet this target, the City has proposed a number of strategies involving transportation, including strategies to reduce the amount of time drivers spend on unnecessary driving or idling in traffic. One approach recently taken in other cities is implementing dynamic parking meter pricing. The reasoning is that by analyzing driver demand at different locations and different times of day, it is possible to adjust parking meter rates so that a given block will have between 70-80% of its meters occupied every hour. This means that there is always an available parking spot for those willing to pay the rate (drivers do not need to circle the block fruitlessly), and that people unwilling to pay that rate may be instead encouraged to carpool, or use other means of transportation (e.g. mass transit).

Currently the City implements static pricing at its meters, although there are rate (and time limit) differences in different parts of the city. Given that the City collects (and makes available) all parking meter transactions, the goal of this project is to describe the current parking meter occupancy over the course of a 'typical' weekday, and to determine whether the available data is sufficient to indicate whether the City *should* move to a dynamic pricing strategy.

#### Method
Data was downloaded from the City of San Diego's [Open Data Portal](https://data.sandiego.gov/). Datasets used were 'treas_parking_payments_2019_datasd.csv' (all 2019 transactions-to-date ) and 'treas_parking_meters_loc_datasd.csv' (information about all parking meter locations).

Parking occupancy was calculated on a per-sub-area basis. A single sub-area, defined in the City meter locations file, includes all the parking meters on a (usually) one-block long stretch of street. For example, the '700 FIFTEENTH ST' sub-area includes the 12 parking meters on 7th Ave between F St and G St. Parking occupancy was calculated for every hour (between the hours of 8am - 8pm) for Tuesdays-Thursdays (in order to capture a typical weekday). Sub-area occupancy during a single hour was the number of spaces occupied by at least one vehicle during that hour divided by the total number of spaces available in that sub-area. Mean sub-area occupency was then calculated for ever hour over all days in the analysis period.

Details of the processing steps can be found in the [Data_Preparation](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook1-Basic_Import_and_Cleaning.ipynb)




#### Results
* **Analysis of factors influencing GID closure time.docx** - full project description, including methods, analyses, and results
* [Notebook1-Basic_Import_and_Cleaning](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook1-Basic_Import_and_Cleaning.ipynb) - describes data import and cleaning
* [Notebook2-Visualization](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook2-Visualization.ipynb) - visualizes data relating to how citizens chose to communicate their service needs to the City
* [Notebook3-Inferential_Statistics-Exploration](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook3-Inferential_Statistics-Exploration.ipynb) - contains code needed to export data tables for statistical analysis in MS Excel (no results are presented in this notebook; they can be found in the full project description instead)
* Machine Learning notebooks - the following three notebooks show the steps to model selection and fine-tuning. **WARNING:** Notebooks 4b and 4c take *many* hours to run. I plan to add pickled versions of the models so that you can load and explore the models on your own, but at the moment, please do not run this code.
    * [Notebook4a-Machine_Learning_Part1](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook4a-Machine_Learning_Part1.ipynb) - shows a comparison of two OOB models (a Random Forest Classifier and a Random Forest Regressor) when attempting to predict amount of time to close a request
    * [Notebook4b-Machine_Learning_Part2](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook4b-Machine_Learning_Part2.ipynb) - coarse tuning of model hyperparameters
    * [Notebook4c-Machine_Learning_Part3](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook4c-Machine_Learning_Part3.ipynb) - fine tuning of model hyperparameters

#### Data
All needed .csv files are in the `Data/` subdirectory (some files have been zipped because they were too large to upload)

#### Acknowledgements
* [Get it Done data](https://data.sandiego.gov/datasets/get-it-done-311/) came from the City of San Diego's [Open Data Portal](https://data.sandiego.gov/)
* Demographic data came from SANDAG's [Data Surfer portal](http://datasurfer.sandag.org/)
* Lat/Lon information was converted to zip codes using the [uszipcode](https://pypi.org/project/uszipcode/) package
* Population density information was obtained from [The Splitwise Blog](https://blog.splitwise.com/2014/01/06/free-us-population-density-and-unemployment-rate-by-zip-code/)
