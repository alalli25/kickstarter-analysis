# Kickstarting with Excel
## Overview of Project
### Purpose
The purpose of this exercise was to review, and organize KickStarter data in order to provide analytical insights to a client, Louise, regarding how different campaigns fared in relation to their launch dates and their funding goals. Louise currently has a play, Fever, she is funding on KickStarter and it is very close to its fundraising goal. I was provided an array of KickStarter Campaign data which included key parameters, some of which are listed below:
- Name
- Goal & Pledged amount
- Outcome
- Launch Date & Deadline
- Percent Funded
- Category & SubCategory
## Analysis and Challenges
### Analysis of Outcomes Based on Launch Date
The goal of this analysis was to visualize Successful, Failed, and Canceled Theater campaigns by month. To perform this analysis, I first created a new column on the "KickStarter" data sheet and used the YEARS() formula *(Years formula screenshot)* to extract the year based on the Date Created Conversion date. I then organized a pivot table using the Parent Category & Years filter, Date Created Conversion columns, and outcome rows. The table is showing the count of outcomes. The table is also filtered for the Theater Parent Category, and the data excludes live campaigns *(Theater Outcome pivot)*. The end result is a lime graph illustrating the Theater Outcomes Based on Launch Date.

While creating this analysis, I faced difficulty grouping the Date Created Conversion by month. When I dragged the Date Created Conversion field into the row section of my pivot table, the data was formatted in a short date format (MM/DD/YYYY HH:MM). I was able to search google and find a solution to properly group dates by month. Please reference this link --> [Mac Pivot Table Grouping by Date](https://answers.microsoft.com/en-us/msoffice/forum/msoffice_excel-mso_mac/excel-for-mac-pivot-table-grouping-date-by-week/72eb6a07-9e11-47e4-8e47-975d9369d9d8)

***Years formula screeshot***
![](/Resources/Screenshots/Years_Formula.png)

***Theater Outcome pivot***
![](/Resources/Screenshots/Theater_Outcome_Pivot.png)



***FINAL TABLE: Theater Outcomes vs Launch***
![](/Resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
The goal of this analysis was to visualize the percent of play campaigns that were successful, failed, & canceled based on the goal requirement. Goal requirements were grouped in increments of $5,000 starting at less than $1,000 and ending at greater than $49,999. To perform this analysis, I created a table and used a series of COUNTIFS() formulas to count the number of successful, failed, and canceled play campaigns by goal parameter. I then calculated the percentage of each outcome vs the total. Being that there were 36 COUNTIFS() formulas I needed to create (3 campaign outcomes x 12 goal $ ranges), I understood this could lead to potential formula redundancies, errors and data tie-out issues. To overcome the redundancy of formulas I created two extra columns to specify the goal range, one for lower limit and one for upper limit, and an extra row to specify the outcome. My COUNTIFS() formula then became dynamic based on these parameters, which allowed me to copy and paste the formula without having to re-type a new formula in each required calculation cell *(Goals and Outcome formula)*. To overcome the potential tie-out issue, I created a check under each of the outcome totals. My check was comparing the total outcome type for plays and comparing that total against my calculation in the data table *(Tieout formula)*.

***Goals and Outcome formula***
![](/Resources/Screenshots/Goal_and_Outcome_Formula.png)

***Tieout formula***
![](/Resources/Screenshots/Tieout_Formula.png)

***FINAL TABLE: Play Outcomes vs Goals***
![](/Resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered
Challenges are captured in the analytics of outcomes above.
## Results

### What are two conclusions you can draw about the Outcomes based on Launch Date?
Conclusion 1: Theater campaigns have a greater chance of being successful than failed regardless of the launch month. 

Conclusion 2: Theater campaigns have the greatest chance of being successful if launched in late spring & early summer months, primarily May, June & July.

### What can you conclude about the Outcomes based on Goals?
Play campaigns that have a goal of less than $1,000 are more successful than any other play goal target range.

### What are some limitations of this dataset?
This dataset does not include information regarding the donators demographic, understanding the demographic would help identify additional marketing that should be done to obtain a higher funding amount. Additionally, this dataset does not include the speed at which it was funded. If we were aware of the funding cadence, it would allow us to identify how long a campaigned should be open for.

### What are some other possible tables and/or graphs that we could create?
Though the two analytical views are informative, this file is lacking statistical analysis. I would like to perform a regression analysis to determine the standard deviation & variance. I would also like to view a box plot for theater and plays to understand what values are outliers so they can be excluded from my analysis. 
