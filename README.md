
# Predicting bike sharing demand using tree-based ensemble methods
Using data from Capital Bikeshare between January 1, 2011, and December 31, 2018, this study predicts bike sharing demand in the metro DC area of the United States using AdaBoost, Random Forests, and XGBoost. The models are assessed against a final value model that serves as a naive baseline model using three different performance metrics: mean average error, root mean squared error, and root mean squared log error.


## Table Of Contents

- [Installation](##Installation)
- [Project Motivation and Description](#Project)
- [File Description](#Description)
- [Results](#Results)
- [Limitations](#Limitations)
- [Licensing, Authors, Acknowledgements](#LicensingAuthorsAcknowledgements) 



## Installation

The code requires Python versions of 3.* and general libraries available through the Anaconda package.


## Project Motivation and Description

Cities are being forced to reevaluate their transportation infrastructure due to climate change. A more environmentally friendly form of transportation that minimizes greenhouse gas emissions and other air pollutants is bike sharing. It is crucial for bike sharing firms to make sure that there are enough bikes at stations, but not too many, to prevent stations from being packed with extra bikes. Knowing future demand is crucial because avoiding overstock and shortages of bikes makes customers happier. There is currently a substantial body of work that discusses how to anticipate demand for bike sharing systems using various attributes, algorithms, forecasting horizons, and location-levels.

However, there isn't presently a comparison of various tree-based ensemble techniques. These models provide the following benefits:

- ease of understanding and visualization of the algorithm
- yield better results than underlying weak learners
- nonparametric nature and ability to handle mixed data types
- robustness against overfitting, outliers, noise, multi-collinearity, and input scaling
- computationally relatively inexpensive

Therefore, this project wants to contribute to the research in the area of bike sharing demand to handle oversupply and shortages of bikes by answering the following research question:

#### How do tree-based ensemble models compare when predicting bike sharing demand?

To answer this question I used three different algorithms:

- AdaBoost
- Random Forests
- XGBoost
In addition to those three advanced machine learning models, I also used a naive baseline model (last value method) to compare the ML models' performances to a benchmark.

I used three different performance metrics to determine how well these models can predict bike sharing:

- MAE (mean average error)
- RMSE (root mean squared error)
- RMSLE (root mean squared log error)

## File Description
Two Jupyter notebooks, three pickled files, and one csv file are all included in this project. The code for creating the csv file "bike_sharing_dataset.csv," which is utilized by the file "bike_sharing_demand.ipynb" to implement the ML algorithms, is included in the.ipynb file "dataset_creation.ipynb." The three different.sav files contain the best ML models that have been stored.
## Results

A short overview of the results shall be given here:

- The last value model marginally outperforms all three ML models on the MAE, which suggests that the ML algorithms are only slightly overpredicting in comparison to the last value method, which drastically deviates from the genuine value in more instances. The strong autocorrelation of the target value may be used to explain why the last value technique is superior than sophisticated models for forecasting the demand for the next day.
- In comparison to the other two ML models, XGBoost has the lowest MAE and RMSE, but Random Forests has the lowest RMSLE; this suggests that Random Forests overpredicts more frequently and severely than the other two ML models.
- XGBoost performs marginally worse when non-stationary target values are employed, whereas AdaBoost and Random Forests perform marginally better (apart from the RMSLE), according to a comparison of the prediction of stationary vs non-stationary target values.

## Limitations
There are a number of limitations of this project and the chosen implementation:

- lagged historical weather data was used to account for look-ahead bias and because weather forecast data is difficult to obtain --> the model results may have been better if forecast instead of realized weather from the day before would have been used
- the forecast horizon is only 1 day --> in reality, it would be necessary to add forecasts for multiple periods and for more periods in the future (1 week, 1 month, 6 months etc.)
- additional features aside from temporal and meteorological features could improve the ML model performances
- the three tree-based ensemble methods should be compared against other ML algorithms and more traditional statistical methods (e.g. ARIMA) so that their contribution to the overall aim of achieving accurate demand predictions can be assessed
## Licensing, Authors, Acknowledgements

The data used for the analysis comes from:

- [Capital Bike Share](https://capitalbikeshare.com/system-data): this includes the bike demand data for the metro DC area
- [NOAA's National Climatic Data Center](https://www.ncdc.noaa.gov/cdo-web/search): this includes the weather data for the metro DC area
- [DC Department of Human Resources](https://dchr.dc.gov/node/162012): this includes the holiday data for Washington, D.C.
