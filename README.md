# Science and Technology in Chile: State funding between 1982 and 2022

Data analysis and visualization of Science and Technology projects that were given funding by the Chilean State in between 1982 and 2022.

@Claudio-AhumadaL, 2023

 ## General Information

The aim of this project is to run an analysis over the Science and Technology funding awarded by the Chilean State between the years 1982 to 2022. I expect to run descriptive and exploratory analysis over the data, which was collected from the [OBSERVA](observa.minciencia.gob.cl) platform of the chilean Ministry of Science. I expect to condense my findings in a dashboard made using Tableau for proper visualization.

 ## Scope

 This project is an exploratory endeavor with the global objective of understanding the route that has been taken by the chilean Ministry of Science to award funding to projects over the last 40 years. This analysis will serve to showcase the importance given by this State to different techonological and scientific areas, considering that this funding is one of the main sources of economic intake for science and techonology in this country.

  ### Goals

The main goal of this project is to get a clear overview of the direction that the chilean State's Ministry of Science has taken during the 40 year period available in the data (1982 to 2022). I expect to analyze categories such as Area of Knowledge, Type of Funding, Amounts and Region of Execution of the projects, as well as the relationship between these categories. This project will be considered succesful after performing descriptive and exploratory analysis over the data and then producing an interactive and informative dashboard to showcase the findings.

  ### Actions

This project could provide insights to interested groups, such as consulting companies or think thanks, that are interested in getting to know how the Chilean State has been assigning funding over the last 40 years for scientific and technological enterprises. It could also help the interested groups to evaluate if the funding has been aligned with the State's areas of interest (macroeconomically speaking), so they can counsel against or in favor of shifting the funding towards one or another area of interest. 

### Data

This project relies on data of the projects awarded through public support instruments for science, technology, knowledge and innovation, executed by the State agencies ANID, CORFO and the CTCI Undersecretariat. This data was taken from the [OBSERVA](observa.minciencia.gob.cl) platform of the chilean Ministry of Science and covers the period between 1982 and 2022.


### Analysis

 ## Initial definitions

The data will be cleaned and inspected using the python library Pandas. Statistical analysis will rely on the python libraries NumPy and SciPy. Exploratory visualization will be performed using the python library MatplotLib. The final dashboard will be constructed using Tableau Public.

This dataframe (called sf_data) has 2 types of columns, namely:

1. Categorical
2. Numerical

Restricting to consider only the columns of interest, the numerical category has just two columns ('Monto' column, the amount granted by the state, and the 'Año' column, the year). The Categorical category is divided in three narrower categories:

1. Categorical - State Agencies and Sub-Agencies ('Agencia' - Agency, 'Subdirección' - Sub-agency)
2. Categorical - Funding Instruments ('Instrumento' - Instrument, 'Contests' - Concursos, 'Tipo de Fondo' - Type of Funding)
3. Categorical - Awardees ('SectorEconomico' - Economic Sector, 'AreaConocimiento' - Area of Knowledge, 'TipoBeneficiario' - Type of Beneficiary, 'RegionEjecucion' - Region of Execution)

The rest of the columns are not included in the analysis.

 ## Descriptive analysis

 The descriptive analysis is divided in three parts. In this list, they are further divided by the methods used in each one of them:

 1. Inspection
    - General inspection using sf_data.head(), sf_data.dtypes, sf_data.describe(include='all')
    - NaN values inspection using sf_data.isnull().sum()
    - Inspection of value counts of Categorical columns using sf_data[column].value_counts()

 2. Modification
    - Unify RegionEjecucion values that correspond to the same region using sf_data['RegionEjecucion'].replace()

 3. Descriptive analysis
    - Bar Plot: Number of projects by State Agencies, Sub-agencies, Area of Knowledge, Economic Sector, Instrument, Region
 
 ## Exploratory analysis

 The exploratory analysis is divided in two parts:

 1. Visual exploratory analysis 
    - 'Monto' vs 'Año' Scatter plot and 'Monto' vs 'code of project' for the top 20 highest earner projects.

 2. Grouping-based exploratory analysis 
    - Grouped tables for Agency, Subagency, Instrument, Type of contest, year of execution, Economic Sector, Area of Knowledge, Type of Beneficiary and region of execution using sf_data.groupby([category]).Monto.mean()
    - Summarizing table with the max and min values for every category
    - Value counts of the year of execution, Instrument, Region of Execution and Area of Knowledge of the top 20 highest earner projects.
    - Grouped tables for Agency, Subagency, Instrument, Type of contest, year of execution, Area of Knowledge, Type of Beneficiary and region of execution using sf_data.groupby([category]).Monto.mean() over the top 20 highest earner projects
    - Summarizing table with the max and min values for every category for the top 20 highest earner projects.
    - Grouped tables for Agency, Subagency, Instrument, Type of contest, year of execution, Economic Sector, Area of Knowledge, Type of Beneficiary and region of execution using sf_data.groupby([category]).Monto.mean() over the last 5 years of the data (2017-2022)
    - Summarizing table with the max and min values for every category over the last 5 years of the data (2017-2022).

 ## Statistical analysis

 For the statistical analysis, the first step was to evaluate the columns of interest for normality and homocedasticity. The performed test were:

  1. Normality: Anderson-Darling test over 'Monto' and 'Year' column
  2. Homocedasticity: Levene's test over 'SectorEconomico' and 'Monto', over 'AreaConocimiento' and 'Monto' and over 'Region' and 'Monto'.




 ## Conclusions
