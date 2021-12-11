# Studying Effectiveness of Covid Policies 

## Team Members 
- [Samarth Negi](https://github.com/tigboatnc)
- __Ally__
- __Chao Cao__
- __Jinhua Yang__


## BIG PICTURE 
The idea mainly evolved after reading [this]() article from CDC regarding effectiveness of policies 

FEATURES = Census(Demographic)+ Covid (Covid Specific Demographic) + Policy 

- - - - - - 

## Running Instructions 
1. __Locally__
    1. Clone the Repository.
    2. Set up the needed python dependencies using the env file [environment.yml](./extras/environment.yml)
        ```bash
        conda install -f environment.yml
        ```
2. Alternatively most notebooks can be viewed here on github. 

- - - - - - 
## Notebooks
The following table lists the notebooks in order of work done to shed light on some of the approaches taken. 


> For the sake of saving time, we are skipping most of the _data gathering_ and _source verification_ as it we feel it is trivial and would like to focus more on the feature engineering and data analytics part. A rough summary can be found [here](./extras/dataacq.md)

### STATE COVID PROFILING `X1`
|Notebook | `Stage` | `Author` | Description | 
|- |- |- |- |
|[Case Exploration](./notebooks/case-exploration.ipynb) |`EDA` |`Jinhua` |Getting the state wise covid data in and checking for continuity breaks  |
|[Case Visualisation and Metrification](./notebooks/case-visualisation-metrification.ipynb)|`Feature Engineering`|`Samarth` |Finding a good interpolation of daily cases as the raw cases were unusable for prediction |
|[Peaks in Cases](./notebooks/case-peaks-in-cases.ipynb) |`Feature Engineering` |`Jinhua` |The final feature (peak times) is calculated in this notebook and some visualisations are created for it -  [see the visualisations here](./outputs/peak_visualisations)|
|[Vaccination Data Processing](./notebooks/vaccine-data-process.ipynb) |`Feature Engineering` |`Chao`,`Ally`|This notebook deals with processing the vaccine data and creating a state classification metric from it. |

### STATE DEMOGRAPHIC PROFILING `X2`
|Notebook | `Stage` | `Author` | Description | 
|- |- |- |- |
|[Data Scraping](./notebooks/census_scraping.ipynb) | `Acquisition` | `Samarth` | This notebook scrapes the census website for one shot data gathering | 



### POLICY `X3`
|Notebook | `Stage` | `Author` | Description | 
|- |- |- |- |
|[Policy Exploration Visualized](./notebooks/policy-exploration-visual.ipynb)|`EDA`,`Feature Engineering` |`Ally` |-|
|[Policy Exploration Data Extraction](./notebooks/policy-exploration-visual.ipynb)|`Feature Engineering` |`Samarth` |This notebook creates the final outputs for the State Policy Data|

### METRICS FOR EFFECTIVENESS OF A POLICY `Y`

### MODEL TRAINING 
|Notebook | `Stage` | `Author` | Description | 
|- |- |- |- |
|[Hypothesis Testing : Demographic to State Covid Correlation](./notebooks/h1-kmeans.ipynb) | `Analytics` | `Chao` | This notebook tests the hypothesis : __A states covid response will be dependent on its demographic__ | 

### EXTRA - TOOLING 
|Notebook | `Stage` | `Author` | Description | 
|- |- |- |- |
|[State Code - Name Merging]() | `Stage` | `Author` | Description | 


- - - - - - 

## Conclusions 