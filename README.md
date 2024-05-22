# Forecasting_Lululemon_Stock

The purpose of this analysis is to analyze the google popularity score trends for company Lululemon, whether it correlates to the price of the stock, and to forecast its quarterly revenue in a timeframe of a year using Prophet. The tools/libraries used in this analysis include Pandas, Datetime, Matplotlib, Hvplot all within Python. Google Collab was used as the IDE since Holoviews and Prophet were also included in the notebook. 

The first part of this analysis included finding unusual patterns in the monthly google search trends dataset. The dataset was read into a DataFrame and it was sliced into the year of 2020 since during this year, Lululemon began to rise in popularity due to COVID-19. Below is a graph of the Lululemon Monthly Google Trends for the year 2020:

![lulu monthly google trends](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/43d1043a-7869-4e30-ba65-56cd9a621667)

The popularity score for the year 2020 was compared against the yearly median across all years since 2004. What was found using some basic calculations, the total search trends for 2020 was greater than the yearly median search trends for all years by an average of 62.23 popularity score.

The next part of the analysis included mining the search trends dataset for seasonality. In other words, finding the month of the year with the most search trends. The historial search trends data was graphed to get an entire visual of the search trends. The following graph is seen below:

![historical search trends](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/970b2d20-3339-481f-a0d6-c99245c59798)

In addition that same data was graphed into a heatmap to show the correlation between the month of the year and year. This was the result:

![heatmap](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/21ee8bff-ba82-4571-8bc9-4c7dc0a64728)

Based on the heatmap, months November and December seem to have a high correlation to popularity score due to the holiday season, leading customers to shop more, especially online.

Last but not least, the dataset was grouped by the month of the year and plotted into a graph. This was the result:

![month of the year](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/9375e0d5-a1c1-46a7-a08e-8c6846565840)

What was found is that the popularity score tends to increase from October exponentially, concluding our previous observation that with the holiday season, online shoppers tend to search Lululemon more frequently.

The next part of the analysis is relating the search trends to the company's stock price patterns. The dataset containing the historical stock prices were read into a DataFrame and plotted into a graph. See below:

![lulu stock](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/944aedf3-c8b9-4d04-be73-77e246d7c926)

That data was then concatenated with the google search trends data and the concatenated dataset was sliced into the period from March 2021 - November 2021. Both columns were plotted into the graph to visualize their relationship:

![close](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/dcaa2f65-466f-461d-9ec3-44b0e442b90a)
![pop score](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/4971eea0-1c9a-4d46-bf12-0aff3f115e52)

Based on these graphs, there seems to be a weak positive relationship between the search trends and the closing prices of Lululemon stock. This can be seen between March and July. Between that period there was a gradual increase in both time series. The increase can be seen again from October and November later that year.

Then the stock's volatility was found by calculating the standard deviation of the closing stock price return data over a 4 period rolling window. Below is the result in a graph:

![stock volatility](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/6e3493c9-512e-40a6-b5ce-a44e00d81acb)

A correlation table was then created using "Lagged Search Trends", "Stock Volatility", and "Daily Stock Return". Based on the results, there is a slight negative relationship between the lagged search trends and the stock volatility, however there is a slight positive relationship between the lagged search trends and the stock price returns. It is hard to tell that there is a predictable relationship among them since the correlation is so small.

The Prophet Model was then used to forecast the google search trends and the total quarterly revenue of Lululemon in 1 year. With calling the model, fitting the data and predicting the results, the following graph was generated for the google search trends:

![Screenshot 2024-05-21 221244](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/303657bf-4ae8-4bcd-8966-5baf2b60f5b1)

Based on the visualizations created, there seems to be an upward trend in the near future for the popularity score

The Prophet Model also generated the following graph for future quarterly revenue within the company. 

![Screenshot 2024-05-21 221603](https://github.com/eduardo20calvo/Forecasting_Lululemon_Stock/assets/104874384/15846f87-8db6-49ab-8dea-3606327df0d3)

Based on the graph, there will be an increase in revenue in the near future, with 3 possibilities that can be considered:

Worst Case:  2.29B (nextquarter) | 10.12B (next year)

Most Likely case:  2.44B (nextquarter) | 10.73B (next year)

Best Case:  2.59B (nextquarter) | 11.37B (next year) This would be the best forecasted figure to consider.
