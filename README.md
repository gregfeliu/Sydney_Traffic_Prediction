# Sydney Traffic Prediction

This project aims to predict traffic patterns on the Eastern Distributor Highway (M1) in Sydney, Australia. The data was provided by the government of New South Wales for the Williams Street Exit toll (https://nswtollroaddata.com). With this information, city planners, trucking companies, and commuters can better plan and predict future traffic levels and plan their commutes accordingly.

## Description

Everyone wants to avoid traffic, companies more than others. The reason being that they lose money when shipments are slowed, both because of fuel/vehicle costs but also because loss of worker productivity that comes with traffic. According to a quick google search of a route that would require the use of the M1 highway:
- No traffic : **8 - 12** min.
- Medium traffic : **9 - 16** min.
- Full traffic : **14 - 26** min.

GOOGLE MAPS PIC

Therefore, as a result of poor planning, a trip can take two times more time than necessary. But what if we could tell the company/commuter eactly how much traffic to expect depending on the time that they leave their house? This would be hugely beneficial to people who make the same commute often but are flexible about when they leave. In this project, **I create models to determine the amount of traffic on the M1 for any hour, day, or time of year**. _The best model, a Long Short Term Memory (LSTM) neural network_, makes predictions that are within 89 cars of the true number of cars per hour. If, for example, there were actually 1,000 cars on the road between 8 and 9 a.m. (as there often is in this data), the LSTM model will, on average, make a prediction between 917 and 1,083 cars on the road for that time period. 

## Results

A variety of models were tried on this data. They can be broken up into 4 categories:
- Baseline model
- Auto regressive models
- Facebook Prophet (fbprophet) models
- LSTM models

Based on one metric, the (root) mean squared error, we can roughly order the success of the models like so: 
1. LSTM models
2. fbprophet models
3. Baseline model
4. Auto regressive models 

The success of various LSTM, fbprophet and the baseline model can be seen in the following table: 

MODEL METRICS DF 

Overall, we can see that LSTM is the best model (highest correlation to actual values (R2_score), and closest guess to actual values ((R)MSE)). A downside to this model is that it consistently underpredicts the true number of cars on the road. One model that does better than the LSTM model, in this regard, is one of the fbprophet models (Model8_no_negs) predicts values that are above and below the true value of cars on the road in equal proportion (as shown by MFE_Bias).

## Technologies Used 
- Jupyter Notebook
- Python
    - Pandas
    - Keras
    - fbprophet
    - sklearn
    - numpy

## Presentation and Collaboration
This project was initially worked on with Treavor Hearn (treavohearn) as our time series capstone for the Flatiron School's Data Science Bootcamp. This collaboration only used autoregressive models. A presentation of these results can be found here: https://docs.google.com/presentation/d/1rRSCcDYUPoec5JbITOHacauFt0mKyWxhl402t8pavRk/edit?usp=sharing.
