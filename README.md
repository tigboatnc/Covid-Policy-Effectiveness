# Studying Effectiveness of Covid Policies 





## BIG PICTURE 
The idea mainly evolved after reading [this](https://coronavirus.jhu.edu/from-our-experts/evaluating-the-effectiveness-of-covid-19-policies-a-q-and-a-with-dr-elizabeth-stuart) article from __JHU__ regarding effectiveness of policies 

Some Interesting excerpts from the article.
> In terms of evaluation, one big picture challenge is that it’s hard to figure out what is the true impact of a policy and what is natural variation that you can’t attribute to a given policy

> __15 day delay__ : Covid-19 is much more dynamic, with a long lag time between exposure and outcomes such as hospitalization; this makes it hard to find the real impact of the policy.

There is a massive problem with judgemnet on what covid policies are effective. 
We aim to tackle this problem using this project and see if we can make any headway. 

We came to realise every state reacts differently to each policy so we split the project into 2 parts. 
1. State Classification 
2. Policy Effectiveness 

Project Split 

## Running Instructions 
1. __Locally__
    1. Clone the Repository.
    2. Set up the needed python dependencies using the env file [environment.yml](./extras/environment.yml)
        ```bash
        conda install -f environment.yml
        ```
2. Alternatively most notebooks can be viewed here on github. 
3. The Datasets are all present in the repo itself but some datasets are too big to download. They are added as api access cells, running which will download the datasets through and API endpoint and add it to the places needed to import to the notebooks. 



## APPROACH 
1. State Profiling : __To find similar states__
    - We collect state wise demographic data.
    - We try to find similarities between states using multiple methods. (K-means, Correlation etc.) 
2. Covid Profiling : __To find similar states in terms of covid__
    - We try to collect covid realated data for the USA and try to find similar states in terms of covid experience. 
    - We analyse covid data in the following time period = Start of Covid to Today.
    - Examples Cases data, Vaccination Data. 
2. Effectiveness Metric : __What is a good jugdge that a policy has been effective__
    - We try to decide what is a good metric to judge effectiveness of policy. 

__NOTEBOOK LAYOUT__
- For each our notebooks, we have a format. 
- First we try an operation for a state and then we generalize. 


## DATA GATHERING 
>  For the sake of saving time, we are skipping most of the _data gathering_ and _source verification_ as it we feel it is trivial and would like to focus more on the feature engineering and data analytics part. A source master list [here](./extras/dataacq.md) .All sources are verified to be good and valid.  

> Most of the data used in our datasets is api based which allows us to get fresh data and run them through our pipelines with just running the notebooks and replacing the existing data with fresh data. [see here](./extras/example_data_api.png)

## Notebooks
The following table lists the notebooks in order of work done to shed light on some of the approaches taken. 




### STATE COVID PROFILING 
|Serial|Notebook | Stage | Description | 
|- |- |-  |- |
|1|[Case Exploration](./notebooks/case-exploration.ipynb) |`EDA` |Getting the state wise covid data in and checking for continuity breaks  |
|2|[Case Visualisation and Metrification](./notebooks/case-visualisation-metrification.ipynb)|`Feature Engineering` |Finding a good interpolation of daily cases as the raw cases were unusable for prediction |
|3|[Peaks in Cases](./notebooks/case-peaks-in-cases.ipynb) |`Feature Engineering` |The final feature (peak times) is calculated in this notebook and some visualisations are created for it -  [see the visualisations here](./outputs/peak_visualisations)|
|4|[Vaccination Data Processing](./notebooks/vaccine-data-process.ipynb) |`Feature Engineering`,`dealing with missing data` |This notebook deals with processing the vaccine data and creating a state classification metric from it. |


### STATE DEMOGRAPHIC PROFILING 
|Serial|Notebook | Stage  | Description | 
|- |- |- |- |
|5|[Data Scraping](./notebooks/census_scraping.ipynb) | `Acquisition` | This notebook scrapes the census website for one shot data gathering | 



### POLICY 
|Serial|Notebook | Stage  | Description | 
|- |- |- |- |
|6|[Policy Exploration Visualized](./notebooks/policy-exploration-visual.ipynb)|`EDA`,`Feature Engineering`  |-|
<!-- |__Tooling__|[Policy Exploration Data Extraction](./notebooks/policy-exploration-visual.ipynb) |`Feature Engineering` |`NA` |This notebook creates the final outputs for the State Policy Data| -->

### METRICS FOR EFFECTIVENESS OF A POLICY 
|Serial|Notebook | Stage  | Description | 
|-|- |- |- |
|10|[Creating Metrics For Effectiveness (train-finalisation)](./notebooks/train-finalisation.ipynb) | `Plumbing` `Feature Engineering` | - | 


### MODELLING

|Serial|Notebook | Stage  | Description | 
|- |- |- |- |
|11|[Correlations in Census Data](./notebooks/census-correlations.ipynb) |`Analytics` |This notebook does internal corellation of census data. _not really a pertaining to the overarching idea but interesting_. Essentially  _obviousness is obvious_ |
|12|[Hypothesis Testing : Demographic to State Covid Correlation](./notebooks/h1-kmeans.ipynb) | `Analytics` ,`K-Means`,`Hypothesis Testing` | This notebook tests the hypothesis : __A states covid response will be dependent on its demographic__ | 
|13 |[MODEL 1](./notebooks/model1.ipynb)|`Analytics`,`Decision Trees` |Dependence analysis : [Results](./outputs/decision_reading.md)|


<!-- ### EXTRA - TOOLING 
|Serial|Notebook | `Stage` | `Author` | Description | 
|- |- |- |- |- |
|-1|[State Code - Name Merging]() | `Plumbing` | `Ally` | Description | 
|8|[merger1](./notebooks/merger.ipynb) | `Plumbing` | `Samarth` | Description | 
|9|[merger2](./notebooks/merger-two.ipynb) | `Plumbing` | `Samarth` | Description | 

 -->



## Conclusions and Insights

- We found some interesting correlations, specifically to covid however,
    - we saw that acceptance to vaccine is correlated to states higher education inclination.
    - When the second case peak hit in a state is correalted to the acceptance of that state to take the vaccine in the month of August. 
    - Many other such insights can be found on [this notebook](./notebooks/census-correlations.ipynb)
- We proved his hypothesis that states with similar demographics effect the covid experience of a state as can be seen through [these](./extras/comparision.png) clusterings.
- The decision trees (can be found [here](./outputs/))laid out some pretty good insights on what kind of policies effect what type of states. A summary can be found [here](./outputs/decision_reading.md)


## Highlights
- The project displayed creative ways of data acquisition as shown by Chao here [Automated Data Scraping from census site](./notebooks/census_scraping.ipynb).
- Exploring datasets like continuity of time series as shown by Jinhua helps later as it avoids unexpected outcomes 
- We feature engineered time series data into segments to get better data types 
- We used lots of default pandas functions as we found them better than writing code ourself (zscore apply or rolling). The standard pandas functions of data modification were extremely well thought out with parameters which felt very natural and even gave us ideas. 
- Pandas, Scikit-Learn, Selenium are very powerful libraries for data science and we made extensive use of those. 
- Over-Engineering is a real issue and we struggled with keeping the main goal in mind and were often derailed by the beauty of feature engineering. 




__Authors :__ 
- [Samarth Negi(me)](https://github.com/tigboatnc)
- [Chao Cao](https://github.com/HenryVarro666)
- [Jinhua Yang](https://github.com/SwagYangJH)
- Ally Mokoto

