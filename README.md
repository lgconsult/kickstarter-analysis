# Kickstarting with Excel

## Overview of Project
We have recently been approached to perform data analysis for someone planning a Kickstarter campaign to raise funds for a theater production. The person wants to know the best strategies to ensure their campaign is successful. As a data analyst, we have decided to use Kickstarter fundraising campaign data to inform the client which is formatted as an .xlsx document. The data consists of the name and description of each campaign, the fundraising goals, and amounts pledged, the country where the campaign took place, and other categories that indicate the length of the campaign, and the type of initiative each campaign was raising money for. We will have to sort through these categories to find the most actionable data for our client.

### Purpose
The purpose of this analysis is to determine strategies that indicate a successful campaign and that can help our client's theater production fundraiser be successful.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
To analyze outcomes based on launch date, I created a pivot table where we can filter by campaign category and year, that displays the outcomes of theater campaigns by month of launch date. 
![Launch Date Process](https://github.com/lgconsult/kickstarter-analysis/blob/main/Lauch_process.png)
Through the following screen shot above, you can see the pivot table I created, filtering the chart by Parent Category and Year, adding date created to the rows (and selecting for months), and then adding outcomes to the columns and values buckets. I have filtered the data for theater campaigns and sorted my column labels to exclude live campaigns.

![Theater_Outcomes_vs_Launch](https://github.com/lgconsult/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png)
From the line graph produced above we can see the results. The months where the most successful campaigns were launched were in late spring to summer including May with 111 successful campaigns, June with 100, and July with 87. August had one more successful campaign than April, at 72 and 71 respectively, and considering April-August together, this indicates a seasonal trend. The winter and especially fall months see a significant decline of successful campaigns. Failed and canceled campaigns seem to follow a more steady trend throughout the year. Failed campaigns range between 52 and 31 a month, while canceled campaigns range from 7 to 1. 

I have experience making pivot tables, and I don't find them too difficult, while I don't usually end up with the correct chart on the first try, I always experiment with the data points in different fields to produce the correct result.

### Analysis of Outcomes Based on Goals
In order to create a chart that sorted outcomes based on goals I used a nested countifs formula that accounted for the range of dollar amount goal in 5000$ increments, and whether the campaign was successful, failed, or canceled.
![Goals Process](https://github.com/lgconsult/kickstarter-analysis/blob/main/goals_process.png)
Through the above screen shot you can see the nested countifs formula I created to produce the line graph. Each line of code in the chart subsititutes the dollar range and goal category for that given line. The rest of the code is standard so that it is all calculating from the same results. 

![Outcomes_vs_Goals](https://github.com/lgconsult/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png)
From the line graph created we can see the percentage of campaigns that were successful, failed, or canceled based on the dollar range of the goal. The percentage of successful campaigns seems much higher on the lower end of the scale, especially between less than 1000$ and 9999$, however the percentage of failed campaigns rises steeply between 4999$ and 9999$. These lines both then proceed erratically, failed campaigns as a percentage are their highest between the 20000 to 34999$ range, then steeply drop between 35000-39999, and then go to 100% at the 45000-49999 range and fall slightly above 50000$. The successful campaigns proceed in an inverse relationship to the failed campaigns but there does not seem to be a strong relationship to goal amount.

This exercise took me while to create the correct countifs formula. While I wasn't getting errors in my formula, I initially sorted the data on the workbook page at first, and then realized this did not calculate the correct results. I needed to nest all of the sorting into one function. I was able to find an explainer on countifs nested formulas from the excel help site, which allowed me to build my own and produce the graph above. Once I found the help site, it took me a few tries to add all of the different categories into the nested function.
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

The best time to launch a campaign is in the Spring and Summer between May and July.
The worst time to launch a campaign is in December.
- What can you conclude about the Outcomes based on Goals?

The best chance of success is to keep your goal below 9999$
The relationship between outcomes and goals is too sporadic beyond this dollar range to provide advice without looking at other factors.
- What are some limitations of this dataset?

The data only covers kickstarter campaigns and does not include fundraising campaigns that might have occured outside of this platform.
- What are some other possible tables and/or graphs that we could create?

I would next look to create a table that compares the number of donors to the overall success rate, and also one that displays the number of donors in each goal range. This will help determine the relationship between outcomes and goals. While outcomes and launch date seem to be correlated based on the month of the year, there is less of a clear relationship between outcomes and goals.
