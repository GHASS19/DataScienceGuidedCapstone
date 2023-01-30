# Data_Science_Ski_Ticket_Price_Predictor_Capstone

![image](https://user-images.githubusercontent.com/86930309/215365766-84e3206d-901c-4e3c-a0bd-01f923175d50.png)


## 1. Context of Problem:
   Big Mountain Resort recently installed a new chairlift. The chairlift increased their operating costs by $1,540,000 for the season. The resort's pricing strategy has been to charge a premium above the average price of resorts in its market segment. Big Mountain is probably not capitalizing on its facilities to its potential.Their current ticket price compared to the market average does not provide how important different facilities are to their guests. Their ticket price is undervalued. This hinders their business investment strategy.

## 2. Criteria for Success:
Implementing a data-driven business strategy to create more revenue. Selecting the best possible value for their ticket price with data and information based upon other resorts in the United States that they compete with. Find ways to cut costs without reducing the ticket price. Or creating new facilities to justify a higher ticket price will create new success for Big Mountain.

## 3. Scope of Success:
Utilizing an algorithm in python based upon other ski resort’s data and facilities in the United States to find the best possible ticket price that fits their market segment. This will also help them locate what facilities they need to add or remove to produce better revenue.

## 4. Stakeholders:
-CEO          
-CTO       
-Data Science Team   
-National Forest Service     
-Alesha Eisen, Database Manager
-Board of Directors          
-Shareholders            
-Jimmy Blackburn, Director of Operations       
-President 
 
## 5. Key Data Sources:
-skiResort.csv  

## 6. Data Wrangling
[Data Wrangling](https://github.com/GHASS19/Data_Science_Ski_Ticket_Price_Predictor_Capstone/blob/master/Notebooks/02_data_wrangling.ipynb)
There are 330 rows and 27 columns in the data originally. Our own resort, Big Mountain Resort was present and did not have any missing data. We know that the adult weekend price is our target feature to predict the ticket price. Prices for tickets in Montana are about equal for weekday and weekend and we have more data on weekend prices.

We dropped the 'fastEight' column because half the values were missing and the rest had a value of 0. This missing information does not help us to create a new ticket price or which facilites to improve. There was a resort created in 2019 that was dropped as a row because we do not know if the numbers were projected or actual at the time of data entry. It is hard to form a sound opinion based upon this type of data. 47 of the 328 columns, (14.32%) had no 'AdultWeekday' or 'AdultWeekend' data, so we deleted those 47 rows as well. Getting rid of this data can help us to form a better idea of how to help the client.

A few other issues with the data had to be sorted out to give us a clear idea on what we were looking at. An example of that was how we had a few more regions than states. This was because states were split across multiple regions, like the Sierra Nevadas. In section 2.6.2 we found what was missing from the data. 'fastEight' had the most missing variables (50.3%), followed by 'nightSkiing_ac' (43.3), 'AdultWeekday' (16.3), 'AdultWeekend'(15.4), and 'daysOpeLastYear' (15.4). Crystal Mountain, Washington was present in the data but another resort had the same name. Which was Crystal Mountain in Michigan on row 104. We know that they were completely different entities since they are located in different states with varying data. These features also gave us possible cause for concern: SkiableTerrain_ac and Snow Making_ac because values are clustered down the low end, trams and fastSixes has more variability but mostly 0.

Currently in the project we have pin pointed that adult weekend prices is the target feature to determine what the ticket price should be. We still have to suggest what that price should be in our market segment to the client. We still need to determine what facilities matter to customers the most so they are more likely to pay more for.

We have 277 rows and 25 columns left in the data.

## 7. EDA
[EDA](https://github.com/GHASS19/Data_Science_Ski_Ticket_Price_Predictor_Capstone/blob/master/Notebooks/03_exploratory_data_analysis.ipynb)
Our state of interest, Montana is less densely populated than most of the others but is the third largest state. It is in the top five for total skiable area. A majority of the states have a smaller number of resorts relative to the state population and size. Interestingly New Hampshire and Vermont have a high amount of resorts per area but are small in size. The distribution for the average adult weekend ticket price per state varied from the mid 
90s.

The first two components of the ski data, resorts per state and state total skiable area account for over 76.8% of the variance. These two data points have the biggest effect on the difference between resorts.

At first it seems that New York standed out for potentially serving a large population with a high number of ski resorts. When we scale the data to make everything equal we find that New York does not stand-out for density of ski resorts for state size or population count. When the data is equally scaled we work towards building a pricing model that considers all states together.

The heat map was helpful to display the correlation between the data points. For example there was a high ratio of night skiing area with the number of resorts per capita. The heat map helped us identify which target features to select in improving the ticket price. Adult weekend price had a high correlation with fast quads,resort night skiing state ratio runs and snow making. Guests like the idea of having guaranteed snow when they are there. This increases the price of snow making equipment and the price of an adult weekend ticket. To increase the ticket price it might be good to have a higher share of night skiing capacity.

The scatterplots helped us to determine which features we should be wary of to form our opinion on ticket prices. It also showed what has a high correlation with the price. Ticket price could decrease a little then go up as the number of resorts per capita increases. Ticket price could climb with the higher number of resorts because it indicates a popular area for skiing with plenty of demand like the state of Colorado. On the opposite side a lower price with less ski resorts might be because it is not popular for skiing. Interestingly enough a high price for a resort where the resorts are far in between for the population size could have a monopoly effect. Lastly, if the resort has a big area then having a few fast quads may increase ticket prices.

## 8. Preprocessing & Training
The Sklearn DummyRegressor was the same as our baseline idea of performance with an average price of 63.81.The results were
almost the same when we used the median and then the mean. When we utilized the mean for missing values in the linear model they
were higher. The similar results gave us a model that was overfitting. 

The mean absolute error was one of the most helpful parts of the metrics. We found out that you could expect to be off by
roughly $19 if you simply guessed the ticket price. During our EDA we found out that vertical drop had a big impact on what 
people were willing to pay for a ticket. The linear model of coefficient validated what we found in the EDA. We also found that
Snowmaking, total chairs and fast quads also had a huge impact on average price.

Going forward we will use the random forest model. This model found that the top features were fastquads, runs, snowmaking
and vertical drop. It worked better than the linear model with missing data. The cross validation between the two models found 
that the random forest model was more accurate. It had a lower mean absolute error by over $1 then the other model.

## 9. Modeling
The exclusion of operating cost of all facilities was a deficiency in the data. We need to know how much it is to
operate a triple on the weekends is just one example. We also need to know how much we save or spend when we close a run or
increase snow making. How much it would cost to install a new chairlift and a permit from the NFS to open 150 vertical feet
could make or break their revenue. There are a lot of variables that we need to know to make a better decision. Building another
model that predicts the change in guest’s behavior due to an increase in ticket price would be helpful for the business leaders
to make a sound decision.

The modeled price is higher simply because Big Mountain offers more facilities and skiable terrain than other resorts in the
United States. It may or may not come as a surprise to the business executives depending on their point of view and the number
of guests that visit the resort every year. Having a conversation with the business executives about the resort would be the
best way to find out if they were surprised that the modeled price was much higher than they thought it would be.

The business leaders could increase prices and reduce a run to improve revenue is how they could make use of this 
information. They could also use the data to get a loan to improve certain facilities by showing a lender that they are in the 
top portion of resort offerings and can charge more for a ticket. This would show the lender that they could pay back the 
loan in a certain amount of time.

We could make a website where the business leaders could manipulate the data to show them different scenarios of ticket
prices, facilities, etc. This would help them make a good decision on product offerings and revenue. This would make it user 
friendly for the busy business executives.

## 10. Key Findings
1. Big Mountain offers more facilities and skiable terrain than most other resorts in the United States.
2. In both of our models vertical drop, snow making, total chairs, fast quads, runs, longest run, trams and skiable terrain were the most important to guests.  
3. The resort is in the top portion of fast quads, runs, snow making, total chairs and vertical drop compared to other places.
4. Most other resorts like Big Sky do not have a tram.

## 11. Recommendations:
1. I recommend that Big Mountain Resort increase their weekend price to $95.87 from $81.00. 
2. I would do an experiment for a certain amount of time and close just one ski run on the weekend to reduce maintenance cost.
3. Adding a run, 150 vertical feet and a new chairlift, (fast quad) is what I highly suggest the resort enact. This plan justifies a ticket price increase of $1.99 that improves revenue to $3,474,638 per year.
4. Creating more space to ski and a new chairlift will prove why it is the most expensive ticket in Montana.
5. Big Mountain needs to invest in facilities that guests value the most on their ski trips.
6. The resort needs data on maintenance cost to make a solid decision going forward.




