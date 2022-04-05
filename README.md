# W210-FinalProject:  Synthetic Capstone project  

# Defense Attorney Advisory Tool for Equity (DAATE)
 
# Team: Jackie Nichols, Hao Wu, Song Park, Robert Ling
W210.4 Wednesday @4:00pmPT 2022

## Summary

This repo contains work performed by Jackie Nichols, Hao Wu, Song Park, and Robert Link for our capstone project in W210 at UC Berkeley.  

## Abstract

There have been recent stories surrounding the challenges within the criminal justice system that have been brought to light as a result of greater access to data. For example, some recent research has shown that African Americans face harsher treatment than whites in the criminal justice system. Minority groups in general tend to face harsher sentencing including longer prison sentences. Equity in the criminal justice system is in question and there is data that help provide greater transparency around the criminal justice system. Drawing inspiration from the following 

- the award-winning "Bias on the Bench" 2016 series from the Sarasota Herald-Tribune, (http://projects.heraldtribune.com/bias/) 
- The story of Walter McMillian, who, with the help of Bryan Stevenson a defense attorney, appealed his murder conviction as depicted in the movie Just Mercy
- The team at American Equity and Justice Group whose goal is to provide transparency into the WA criminal justice system


### Introduction

Defense Attorney Advisory Tool for Equity (DAATE) is motivated by the desire to explore the inequity in the US criminal justice system. A desire that was realized after becoming aware of research that has shown that approximately five times more Black Americans are being incarcerated than that of White Americans and that Black Americans face harsher treatment than White Americans in the US criminal justice system; with as much as 19.1% longer sentences than White offenders.

The goal of DAATE is to provide greater transparency into sentencing of Black and White Americans in the United States (US) criminal justice system. Leveraging the Florida Department of Corrections data from 2004-2016, DAATE is intended to be an advisory tool for defense attorneys to gain additional insight about potential inequity in the Florida legal system through simple yet impactful analytics. In addition to analytics, DAATE provides statistical guidelines for evidence of sentencing bias through exploring causality, as well as providing easily interpretable, statistical model-based sentence time predictions. This is accomplished by identifying potential bias in sentences for particular crimes based on a defendants race using various data science techniques.

DAATE is intended to be an advisory tool for defense attorneys to gain additional insight about potential inequity in sentencing, and to aid in the attorney's case preparation to represent and to seek fair and equal treatment for their client.

### Mission

To empower legal professionals to realize fairness and equity for their clients by providing transparency into sentencing in the US criminal justice system using data science techniques.

### MVP Architecture

The DAATE MVP leverages Microsoft Azure Cloud infrastructure to host the synchronous pipeline and data ingestion and processing. The Florida Department of Corrections (DOC) data from 2004-2016 was used and stored in this infrastructure. This backend is used for processing the DOC data through various modelling techniques and is built for high scalability and modularity. The data and modelling results are accessed by Tableau and served on this site via GitHub pages. The pipeline and process consists of multiple stages:

- Ingest the Florida Department of Corrections (DOC) data from 2004-2016 to Azure Blob Storage
- Leverage Databricks to move to Azure SQL DB table
- Elastic search, Azure ML and Python to perform EDA and create MVP Azure SQL table
- Leverage Bias and Disparity Detection API via Docker container updating MPV Azure SQL table
- Perform multi-modelling in Azure ML and Python updating the MPV Azure SQL table
- Tableau is used to access MVP Azure SQL table to create dashboard
- GitHub pages are used to serve up the DAATE website



### Our Results

For a look at our MVP results, please visit our website at https://mspuckit.github.io/DAATE/

## Navigating the Files in this Repository

Below is a list of directories found in this repository along with a brief description.

|Directory | Description |
|:---------|:------------|
|[`MODELS`](https://github.com/mspuckit/DAATE/tree/main/Models)|Contains all of the notebooks for the various models|
|[`DELIVERABLES`](https://github.com/mspuckit/DAATE/tree/main/Deliverables)|Contains the final deliverables for this project|
|[`DATA`](https://github.com/mspuckit/DAATE/tree/main/data/sentencing)|Scrubbed data used|
|[`EDA & DATA CLEANSING`](https://github.com/mspuckit/DAATE/tree/main/EDA%20%26%20Data%20Cleansing)|Contains notebooks for EDA & data cleansing|
|[`ASSETS`](https://github.com/mspuckit/DAATE/tree/main/assets)| Website specific files|

Below is a list of notable files found in this repository along with a brief description.

|File | Description |
|:----|:------------|
WEB SITE
|[`index.html`](https://github.com/mspuckit/DAATE/blob/main/index.html)|Home page for DAATE|
|[`acknowledgment.html`](https://github.com/mspuckit/DAATE/blob/main/acknowledgement.html)|Acknowledgement page for DAATE.|
|[`arch-details.html`](https://github.com/mspuckit/DAATE/blob/main/arch-details.html)|Architecture details page for DAATE.|
|[`data-details.html`](https://github.com/mspuckit/DAATE/blob/main/data-details.html)|Data details page for DAATE.|
|[`model-details.html`](https://github.com/mspuckit/DAATE/blob/main/model-details.html)|Model details page for DAATE.|
|[`results-details.html`](https://github.com/mspuckit/DAATE/blob/main/results-details.html)|Results details page for DAATE.|
|[`whatsnext-details.html`](https://github.com/mspuckit/DAATE/blob/main/whatsnext-details.html)|Next Steps details page for DAATE.|
|[`terms.html`](https://github.com/mspuckit/DAATE/blob/main/terms.html)|Terms of Use page for DAATE.|
|[`privacy.html`](https://github.com/mspuckit/DAATE/blob/main/privacy.html)|Privacy Policy for DAATE.|
|[`tryit_bdde.html`](https://github.com/mspuckit/DAATE/blob/main/tryit_bdde.html)|BDDE Dashboard results for DAATE.|
|[`tryit_caselist.html`](https://github.com/mspuckit/DAATE/blob/main/tryit_caselist.html)|Judge case list for DAATE.|
|[`tryit_modelresults.html`](https://github.com/mspuckit/DAATE/blob/main/tryit_modelresults.html)|Model results for DAATE.|
|[`tryit_one.html`](https://github.com/mspuckit/DAATE/blob/main/tryit_one.html)|Analytic results for DAATE.|
MODEL ANALYSIS
|[`Notebooks/ModelAnalysis.ipynb`](https://github.com/mspuckit/DAATE/blob/main/Deliverables/DAATE_Pres1.pdf)|Analysis of dataset|
|[`Notebooks/aligning_and_balancing_multiple_datasets`](https://github.com/mspuckit/DAATE/blob/main/Deliverables/DAATE_Pres1.pdf)|Code file to balance datasets.|
|[`Notebooks/Causal_finalize.ipynb`](https://github.com/mspuckit/DAATE/blob/main/Models/Causal_finalize.ipynb)|Causal Inference result generation|
|[`Notebooks/regression_circuitsXcrimes.ipynb`](https://github.com/mspuckit/DAATE/blob/main/Models/regression_circuitsXcrimes.ipynb)|Predictions Circuit Level|
|[`Notebooks/regression_withJudge.ipynb`](https://github.com/mspuckit/DAATE/blob/main/Models/regression_withJudge.ipynb)|Predictions Judge Level|
DELIVERABLES
|[`deliverables/DAATE_Pres1.PDF`](https://github.com/mspuckit/DAATE/blob/main/Deliverables/DAATE_Pres1.pdf)| PDF of presentation 1.|
|[`deliverables/DAATE_Pres2.PDF`](https://github.com/mspuckit/DAATE/blob/main/Deliverables/DAATE_Pres2.pdf)| PDF of presentation 2.|
|[`deliverables/DAATE_Pres3.PDF`](https://github.com/mspuckit/DAATE/blob/main/Deliverables/DAATE_Pres1.pdf)| PDF of presentation 3.|
EDA & DATA CLEANSING
|[`Data_Cleaning_Outliers_ZScore.ipynb`](https://github.com/mspuckit/DAATE/blob/main/EDA%20%26%20Data%20Cleansing/Data_Cleaning_Outliers_ZScore.ipynb)| Data cleansing process & removing outliers| 
|[`Initial_EDA_sentencing.ipynb`](https://github.com/mspuckit/DAATE/blob/main/EDA%20%26%20Data%20Cleansing/Initial_EDA_sentencing.ipynb)| Data Exploration & Analysis|
|[`JudgeCleanups.ipynb`](https://github.com/mspuckit/DAATE/blob/main/Models/JudgeCleanups.ipynb)| Messy Judge Name Cleanups|
REFERENCES
|[`References.pdf`](https://github.com/mspuckit/DAATE/blob/main/assets/resources/References.pdf)| A list of references used throughout the DAATE MVP journey| 



