### Get It Done San Diego - Analysis

**NOTE:** The Jupyter notebooks probably will not load in GitHub. To view an 
individual notebook, please copy and paste its URL to [nbviewer](http://nbviewer.jupyter.org/) (or click on the Notebook links below)

#### Introduction
Using the "Get It Done San Diego" data available on the City of San Diego's open data portal, 
I examined factors that influenced the amount of time it takes to close a service request submitted 
to the City of San Diego. I wanted to 1) evaluate whether the City was distributing resources evenly 
across its neighborhoods, and 2) to create a model that would predict how long it would take to close 
any given service request.

#### File description
* **Analysis of factors influencing GID closure time.docx** - full project description, including methods, analyses, and results
* [Notebook1-Basic_Import_and_Cleaning](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook1-Basic_Import_and_Cleaning.ipynb) - describes data import and cleaning
* [Notebook2-Visualization](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook2-Visualization.ipynb) - visualizes data relating to how citizens chose to communicate their service needs to the City
* [Notebook3-Inferential_Statistics-Exploration](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook3-Inferential_Statistics-Exploration.ipynb) - contains code needed to export data tables for statistical analysis in MS Excel (no results are presented in this notebook; they can be found in the full project description instead)
* Machine Learning notebooks - the following three notebooks show the steps to model selection and fine-tuning. **WARNING:** Notebooks 4b and 4c take *many* hours to run. I plan to add pickled versions of the models so that you can load and explore the models on your own, but at the moment, please do not run this code.
    * [Notebook4a-Machine_Learning_Part1](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook4a-Machine_Learning_Part1.ipynb) - shows a comparison of two OOB models (a Random Forest Classifier and a Random Forest Regressor) when attempting to predict amount of time to close a request
    * [Notebook4b-Machine_Learning_Part2](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook4b-Machine_Learning_Part2.ipynb) - coarse tuning of model hyperparameters
    * [Notebook4c-Machine_Learning_Part3](https://nbviewer.jupyter.org/github/mwesterfield/Portfolio/blob/master/Get-It-Done-SD_Analysis/Notebook4c-Machine_Learning_Part3.ipynb) - fine tuning of model hyperparameters

#### Data
Zipped versions of all .csv files needed are in the `data/` subdirectory

#### Acknowledgements
* [Get it Done data](https://data.sandiego.gov/datasets/get-it-done-311/) came from the City of San Diego's [Open Data Portal](https://data.sandiego.gov/)
* Demographic data came from SANDAG's [Data Surfer portal](http://datasurfer.sandag.org/)
* Lat/Lon information was converted to zip codes using the [uszipcode](https://pypi.org/project/uszipcode/) package
* Population density information was obtained from [The Splitwise Blog](https://blog.splitwise.com/2014/01/06/free-us-population-density-and-unemployment-rate-by-zip-code/)
