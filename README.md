# Usage Patterns of Bay Wheels Bicycle Sharing System
## by Moamen Abdelkawy

## Dataset

Bay Wheels (formerly Ford GoBike) is a regional public bicycle sharing system in California's San Francisco Bay Area, and one of the largest in the US. This document explores a dataset containing Bay Wheels's trip data covering the period from 28 June 2017 to 31 August 2021.

I uploaded a copy of the whole dataset to Kaggle that can be found [here](https://www.kaggle.com/moamenabdelkawy/bay-wheels-trip-data-full-august-2021), this is the dataset used in the first notebook (exploratory-analysis). <br>
I also uploaded the wrangled dataset [here](https://www.kaggle.com/moamenabdelkawy/bay-wheels-trip-data-wrangled), this is the dataset uploaded in the second notebook (explanatory-analysis).

In the wrangling phase, I dropped all columns not mentioned in the official data description, and all NaN values and duplicates. I converted the time stamps to datetime format, changed trip durations from seconds to minutes, and added a column to show if the trip is in a workday or a weekend. I also calculated the distance between start and end station for each trip, and store it in a new column. Finally, to make my analysis easier, I converted a categorical variable of user type to a dummy variable; and since duration and distance variables had extreme outliers, I cut them at the  99𝑡ℎ  percentile.

The wrangled dataset, contains 5,022,833 trips covering the period from  28th  June 2017 to  1st  April 2020. There are 8 features in the dataset:
- Trip duration (minutes)
- Distance between start and end station (km)
- Trip start time (datetime format)
- Trip end time (datetime format)
- Is it a weekend? (dummy variable)
- User type (subscriber or customer) (dummy variable)
- Start station name
- End station name

## Summary of Findings

- Trip durations in the dataset ranges from  1 minute to about 90 minutes . The distribution is right-skewed on a linear scale but when plotted on a logarithmic scale, the distribution of trip durations gets closer to normal but with a rough shape.

- Distances between start and end station for each trip ranges from  0 km to about 5 km  in the dataset. The distribution is right-skewed on a linear scale; and when plotted on a symmetrical logarithmic scale, the distribution takes on a multimodal shape with a major mode at  1.3 𝑘𝑚  and many minor modes.

- There is a clear growth in monthly trips until the last quarter of 2019.

- During the month, demand is the highest on 11𝑡ℎ - 12𝑡ℎ , followed by 7𝑡ℎ and 19𝑡ℎ ; During the day, the rush hours are between 8-9 am, and 5-6 pm; demand drops significantly on weekends, and slightly on Friday and Monday.

- Most users of Bay Wheels are subscribers (78.4% of all users).

- Popular start and end stations are entirely different.

- For short trips (duration less than 30 minutes), there is a strong linear correlation between duration and distance between start and end stations.

- On average, bike trips tend to be longer on weekends compared to workdays; and the distribution of duration tends to have more spread on weekends.

- Customers tend to have more duration for their trips, their distribution also have more spread compared to subscribers.

- For the most part, changes in monthly trips count tend to be similar for both user types. This pattern persists till the end of November 2019; after that date, the number of customers is, surprisingly, higher than this of subscribers.

- Investigating demand during the month reveals that; daily demand of "Customers" tended to be more volatile compared to "Subscribers"; and that peaks and off-peak days are different for the two groups.

- Weekends saw a significant drop in "Subscribers" demand, while "Customers" demand was smoother across the week.

- On an hourly basis, both user groups have the same peak and off-peak hours; but "Subscribers" demand was more volatile.

- There is a strong positive linear correlation between short trips duration (less than 30 minutes) and distance between start and end station; this relation becomes weaker for longer durations. 

- Trips durations tend to be longer on weekends compared to workdays; and for customers compared to subscribers.

- The linear correlation between duration and distance is stronger for subscribers.

- The median trip duration for customers is higher than subscribers on all weekdays. 

- Customers' trip durations distribution have higher spread on all weekdays compared to subscribers.

## Key Insights for Presentation

- Bay Wheels differentiate between two user groups; "Subscribers" who are members of an annual or a monthly plan, and "Customers" who pay for each single trip. During the investigation period, 78.4% of users were "Subscribers", while 21.6% were "Customers".

- The number of monthly trips is affected heavily by the season; after taking that into consideration, there is a clear growth in monthly trips until the last quarter of 2019.

- For the most part, changes in monthly trips count tended to be similar for both user groups; this pattern persists till November 2019; after that, the number of "Customers" became, higher than this of "Subscribers".

- Investigating demand during the month reveals that; daily demand of "Customers" tended to be more volatile compared to "Subscribers"; and that peaks and off-peak days are different for the two groups.

- Weekends saw a significant drop in "Subscribers" demand, while "Customers" demand was smoother across the week.

- On an hourly basis, both user groups have the same peak and off-peak hours; but "Subscribers" demand was more volatile.

- Trip durations in the dataset ranges from  1 𝑚𝑖𝑛𝑢𝑡𝑒 𝑡𝑜 𝑎𝑏𝑜𝑢𝑡 90 𝑚𝑖𝑛𝑢𝑡𝑒𝑠 . The distribution is right-skewed on a linear scale but when plotted on a logarithmic scale, the distribution of trip durations gets closer to normal but with a rough shape.

- Distances between start and end station for each trip ranges from  0 𝑘𝑚 𝑡𝑜 𝑎𝑏𝑜𝑢𝑡 5 𝑘𝑚  in the dataset. The distribution is right-skewed on a linear scale; and when plotted on a symmetrical logarithmic scale, the distribution takes on a multimodal shape with a major mode at  1.3 𝑘𝑚  and many minor modes.

- For short trips (duration less than 30 minutes), there is a strong linear correlation between duration and distance between start and end stations. This means that for short trips, it is likely that the bike will end the trip in a different station. This insight is important to keep stations stocked with enough bikes.

- The linear correlation between duration and distance is stronger for "Subscribers", since duration values are more scattered for each distance in the case of "Customers".

- "Customers" tend to have more duration for their trips, and their distribution also have more spread compared to "Subscribers". This means that "Customers" tend to vary their trip durations, while "Subscribers" typically use the service for short trips.

- On weekends, bike trips tend to be longer, and the distribution of durations tends to have more spread on compared to workdays; this is more apparent for "Customers" but is true for both groups.

## Useful Feedback

I changed the color encoding and the size of some plots based on helpful feedback from my lovely and artistic wife, Heba Abdeen.

## Resources
- [Bay Wheels trip history data](https://s3.amazonaws.com/baywheels-data/index.html)
- [Data description](https://www.lyft.com/bikes/bay-wheels/system-data)
- [Wikipedia page of Bay Wheels](https://en.wikipedia.org/wiki/Bay_Wheels) 

## Notes

- Original dataset used for first notebook (exploratory-analysis) [here](https://www.kaggle.com/moamenabdelkawy/bay-wheels-trip-data-full-august-2021)
- Wrangled dataset used for second notebook (explanatory-analysis) [here](https://www.kaggle.com/moamenabdelkawy/bay-wheels-trip-data-wrangled)
- The first notebook takes about 40 minutes to run on Kaggle kernels.
