# Kickstarting with Excel

## Overview of Project
Creating an analysis to help Louise see how the different campaigns did based on their launch date and funding goals. 

### Purpose
We analyzing specifically on two outcomes. One is the outcome based on the Launch Date a nd the other will be back on goals. Outcomes based on Launch Date will tell us what month we launch the threatre projects will be the most successful. Outcomes based on Goals will tell us what percentage of plays based on the goals set were the most successful.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
In the analysis of outcomes based on Launch Date, we focused on theatre projects. In the line graph below, there were the most successful projects and the most failed project that were started in May and the most canceled project were started in January. There were the least amount of successful project started in December, the least amount of failed project that were started in November and the least amount of canceled projects were started in October. Based on this, if you want to have the most amount of sucessful and failed projects, you would want to start in May and if you want the least amount of cancelled, you would start the project in October. 

![Theater_Outcomes_vs_Launch](/Resources/Theater_Outcomes_vs_Launch.png)

This line graph is based on a pivot table created using the Kickstarter data provided. First, we created a column for Date Created Conversion using the formula "=(((J1/60)/60)/24)+DATE(1970,1,1)"; Column J is the "launched_at" date. This formula will help us figure out how many days, minutes, and second that will need to be added to January 1, 1970 to calculate the actual campaign launch date. Then, we created another column for Years based on the column we just calculated for the Date Created Conversion, we calculated the year using the formula "=year(S1)". Using this data, we created a pivot table with "Parent Category" and "Years" under Filters, "Date Created Conversion" under Rows, "outcomes" under columns and "Count of outcomes" under Values as shown belown. 

![Launch_Date_Outcomes_Pivot](/Backup/Launch_Date_Outcomes_Pivot.png)

### Analysis of Outcomes Based on Goals
The line graph below shows the percentage of successful, failed, and canceled based on the different ranges of goals. There were no canceled plays, the highest percentage of successful was when the goals were set to less than $1,000, and the highest percentage of fail plays were when the goals were sent in the range of $40,000 t0 $49,999. Thes lowest percentage of sucessful plays were when the goals were set $45,000 and $49,999 and the lowest percent of failed plays were when goals were set to less than $1000. If you want the highest percentage of successful plays and the lowest percentage of failed plays, then the play should have a goal of less than $1,000 and the lowest percentage of successful and highest percentage of failed plays should set a goal with a range of $45,000 to $49,999. 

![Outcomes_vs_Goals](/Resources/Outcomes_vs_Goals.png)

In order to calculate the percentage, the count of number of successful, number of failed and number of canceled using the following formula "=COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,"<1000",Kickstarter!$R:$R,"plays")", and "=COUNTIFS(Kickstarter!$F:$F,"canceled",Kickstarter!$D:$D,"<100",Kickstarter!$R:$R,"plays")" respectively. The formula will have to updated for the appropriate goal ranges. Once all the the number of successful, failed and canceled have been updated, under the total projects column, the formula "=SUM(B2:D2)" will be used to add up all the columns. The percentage columns will be calculated by Number of Successful/Failed/Canceled divided by Total Projects. 

![Goals_Outcome_Chart](/Backup/Goals_Outcome_Chart.png)

### Challenges and Difficulties Encountered
In order to separate the Category and Subcategory column into the Parent Category and Subcategory using Text to Column, the columns needed will have to be empty or excel will have a error message asking if you want to replace the data that are in those columns as shown below. 

![Text_to_Column_error](/Backup/Text_to_Column_error.png)

When creating the countifs formula, the range of the goals will need to be carefully set as it may include different more than it should and will affect the total projects amounts. This would cause the data to be incorrect and would also cause the percentages to be incorrect. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

Based on successful amount of theatre projects, the best three months to launch a theatre project is in May, June, and July, as the amount of successful projects were the highest in these three months. The worst months to launch a theatre project is in December, November and tied at third was January and March since the lowest successful amounts were launched in these months respectively. If only looking at the amount of canceled projects, the best months to launch projects would be in November, January and March as there were the least amount of failed projects. Although, there were the most successful and most failed outcomes in May, I would lauch the most projects in May and the least in December based on the line graph. 

- What can you conclude about the Outcomes based on Goals?

When the goals were set higher than $45,000 and between $25,000 to $34,999, there were the most amount of failed plays project. There were the most successful play when goals were set under $4,999 and between $35,000 to $44,999. If you want the plays to be successful, the goals should be set lower than $4,999. 

- What are some limitations of this dataset?

The dataset only goes from 2009 to 2017; it is not up to date or current and could affect the conclusion made today as the interest have changed. The categories for the data are more art centric and should include more genres. 

- What are some other possible tables and/or graphs that we could create?

We could create a line graph to see the trends throughout all the years of different outcomes and see which years had the most amount of successful, failed and canceled film & video. A bar graph showing the different outcomes for each of the different countries to see how each of the different countries did. A line graph to show all the different categories for a specific country and see how successful or failed or canceled each of the categories are doing. 
