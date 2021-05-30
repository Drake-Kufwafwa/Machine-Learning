## COVID-19 REGRESSION ANALYSIS AND FUTURE PREDICTION USING REAL-TIME DATA

# Description: 

This project focuses on analysing covid trends and predicting future information based on available daily updates for the United States. Covid-19 has been really impactful to almost all of the world as a crisis. In response to this ongoing public health emergency, the Center for Systems Science and Engineering (CSSE) developed an online interactive dashboard to visualise and track reported cases of coronavirus disease 2019 (COVID-19) in real time. This is potentially meant as a tool to provide learners, researchers, public health authorities, and the general public with a user-friendly tool to track the outbreak as it unfolds. The data is fetched from an automated github dashboard. The dashboard automatically fetches daily updates as reported by the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). It is supported by ESRI Living Atlas Team and the Johns Hopkins University Applied Physics Lab (JHU APL). There are various datasets on the datasets, including US specific data, global data, etc. For this project, the data used is only the US data, with USA State level data. The repository can be accessed via the following link;

https://github.com/CSSEGISandData/COVID-19

The data is structured into daily csv files whi are named by date. It contains several variables, including state names and associated information. There also includes some daily feature variables.
Here is the documentation of the variables;

### File naming convention

MM-DD-YYYY.csv in UTC.

### Field description

##### Province_State - The name of the State within the USA.
##### Country_Region - The name of the Country (US).
##### Last_Update - The most recent date the file was pushed.
##### Lat - Latitude.
##### Long_ - Longitude.
##### Confirmed - Aggregated case count for the state.
##### Deaths - Aggregated death toll for the state.
##### Recovered - Aggregated Recovered case count for the state.
##### Active - Aggregated confirmed cases that have not been resolved (Active cases = total cases - total recovered - total deaths).
##### FIPS - Federal Information Processing Standards code that uniquely identifies counties within the USA.
##### Incident_Rate - cases per 100,000 persons.
##### Total_Test_Results - Total number of people who have been tested.
##### People_Hospitalized - Total number of people hospitalized. (Nullified on Aug 31, see Issue #3083)
##### Case_Fatality_Ratio - Number recorded deaths * 100/ Number confirmed cases.
##### UID - Unique Identifier for each row entry.
##### ISO3 - Officialy assigned country code identifiers.
##### Testing_Rate - Total test results per 100,000 persons. The "total test results" are equal to "Total test results (Positive + Negative)" from COVID Tracking Project.
##### Hospitalization_Rate - US Hospitalization Rate (%): = Total number hospitalized / Number cases. The "Total number hospitalized" is the "Hospitalized – Cumulative" count from COVID Tracking Project. The "hospitalization rate" and "Total number hospitalized" is only presented for those states which provide cumulative hospital data. 

### Update frequency
Once per day between 04:45 and 05:15 UTC.

### Project Specifics and Goals

For this project, I have combined the daily dataframes into one csv which will be fetching updates and appending them on a daily basis. The advantage with using the repository chosen is that the dataframe format is the same for all csv files. The csv used for analysis has one $Date$ variable and state names specified as $'State\_Name'$. The rows are made of data for each date. For analysis, I decided to select only the variables: $Confirmed, Deaths, Recovered$. I then created separate dataframes for each of the instances in order to analyze them separately. The final datasets I used are separately feature specific.

The project starts with some descriptive analysis, including summary statistics and some visualization of the quantitative variables. I will then proceed to use different algorithms to do regression and predict future trends. In this attempt, I will include visualizations such as scatterplots and line plots to show trends. I will pick the best model and use it as the most efficient model to predict daily covid trends. This will be done by selecting the model with the lowest error rate(highest accuracy rate). I hope to achieve a model that can actually be used in practice with a few further improvements.

### Progress and Plans

So far, I have managed to write a program that fetches and wrangles the data to achieve the desired format for analysis, as explained above. The steps and output are done in the notebook file: $data.ipynb$. The data csv files are then stored and imported in the second notebook: $covid_trends$. This second notebook focuses on discovering more about the data, including exploration and visualization. The data is straightforward and any missing data is automatically filled with zero values, so we'll not need to do any cleaning on our final dataset. While gaining insight into the data, I also proceed to split the data into both test and training sets. We want to make sure the training dataset is constant and we don't change it based on biases such as: when we further explore the data and notice trends that might influence our decision on the variables to include in training the data.

Going forward, I will proceed to implement training algorithms using dofferent methods. This should be straightforward given the stable data that I have. I will then output the respective error rates and select the model with the best accuracy to be our prediction model for future covid-19 trends. I will also write the algorithm function to be able to predict trends for each state as desired. This will be more significant and helpful than generalizing the model to the larger United States. I will then finalize the report for this project, and state any proposed advancements that I could not implement during the timeline of the project. Currently the notebooks $predictions$ and $reconcile$ are empty but they will contain the algorithms and reconcilation of global trends as I continue with the project.

### Conclusion

Given the current Covid-19 pandemic, the final tool outputted in this project is a step further in preparing for the future. It informs all types of unit that depend on such critical information , such as businesses, governments and researchers. Any help, criticization and comments on the project is welcome.