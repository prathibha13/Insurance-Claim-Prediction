# Insurance-Claim-Prediction
A brief outline of the approach towards solving the given problem statement is as follows:

#### Problem Statement : To predict Workers Compensation claims 

### Dataset:
Link to the dataset : https://www.kaggle.com/c/machine-learning-24-hrs-hackathon/data?select=train_SJC.csv
The training set in train.csv containing 36,000 insurance policies that can be used to train the model.
The test.csv contains data for testing the model.

### Data description:
ClaimNumber: Unique policy identifier
DateTimeOfAccident: Date and time of accident
DateReported: Date that accident was reported
Age: Age of worker
Gender: Gender of worker
MaritalStatus: Martial status of worker. (M)arried, (S)ingle, (U)unknown.
DependentChildren: The number of dependent children
DependentsOther: The number of dependants excluding children
WeeklyWages: Total weekly wage
PartTimeFullTime: Binary (P) or (F)
HoursWorkedPerWeek: Total hours worked per week
DaysWorkedPerWeek: Number of days worked per week
ClaimDescription: Free text description of the claim
InitialIncurredClaimCost: Initial estimate by the insurer of the claim cost
UltimateIncurredClaimCost: Total claims payments by the insurance company. This is the field you are asked to predict in the test set.

### Libraries used:
pandas, numpy, matplotlib, seaborn, sklearn

### Approach :
1. Pre-processing:
   -  Initially I imported the required linbraries, loaded the data to find out how it looks like and did some processing to name the headers properly. 
   -  In order to understand basic description of the data, I found out the summary, shape, datatypes of the data.
   -  Found out the missing values and treated them in required manner.
   -  Transformed the data-time columns, changed the datatypes of few columns and binned few columns to make better analysis

2. Exploratory Data Analysis:
   - Started the EDA with basic statistical analysis by separating the numeric and categorical variables
   - Created charts in 3 sections : Univariate analysis, bivariate analysis and Multivariate analysis and drew various insights of the data

3. Outlier Analysis: 
   In order take care of the outliers that might affect the working of the model, with the help of boxplot analysed which columns have outliers and treated them by writing a function.

4. Model Building: 
   - In order to select the model I built 3 models namely Linear Regression, Support Vector Regressor and Random Forest Regressor. 
   - After building these models by writing a single function that can encode, scale, build the model, find rmse value, and the best parameters to get the best score, I concluded that Random Forest Regressor performs better with lower RMSE value.
   - After selecting the model as Random Forest Regressor, I decided to optimize the model. Using feature importance, I selected the featured, performed Label encoding and min max scaling, tried randomized search CV to get the best parameters( but did not use it as it did not give good results) and finally obtained the Rmse score
   
5. Testing the model:
   After training the model on the train data, I tested it on the given test data by preprocessing the test data and predicting the target variable using the built model.

### Result:
The root mean squared error for the random forest model was approximately 1651.46

### Conclusion:
Exploratory data analysis using visualizations helped understand the data better and the regression models helped in predictions. however, the model can be further optimized in selecting only the most import features and other data transformation techniques for lower RMSE value.

**Kaggle notebook link** : https://www.kaggle.com/prathibhaks/20bda15
