# Regression-Problems
Projects dealing with regression problems

- **Predict Sale Price of Houses** - </br>
The House Price Training data as well as the Test data (which we consider as production data or new data) both had a wide range of null values. </br>
Missing value imputation was done after thorough data analysis of the column itself as well as related columns (from domain perspective). </br>
The dependent variable had a skewed distribution, meaning a log transformation was done to get it to a normal distribution. </br>
Feature selection was minimal with occassional less significant column being dropped. </br>
Extreme outliers (< Q1-3IQR or > Q3+3IQR) were removed from both Train and Test. </br>
Metadata validation was done rigorously for Test data based on that collected from Train data </br>
Categorical values coming first time in Test were not fed in to the model as it was completely unseen for the model. For categorical values in Train but absent from Test, dummy (empty) columns were added to make the Train data suitable for Prediction </br>
The Train data was split into further subsets for training and testing of the model. However the models built did not give good evaluation metric scores, implying that this generic data split was not good for the model learning. </br>
Hence the approach taken, was applying Cross Validation with k=12 over the full train data for training our models. </br>
Evaluation metric scores after Cross Validation were highest for algorithms like Ridge Regression, XG Boosted Regression, Gradient Boosted Regression and Random Forest Regression. However after creating a blended model using the better models we got significant rise in the metric score. </br>
Finally we used this blended model (generally gives more stable predictions) to make predictions on the Test data. </br>
There is no direct way to validate our final predictions on the Test (new) data. However when we compared the distribution (mean and standard deviation) of the dependent variable 'SalePrice', between Train and Test (our Predicted column) the values were quite close.
