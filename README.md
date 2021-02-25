# UChicago MSCA 31012 (Data Engineering Platforms for Analytics)
# Final Project: COVID-19 Mask Use Analysis

## ‘Data’ Folder
### ‘aggregated by county.csv’
* source: ‘covid by county.csv’, ‘mask use by county.csv’, ‘population by county.csv’
* description: joined by County Key

### ‘aggregated by state.csv’
* source: ‘covid by state.csv’, ‘mask use by state.csv’, ‘population by state.csv’, ‘health insurance by state.csv’, ‘hospital utilization by state.csv’
* description: joined by State Key

### ‘covid by county.csv’ & ‘covid by state.csv’
* source: https://github.com/nytimes/covid-19-data/blob/master/live/us-states.csv
* description: Cumulative coronavirus cases and deaths for each geography up to Nov 13th. The counts include both laboratory confirmed and probable cases using criteria developed by states and the federal government.  

### ‘health insurance by state.csv’
* source: https://www.census.gov/data/tables/time-series/demo/income-poverty/cps-hi/hi-01.html
* description: Health Insurance Coverage Status and Type of Coverage by State All Persons: 2008 to 2019. Type of coverage includes private (employer-based and direct-purchase) and public (Medicaid, Medicare,etc).  

### ‘hospital utilization by state.csv’    
* source: https://www.census.gov/data/tables/time-series/demo/popest/2010s-counties-total.html
* description: Estimated hospital utilization data are available for the U.S. states, and territories. This data includes total inpatient bed, total ICU beds, percent of inpatient bed utilization, and percent of inpatients with covid, etc. 

### ‘mask use by county.csv’ & ‘mask use by state.csv’#
* source: https://github.com/nytimes/covid-19-data/tree/master/mask-use
* description: Estimates of mask usage in the United States. This data comes from a large number of interviews conducted online by the global data and survey firm Dynata at the request of The New York Times.  

### ‘population by county.csv’ & ‘population by state.csv’
* source: https://www.census.gov/data/tables/time-series/demo/popest/2010s-counties-total.html
* description: Annual Estimates of the Resident Population for Counties in the United States: April 1, 2010 to July 1, 2019. 


## ‘Data Processing_Python’ Folder
### ‘data_processing_county_level.html’ & ‘data_processing_state_level.html’
* Used libraries like pandas, numpy
* Drop columns with many NAN
* Drop duplicated columns and rows
* Add calculated fields useful for modeling 
* Merged the datasets

## ‘Data Analysis_R’ Folder
Inputs
●    Imports cleaned aggregate data from python script: ‘State_Data_Variables.csv’

Outputs
●    ‘Principle Component Analysis.html’
●    ‘Principle Component Analysis.Rmd’
●    ‘State_Rankings.csv’
●    ‘Scaled_State_Data_for_MFA.csv’

## ‘Data Visualization_Tableau’ Folder
### ‘County.twb’
* The dashboard ‘By County’ can be filter by state_county (default shows top 10 counties that have the highest deaths) and is made up of 2 sheets
* ‘Death Number (size) & Rate (color)’: Map based on Longitude (generated) and Latitude (generated).  Color shows sum of Death Rate.  Size shows sum of Deaths.  The marks are labeled by sum of Deaths and sum of Death Rate.  Details are shown for State1 and County. The data is filtered on State_County, which keeps 10 of 3,131 members. The view is filtered on County, which keeps multiple members.
* ‘Mask Use: Never, Rarely, Sometimes, Frequently, Always’: Always, Frequently, Sometimes, Rarely and Never for each State_County.  Color shows details about Always, Frequently, Sometimes, Rarely and Never.  The marks are labeled by Always, Frequently, Sometimes, Rarely and Never. The view is filtered on State_County, which keeps 10 of 3,131 members.

### ‘State.twb’
* The dashboard ‘By State’ can be filtered by state and is made up of 4 sheets
* ‘Death Number (size) & Rate (color)’: Map based on Longitude (generated) and Latitude (generated).  Color shows sum of Death Rate.  Size shows sum of Deaths.  The marks are labeled by sum of Deaths and sum of Death Rate.  Details are shown for State. The view is filtered on State, which keeps 49 of 49 members.
* ‘Mask Use: Never, Rarely, Sometimes, Frequently, Always (Order by 'Always' DESC)’: Always, Frequently, Sometimes, Rarely and Never for each State.  Color shows details about Always, Frequently, Sometimes, Rarely and Never.  The marks are labeled by Always, Frequently, Sometimes, Rarely and Never. The view is filtered on State, which keeps 49 of 49 members.
* ‘Insurance Coverage Number (size) & Rate (color)’: State, sum of Any coverage and sum of Insurance Coverage Rate.  Color shows sum of Insurance Coverage Rate.  Size shows sum of Any coverage.  The marks are labeled by State, sum of Any coverage and sum of Insurance Coverage Rate. The view is filtered on State, which keeps 49 of 49 members.
* ‘Pct Hospital Utilization (Order by 'Pct Inpatients With Covid' DESC)’: Pct Icu Bed Utilization, Pct Inpatient Bed Utilization and Pct Inpatients With Covid for each State.  Color shows details about Pct Icu Bed Utilization, Pct Inpatient Bed Utilization and Pct Inpatients With Covid.  The marks are labeled by Pct Icu Bed Utilization, Pct Inpatient Bed Utilization and Pct Inpatients With Covid. The view is filtered on State, which keeps 49 of 49 members. 
