# Mission
Utilizing trucking data to predict economic activity in Rochester metro area and develop as an economic indicator to improve company strategy. 
# Tools
SQL (Clean and re-organize the data)

R (Exploratory analysis to find the basic insights about trucking data + Predictive analysis to select the best predictive model)

Tableau (Visualization insights to the client)
# Analysis
Clustering, Time Series Regression, Exploratory Analysis, Predictive Analytics.
# Conclusion and Recommendation 
 Best NNET model: 
 nnet_model <- nnet (Economic_index~ log(Truck_activity)^2 + log(Total_Nonfarm_Employment)^2 + log(Unemployment_Rate)^2, 
 data = trainingdata, linout=3, size=4, maxit=1000).
 
Best Linear Model: 
 lm_model_5 <- lm(Economic_Index ~ log(Truck_activity+Total_Nonfarm_Employment^3+Unemployment_Rate), data = trainingdata)

Best Model for Rochester MSA:
mars_model_16 <- earth(Economic_Index ~ Truck_activity, data = trainingdata, degree = 2, thresh = 0.1)

We find NNET model fits the training data best with the min MSE lower than 0.5. But for the whole dataset, NNET tends to overfit the
data and for that reason, we decided to choose the Linear regression model for the whole prediction. 
