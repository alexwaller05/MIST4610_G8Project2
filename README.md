# MIST 4610 Group Project 2 - Group 8

## Group Name: 21482 Group 8

## Team Members:

1. Ryan Buckley [@rwb11687](https://www.github.com/rwb11687)
2. Suba Senthil [@subasen25](https://github.com/subasen25)
3. Ayush Desai [@Ayush-des](https://github.com/Ayush-des)
4. Mithun Fernandez [@MFernandez2005](https://www.github.com/MFernandez2005)
5. Alex Waller [@alexwaller05](https://www.github.com/alexwaller05)

## Dataset Description:
### Basic features & description:
The dataset provides comprehensive records of each arrest made by the NYPD from 2006 to 2024, totaling nearly 5,986,025 rows of entries across 19 columns. Sourced from data.gov, a public information repository, this dataset captures key details such as the perpetrator’s demographic information, the type of offense committed, and the location of each arrest. It offers valuable insights for analyzing crime trends, demographic patterns, and law enforcement activity across New York City over nearly two decades.

In Microsoft Excel, the data is viewable as individual rows that reference each recorded arrest and 19 columns that describe a different facet of the arrest (location, the perpetrator’s gender, etc.).

* For example, one row may contain the following information: 272061744 (arrest number/identifier), 7/29/2023 (arrest date), STRANGULATION 1ST (crime/has the perpetrator  committed this before?), 106 (offense identifier), FELONY ASSAULT (offense description), ...

### Why is this data important?
Analyzing this NYPD arrest data is important because it allows for the identification of significant crime trends over time. Furthermore, this analysis informs strategic resource allocation for law enforcement, such as focusing patrols based on crime hotspots or specific types of offenses, and provides data-driven insights crucial for shaping policy decisions and developing effective prevention programs. 


### Columns:
<img width="749" alt="Screenshot 2025-04-22 at 8 53 41 PM" src="https://github.com/user-attachments/assets/3f5ae25f-9da0-4a20-b7a9-66c279713ea8" />

<img width="808" alt="Screenshot 2025-04-22 at 8 53 59 PM" src="https://github.com/user-attachments/assets/42abe840-e3d6-40e5-b270-cf1aa6520039" />

## For our questions, we focused on the seven major felonies. But what are they, and why are they important?
According to NYC.gov, the seven major felonies are a category of crimes that vary by state. 
In the state of New York, this category that refer to murder and non-negligent manslaughter, forcible rape, robbery, felonious assault, burglary, grand larceny, and grand larceny auto.
According to the New York State Criminal Justice Services, the classification of the “seven major felonies” originates from the FBI’s Uniform Crime Reporting Program, which was established in 1930 to standardize crime statistics across the United States for consistent tracking and comparison of crime trends nationwide. Focusing on these specific felonies helps in analyzing trends and patterns in serious crime.

## Preparing the data 
To prepare the data for analysis, the focus was narrowed to the seven major felonies as defined by the FBI/NYS; this involved using a CASE WHEN statement on the Ofns Desc field to categorize arrests accordingly. For the first question concerning age analysis (Q1), data cleaning was performed to remove records with invalid age entries, such as 'Unknown', '200+', or birth years, ensuring accurate age group comparisons. For the second question regarding trend analysis (Q2), the data was filtered to include only records from 2020 onwards to analyze recent trends and generate a relevant forecast. Finally, aggregation was applied by grouping the data by month, felony type, and age group as needed for visualization and further analysis.

## Question 1: How does the distribution of major felonies differ across age groups?
### Why is this question important?
This question is important because it helps to understand the relationship between age and specific types of major felonies, allowing for the identification of age groups that are disproportionately involved in certain crimes. Understanding these patterns is crucial as it informs targeted policy decisions and resource allocation. For instance, this knowledge enables law enforcement and community organizations to more effectively allocate resources towards age groups exhibiting higher crime rates, implement tailored youth intervention programs (like school-based initiatives or mentorship opportunities), and strengthen adult rehabilitation efforts focused on reducing recidivism and supporting reintegration.
  
### Manipulations Applied to the Dataset for Question 1
* Aggregated monthly counts by the Seven Major Felony categories
* Removed extreme ages such as 200+, years (i.e. 1916), and “Unknown”
* The percentages on the chart represent the proportion of total arrests within each specific age group that corresponds to each particular major felony type.

### Question 1 - Analysis Visualization
<img width="1422" alt="image" src="https://github.com/user-attachments/assets/12cfc8ac-b326-43b0-a857-3034b40fdeca" />

### Analysis Conclusion
Insights from age group distribution:
* Younger arrestees (<18, 18-24) have higher rates of robbery compared to other groups
* Middle-aged groups (both 25-44 and 45-64) dominate felony assault counts
* 45-64 have have higher rates of burglary than other groups
* Older cohorts (65+) show minimal arrest counts across all categories
* Rape, murder & non-negligent manslaughter, and grand larceny of motor vehicles is low among all groups relative to the other major felonies
Based on the analysis of age and felony patterns, key findings reveal distinct correlations. Robbery arrests are proportionally higher among younger individuals (<18 and 18-24 years old), while Felony Assault arrests peak within the 25-44 age group and remain high for those aged 45-64. Burglary shows higher rates specifically within the 45-64 age group compared to others. Conversely, arrests for Rape, Murder, and Grand Larceny Auto are relatively low across all age groups compared to the other major felonies, and arrests are minimal across all categories for the 65+ age group. These findings imply that targeted youth outreach and intervention programs may be crucial for addressing robbery. Additionally, assault prevention and response strategies need a significant focus on the 25-64 age range, highlighting that different crime prevention strategies are likely necessary for different age demographics.


## Question 2: Which major felony arrests show the highest volumes or are increasing most significantly?
### Why is this question important?
This question is important because understanding how felony types are distributed across different age groups can help policymakers and law enforcement agencies tailor their crime prevention strategies. Ultimately, this analysis supports more efficient and specific approaches to reducing crime and recidivism.
* Anticipate crime trends: Allows agencies to forecast surges in violent offenses and prepare proactive strategies rather than reacting after the fact.
* Optimize resource allocation: Helps police departments assign patrols, detectives, and support services to the units most likely to see increased cases.
* Guide policy and budgeting: Provides data‑driven justification for funding specialized task forces or community resources focused on the highest‐risk felony types.
* Measures policy effectiveness: If a citywide violence‑prevention initiative comes into action and the actual assault arrests come in below your forecasted baseline, that gap quantifies how much crime the program likely prevented.

### Manipulations Applied to the Dataset for Question 2
* Mapped offense descriptions into 7 felony categories via `CASE WHEN`
* Filtered data to 2020 and beyond (for forecast analysis)
* Aggregated monthly counts by Felony Category

### Question 2 - Analysis Visualization
<img width="961" alt="Screenshot 2025-04-22 at 9 10 45 PM" src="https://github.com/user-attachments/assets/df987def-27e3-4817-aac3-86f09064568f" /> <br>
### Analysis Conclusion
Based on the one-year forecast:
* Felony Assault shows the highest predicted count
* Grand Larceny and Robbery follow closely and have similar rates to each other
* Other categories have relatively flat forecasts



