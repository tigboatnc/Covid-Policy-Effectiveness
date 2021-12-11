# Covid Policy



__Hypothesis 1__ :  Similar show similar 


## State Profiling Data 
|Dataset Description|Dataframe|Merge ID|
|-|-|-|
|Census|censusDF|__`CEN`__|
|Case Peak |case_peakDF| __`CP`__ |
|Obesity |obesityDF| __`OB`__ |
|Fire Department |fireDF| __`FD`__ |
|State Party (Political Affiliation) |statePartyDF| __`SP`__ |
|Hospital Beds and who operates them |hospitalBedDF| __`HB`__ |




## State Wise Case Data 
[Source](https://data.cdc.gov/Case-Surveillance/United-States-COVID-19-Cases-and-Deaths-by-State-o/9mfq-cb36)








## Notebook Description 
|__Notebook__|__Date Created__|__Description__|__context__|__output__|__input__|__status__|
|-|-|-|-|-|-|-|
|[vaccine-data-process](./notebooks/vaccine-data.ipynb)|2 December 2022|New Vaccine data found late in the project, inclusion notebook||[state_vac](./outputs/state_vac.csv)|[state_vac_og]('./dataset/us_vac_og.csv')|
|[case exploration](./notebooks/case-exploration.ipynb)|22 November 2021|Explores the CDC case dataset and finds problems in it if existing|`EDA` `policy effective metric`|||_Does Not Work_|
|[case visualisation and metrification](./notebooks/case-visualisation-metrification.ipynb)|22 November 2021|Visualising case data and deciding to create a noise free interpolation using multiple filtering and interpolation techniques|`EDA` `policy effective metric`|[case_processed.csv](outputs/case_processed.csv)
|[finding peaks in case dataset](./notebooks/peaks-in-cases.ipynb)|22 November 2021|Visualising case data and deciding to create a noise free interpolation using multiple filtering and interpolation techniques|`EDA` `state profiling`|||_Working_|
|[policy exploration visual](./notebooks/policy-exploration-visual.ipynb)|24 November 2021|Exploring the policy dataset and creating a new dataset : __policy change dataset__ | `metric`|
|[policy exploration create](./notebooks/policy-exploration-create.ipynb)|24 November 2021|Exploring the policy dataset and creating a new dataset : __policy change dataset__ | `metric`|[processed_2020_statePolChange.csv](./outputs/processed_2020_statePolChange.csv),[processed_2021_statePolChange.csv](./outputs/processed_2021_statePolChange.csv)|
|[merger](./notebooks/merger.ipynb)|27 November 2021|Merging all of the collected and processed data into training data|-|[train.csv](./outputs/train.csv)|-|
|[merger-two](./notebooks/merger.ipynb)|27 November 2021|Add policy data to the state profile data|-|[train.csv](./outputs/train2_state.csv)|-|
|[K-Means](./notebooks/kmeans.ipynb)|-|-|-||-|
|[train finalisation](./notebooks/train-finalisation.ipynb)|2 December 2021|Create the final training DAta X + Y and save it into one csv |-|[`trainXY.csv`](./outputs/trainXY.csv)|-|
|[train1](./notebooks/train1.ipynb)|-|-|-|-|-|





