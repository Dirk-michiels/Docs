# Why are time series different?
Time series are completely different beast to tame when compared to other ML tasks. Some differences make it easier to model, some make it more difficult. Tangent Works focused really hard on understanding where these differences come from and exploiting them to create a fully automated modelling engine. On this page, we will demonstrate the key ones using simple stories. 

# More data - more problems

In the following pictures we can see two completely different signals. The first one is a gas consumption and the second one is an aggregation of different electricity consumption. However, they have one thing in common - structural changes. The structural change can be of various types - changes in mean, variance, seasonality, etc. Sometimes the difference is so radical, that it might feel like a completely different time series.  


When trying to teach ML algorithms how to play Go or how to distinguish between pictures of lungs to detect lung cancer, more data samples typically make you happy, because they enhance your performance. This, in general, is not the case when modelling time series. New data might give you a headache because your model might become useless from one hour to another. It can also be an advantage, because you usually do not have to deal with enormous datasets with millions of records. It is crucial to learn when and with what data you should retrain your models.
Database looks different every time
When dealing with time series, the time ordering of data is crucial. This is different to classification for example, where it does not matter how you reorder your dataset before you plug into your algorithm. Time series are oftentimes even cross-correlated meaning that the value of target variable in time t depends also on values of predictors from times t-k. This is unpleasant, because your new data do not arrive to your database all at once with the rows always complete. On contrary, the arrival of your data samples might be completely asynchronous meaning that your models using values from specific time lags might become useless as you do not have them when making a forecast. This has to be taken in account when modelling. Another option would be to retrain your model every time you want to make a forecast, but with AutoML techniques this is nearly impossible due to the long time taken to build models. 

More outputs at once
When forecasting, one is rarely concerned with only the one step ahead forecast. Most of the academic research is focused on the algorithm in use but they use it to forecast only one step ahead. This is very different to practice, where forecasts days or even months ahead are needed. Typical neural network solution solve this problem by creating architectures with multiple output - for example 24 outputs for day ahead forecast on daily data. However, what happens, if you want to forecast 36 hours ahead with this model? Nothing, you simply will not. The best way to solve this would be to - again - go back and retrain your model.
 
Dependence changes in time
If you ever tried modelling electricity consumption using temperature values, you would notice that the dependence is not straightforward. This makes sense because while in winters people consume more to heat with lowering temperatures, they do the opposite in summers to power air conditioning. 

This means that the dependence of consumption changes over time. To model it with linear dependency would not be appropriate. But if one can cleverly split the temperature predictor into new ones, he might gain accuracy for almost free. This is an important lesson because it tells us that the focus on feature engineering might be more crucial than the algorithm in use. 
 

And time IS a dependence
When modelling time series, usage of so called lags (or offsets) is crucial. To illustrate why, we picked a furnace melting metals where we measure levels of silicon and sulfur in the final product. If you look at the first picture, they might not seem correlated that much. But if we offset levels of sulfur by 15 steps, they suddenly become visibly correlated.


This is also something people should be familiar with when reacting to changes in real life. They typically do not come right away, but with some delay - I will turn the heat up only after some time when I find my apartment colder, not reacting to the actual outside temperature, but to the one from hour or two before. This has also consequences for time series modelling, because it once again shows us, that features and their correct generation matters. Will I use predictor from time t? Or t-100? How far should I go? These are all questions that are not trivial to solve. 
It matters WHEN you forecast
Imagine trying to forecast how many cars will be moving in the city an hour from now. If it is 3 AM, the model cars(t) = cars(t-1) would be quite good. There is no reason to believe that the number of moving cars will suddenly change during night from one hour to another. But would you use this model at 4 PM to forecast situation at 5 PM? Probably not. The variance is a lot higher during these times. Suddenly it matters whether it rains and people take taxi to go home or, the opposite, the sun is shining and people leave their cars at work to take a walk. While the rain predictor might not help you during nights at all, it might be crucial during days.  While both situations are technically an hour-ahead forecasts, the required model complexity differs a lot for them.
 
And it matters WHAT time frame you forecast

In the picture we can see a typical solar farm production during one day. Imagine you wanted to forecast it. At 3AM. It is easy to see that model production(t) = 0 is a good one. Sun simply doesn't shine during nights. But would you use this model at 12AM? Definitely not. The complexity is, once again, very different for models that you would like to use for different time frames of the day. 
In general, proper understanding of your "situation" (when and what you want to forecast while using what is available to you), that occurs when actually forecasting, might drastically improve your accuracy because you will not waste complexity where it is not needed and vice versa. 