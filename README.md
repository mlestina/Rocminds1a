# Rocminds1a
Analysis of changes in nightly lows at Rochester, NY over last 73 years
Everyone is aware of global worming caused by the increased CO2 content and CH4 content in our atmosphere, the former being caused by the combustion of fossile fuels and the latter being caused by thawing of tundra and gas flares. It is also well known that the international community strives to limit global warming by about 1.5 fahrenheit degrees. Nevertheless, authorities say we may have reached this 1.5 fahrenheit degree increase.
This project explores the data for Rochester NY, specifically at the Monroe County Airport (aka ROC) and examines what patterns can be formed, and determine whether global warming shows up more in the data of winter lows, summer highs, certain months of the year and how it shows up in extreme and cold months.
l

The data was imported from the National Centers for Environmental Information of NOAA (i.e. the National Weather Service)

I will now examine the daily mean, daily highs and daily lows and see how they changed over the last 73 years:

![image](https://user-images.githubusercontent.com/28972117/158037741-cbb3dae3-0a2b-4471-a1f4-14eaa6c916fb.png)

It appears that temperatures overall increased by about 2.0 Fahrenheit degrees at ROC from the end of WW II to today, suggesting that Rochester NY may be approaching the 2015 Paris Agreement limit of 2.7 Fahrenheit degrees.

![image](https://user-images.githubusercontent.com/28972117/158037763-780580ff-14da-4972-bd14-d0a1f2d6408e.png)

daily highs seemed to increas only about 1.5 Fahrenheit degrees in this period

![image](https://user-images.githubusercontent.com/28972117/158037770-8e8eb8df-9588-4ed0-9bc7-ef7b383a7e14.png)

however daily lows seemed to have increased about 2 Fahrenheit degrees over this 77 year period, suggesting that an outsized proportion of the global warming is reflected in the daily minimum temperatures

With that, I will now focus on the coldest months of the year for the data, that being Dec thru Feb. This presents a small problem because December is of a different year than Jan and Feb. I'll remedy this issue by adding a new column called 'season' to allow for December to be grouped in the same season as Jan and Feb of the next calendar year

After forming month and year columns derived from the date column, we will now focus on the coldest months of the year (Dec to March) and store in in another dataframe¶

![image](https://user-images.githubusercontent.com/28972117/158037782-e28936dd-7d03-4bd6-bb1c-90464a0ae0fa.png)

There seems to be a wide variance in the average winter seasonal daily low temperature making it difficult to determine how much of an increase it had over the 77 year period. Even after applying a 7 year rolling average as in the above right graph, it is difficult to determine the increase of winter nightly average lows over the 77 year period. A steady upward trend seems to be in place

Now, I will focus on the number of nightly lows each season that dropped below a certain threshold. I played around and it seamed that a threshold of 10F gave significant data¶

![image](https://user-images.githubusercontent.com/28972117/158037802-b8279d26-0ed2-429b-ae5b-14f693414010.png)

data and graphs above seemed to show a steady drop in the occurrences of winter nightly lows well below the norm. Due the the high fluctuation, a rolling mean is appied to the right graph to try to clarify the results.¶

![image](https://user-images.githubusercontent.com/28972117/158037809-8cec1c68-848b-493e-a70b-f6150f724dec.png)

As can be seen above, the number of daily highs exceeding 90F has not increased and may have decreased over the last 77 years, indicating that data for the warmer months and hot temperatues in Rochester do not show the 2F degree increase we previously saw

now I will calculate and plot the average nightly lows for each year for the coldest month of the year (January) and the warmest month of the year (July) to see how they compare

![image](https://user-images.githubusercontent.com/28972117/158037818-89544905-5ef7-4644-b843-8d6d8a6abda7.png)

Suprisingly, it appears that the average nightly lows for July have increased over the 73 year period as compared to the average nightly lows for January.

I will now plot the average low for each month and the average high for each month for each year for the 1948 to 2022 time frame. I will then use Seaborn's FacetGrid function to make a grid plot of these 24 graphs (12 months * min and max variants). This will involve a groupby call for each of Min and Max temps, a merging of these two dataframes, and the use of the FacetGrid function to make the 24 plots. Before merging, column names for TMAX and TMIN will each become 'temp', a flag column 'attr' will be formed that tells whether the temperature listed in the temp column is a high or a low temp.

![image](https://user-images.githubusercontent.com/28972117/158037836-2e66f027-c8a5-42a2-bd51-470d62522f24.png)

After spanning all 24 combinations (12 months by max or min temps), it seems that tMarch highs and December highs and lows experienced the greatest increase in temperatures over the 73 year period. March, September and October lows also saw significant increases over the other months for the 73 year window.
More striking were the decrease in winder season lows below 10F, and the increase in the seasonal winter lows. This contrasts from that of Washington DC (my sister project) which seemed to show the greatest increases were in the summer and saw little change in extreme winter lows and winter night temperatures.


