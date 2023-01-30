# Data_Science_Ski_Ticket_Price_Predictor_Capstone

![image](https://user-images.githubusercontent.com/86930309/215365766-84e3206d-901c-4e3c-a0bd-01f923175d50.png)


## Context of Problem:
Big Mountain Resort recently installed a new chairlift. The chairlift increased their operating costs by $1,540,000 for the season. The resort's pricing strategy has been to charge a premium above the average price of resorts in its market segment. Big Mountain is probably not capitalizing on its facilities to its potential.Their current ticket price compared to the market average does not provide how important different facilities are to their guests. Their ticket price is undervalued. This hinders their business investment strategy.

## Criteria for Success:
Implementing a data-driven business strategy to create more revenue. Selecting the best possible value for their ticket price with data and information based upon other resorts in the United States that they compete with. Find ways to cut costs without reducing the ticket price. Or creating new facilities to justify a higher ticket price will create new success for Big Mountain.

## Scope of Success:
Utilizing an algorithm in python based upon other ski resort’s data and facilities in the United States to find the best possible ticket price that fits their market segment. This will also help them locate what facilities they need to add or remove to produce better revenue.

## Stakeholders:
-CEO          
-CTO       
-Data Science Team   
-National Forest Service     
-Alesha Eisen, Database Manager
-Board of Directors          
-Shareholders            
-Jimmy Blackburn, Director of Operations       
-President 
 
## Key Data Sources:
-skiResort.csv  

## Data Wrangling
There are 330 rows and 27 columns in the data originally. Our own resort, Big Mountain Resort was present and did not have any missing data. We know that the adult weekend price is our target feature to predict the ticket price. Prices for tickets in Montana are about equal for weekday and weekend and we have more data on weekend prices.

We dropped the 'fastEight' column because half the values were missing and the rest had a value of 0. This missing information does not help us to create a new ticket price or which facilites to improve. There was a resort created in 2019 that was dropped as a row because we do not know if the numbers were projected or actual at the time of data entry. It is hard to form a sound opinion based upon this type of data. 47 of the 328 columns, (14.32%) had no 'AdultWeekday' or 'AdultWeekend' data, so we deleted those 47 rows as well. Getting rid of this data can help us to form a better idea of how to help the client.

A few other issues with the data had to be sorted out to give us a clear idea on what we were looking at. An example of that was how we had a few more regions than states. This was because states were split across multiple regions, like the Sierra Nevadas. In section 2.6.2 we found what was missing from the data. 'fastEight' had the most missing variables (50.3%), followed by 'nightSkiing_ac' (43.3), 'AdultWeekday' (16.3), 'AdultWeekend'(15.4), and 'daysOpeLastYear' (15.4). Crystal Mountain, Washington was present in the data but another resort had the same name. Which was Crystal Mountain in Michigan on row 104. We know that they were completely different entities since they are located in different states with varying data. These features also gave us possible cause for concern: SkiableTerrain_ac and Snow Making_ac because values are clustered down the low end, trams and fastSixes has more variability but mostly 0.

Currently in the project we have pin pointed that adult weekend prices is the target feature to determine what the ticket price should be. We still have to suggest what that price should be in our market segment to the client. We still need to determine what facilities matter to customers the most so they are more likely to pay more for.

We have 277 rows and 25 columns left in the data.

## Key Findings
1. Big Mountain offers more facilities and skiable terrain than most other resorts in the United States.
2. In both of our models vertical drop, snow making, total chairs, fast quads, runs, longest run, trams and skiable terrain were the most important to guests.  
3. The resort is in the top portion of fast quads, runs, snow making, total chairs and vertical drop compared to other places.
4. Most other resorts like Big Sky do not have a tram.

## Recommendations:
1. I recommend that Big Mountain Resort increase their weekend price to $95.87 from $81.00. 
2. I would do an experiment for a certain amount of time and close just one ski run on the weekend to reduce maintenance cost.
3. Adding a run, 150 vertical feet and a new chairlift, (fast quad) is what I highly suggest the resort enact. This plan justifies a ticket price increase of $1.99 that improves revenue to $3,474,638 per year.
4. Creating more space to ski and a new chairlift will prove why it is the most expensive ticket in Montana.
5. Big Mountain needs to invest in facilities that guests value the most on their ski trips.
6. The resort needs data on maintenance cost to make a solid decision going forward.


Modeling Results & Analysis 
(Number of Fast Quads & Runs in Market)


