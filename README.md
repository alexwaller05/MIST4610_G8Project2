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
To prepare the data for analysis, the focus was narrowed to the seven major felonies as defined by the FBI/NYS; this involved using a CASE WHEN statement on the Ofns Desc field to categorize arrests accordingly. 

For the first question concerning age analysis (Q1), data cleaning was performed to remove records with invalid age entries, such as 'Unknown', '200+', or birth years, ensuring accurate age group comparisons. 

For the second question regarding trend analysis (Q2), the data was filtered to include only records from 2020 onwards to analyze recent trends and generate a relevant forecast. 

Finally, aggregation was applied by grouping the data by month, felony type, and age group as needed for visualization and further analysis.

## Question 1: How does the distribution of major felonies differ across age groups?
### Why is this question important?
This question is important because it helps to understand the relationship between age and specific types of major felonies, allowing for the identification of age groups that are disproportionately involved in certain crimes. 

* Inform Policy and Resource Allocation: Understanding these patterns is crucial for making targeted policy decisions and allocating resources effectively. This includes enabling law enforcement and community organizations to:
  * Focus resources on age groups with higher crime rates.
  * Implement tailored youth intervention programs (e.g., school-based initiatives, mentorship).
  * Strengthen adult rehabilitation efforts to reduce recidivism and support reintegration.
  
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
* 45-64 have higher rates of burglary than other groups
* Older cohorts (65+) show minimal arrest counts across all categories
* Rape, murder & non-negligent manslaughter, and grand larceny of motor vehicles is low among all groups relative to the other major felonies

Based on the analysis of age and felony patterns, these findings imply that targeted youth outreach and intervention programs may be crucial for addressing robbery. Additionally, assault prevention and response strategies need a significant focus on the 25-64 age range, highlighting that different crime prevention strategies are likely necessary for different age demographics.


## Question 2: Which major felony arrests show the highest volumes or are increasing most significantly?
### Why is this question important?
This question is important because understanding how felony types are distributed across different age groups can help policymakers and law enforcement agencies tailor their crime prevention strategies. Ultimately, this analysis supports more efficient and specific approaches to reducing crime and recidivism.
* Anticipate crime trends: Allows agencies to forecast surges in violent offenses and prepare proactive strategies rather than reacting after the fact.
* Optimize resource allocation: Helps police departments assign patrols, detectives, and support services more effectively to the units and areas facing the greatest need.
* Guide policy and budgeting: Provides data-driven justification for funding specialized task forces or community resources focused on the highest-risk felony types.
* Measures policy effectiveness: Establishing trends and forecasts creates a performance baseline, making it possible to measure the impact of new initiatives by comparing actual outcomes against expected projections.

### Manipulations Applied to the Dataset for Question 2
* Mapped offense descriptions into 7 felony categories via `CASE WHEN`
* Aggregated monthly counts by Felony Category
* A multiplicative forecast model was used because the seasonal variations in felony arrests appeared to grow proportionally larger as the overall trend increased, suggesting seasonality has a multiplicative effect on the trend.
* Filtered data to 2020 and beyond (for forecast analysis)
  * The analysis focused on data from 2020 onwards because this period captured a notable dip and subsequent rise in felonies, while also providing more timely data for recent trend analysis, as illustrated in the graph below, which shows felony trends from 2006 to 2024.
  * <img width="773" alt="Screenshot 2025-04-27 at 1 35 06 PM" src="https://github.com/user-attachments/assets/0477d905-8d0a-4b9e-91a1-11cdf831248b" />



### Question 2 - Analysis Visualization
<img width="1289" alt="Screenshot 2025-04-27 at 1 36 14 PM" src="https://github.com/user-attachments/assets/4844c4e2-9986-44d1-8815-9315f67c180e" /> 


### Analysis Conclusion
Key findings from recent trends and the future outlook include:
* Highest Volume: Felony Assault consistently shows the highest arrest counts and is predicted to remain the highest in the near future.
* Significant Volume: Grand Larceny and Robbery follow Felony Assault, showing considerable volume alongside recent fluctuations or upward trends.
* Lower Volume/Stable: Arrests for Rape, Murder, and Burglary remain relatively low and exhibit flatter trends/forecasts compared to others.Felony Assault shows the highest predicted count

Based on this analysis, the implications suggest that Felony Assault requires sustained focus and resources from law enforcement due to its high volume and projected continuation. Monitoring trends in Grand Larceny and Robbery is crucial given their significant volume and potential for increases, while lower volume serious crimes like Murder and Rape still necessitate dedicated investigative resources.

## Conclusion 
Analysis of NYPD arrest data reveals distinct patterns based on both age and time.
* Age: Younger individuals (<24) are disproportionately arrested for Robbery, while middle-aged groups (25-64) show higher arrest rates for Felony Assault.
* Trends: Felony Assault represents the largest volume of major felony arrests and is projected to continue as the highest volume category. Grand Larceny and Robbery also remain significant concerns based on recent trends.

Ultimately, this data-driven analysis of NYPD arrest data underscores the essential role such investigations play in modern law enforcement and policy-making. Understanding the nuances of crime patterns, both across different age demographics and evolving over time, is critical for the effective allocation of resources, the design of targeted crime prevention strategies tailored to specific groups, and the implementation of proactive policing measures informed by emerging trends. By leveraging these insights, stakeholders can move towards more efficient and impactful approaches to public safety.
