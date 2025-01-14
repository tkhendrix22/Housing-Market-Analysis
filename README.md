# Housing-Market-Analysis

![city seattle ](https://user-images.githubusercontent.com/113871039/198593894-4be780d6-137b-497c-924d-f5ad5dec96e2.jpeg)


# Objective
The goal of this project is to analyze housing data in King County, Washington to figure out what features have an impact on the sale price, create a linear regression model that can predict price by inputing these features, and then use this data to solve some real world problem. Along the way we will need to clean our data, do some feature engineering, explain and display our work/findings via models and graphs.

# Business Problem
A newlywed couple has recently started their new journey together. The first thing that these high school sweethearts would like to do is build a family in their brand new home in the city of Kings County where they were both born and raised. They made a visit to Kings County Real Estate where they stopped at my desk being that they were recommended by a friend. They are specific in their requests in which they’d want a 3 bedroom home with about a $500,000 budget. It is my goal to give the best recommendations of the homes in the area and help these first time home buyers understand how price of a home can change depending on its features and parameters. 

# Data 
This project uses the King County House Sales data set that is listed under the data folder located in this repository. There is a description of the columns and their respective names also located in the same folder. 

# Data Cleaning and Exploratory Data Analysis
Before we can use features in our model to predict price, we need to make sure that these features can be interpreted accurately or interpreted at all.

![corrmap](https://user-images.githubusercontent.com/113871039/198896778-2c7028a2-67ab-4455-bc71-2074878d0694.png)
First I checked out the correlation between the different columns provided in the data set to see if there was any multicollinearity

- Waterfront, view, and yr renovated all had null values that we filled with zeroes in their place, which in the context of the data is logical to do. For example in the feature waterfront only 142 out of the 20999 values were waterfront properties. So not only is the ratio extremely low as it is, but if a property was a waterfront property, that information would be mentioned rather than omitted as it should be a very important eye-gazing feature.
- Waterfront, view, condition, grade, and date are categorical data, of which view, condition and grade are ordinal. These values were converted to integer values so they are better interpretable.
- Dropped unnecessary columns that I felt wasn’t necessary for this project included id, sqft living15 and sqft lot15. 

![bedroombox](https://user-images.githubusercontent.com/113871039/198899687-7ba18024-53cc-466c-bfc0-70a74c42b3f0.png)




# Methods
With price as the target variable or “y”, there are plenty other columns in the data set to serve as its predictor variable to create the best linear regression model possible. Started off with a base model that took sqft living as the main predictor variable because I found out that it was the highest correlated variable. This model however did not give us good results in which the R-squared or “Coefficient of Determination” which shows us how much variance is captured by the predictor variables, gave us a result of 0.494 which is not great but normal for a base model. 

<img width="882" alt="Screen Shot 2022-10-28 at 12 26 17 PM" src="https://user-images.githubusercontent.com/113871039/198899894-5beb01df-b7d7-4bbd-a6bc-5a8f1fb4b9e5.png">


Then through trial and error tested a few more models based on the other features of the home vs. price. 

# Model Regression Results
This section shows the results and findings of the R-squared of each model after scaling and transformations. 

## Structural Features vs. Price (applied Standard Scaler)
2nd model Train R2: 0.519
2nd model Test R2: .510

## Selling Features vs. Price 
3rd model Train R2: 0.612
3rd model Test R2: 0.623

## Location Related Variables 
4th model Train R2: 0.409
4th model Test R2: 0.398

## Combination of Important Features in Home
5th model Train R2: 0.806
5th model Test R2: 0.806

<img width="874" alt="Screen Shot 2022-10-28 at 1 10 37 PM" src="https://user-images.githubusercontent.com/113871039/198899904-5a2d00da-82a2-4549-87da-19064836e1cb.png">

The last model gave us our best predictions in which our error decreased the most and gave us our best R-squared in 81%. The last model included the features of: waterfront,sqft_lot, condition, sqft living,  grade and locations including all the zipcodes and longitude and latitude. 

# Recommendations / Next Steps

Based off our predictions here we can see that a home around $462,000 would be best for our stakeholders in which it falls right within their budget. Through trial and error our predictive model went from around 50% to 81% as we increased the complexity of the model. A model like this would be interesting to see if it was linked to more moden data. If I had more time, it would also be interesting to see a much larger data set to see how the model would perform then as well. 
