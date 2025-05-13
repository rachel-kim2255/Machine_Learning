**This repository is dedicated to archiving and showcasing my Machine Learning projects.**

------------------------------------------------------------------------------------------------------------
📎 Rachel Kim  
📅 Date: 2024.11  
📚 Individual Project

# Vehicle Price Prediction Using Regression Models 


## 📂 1. Introduction  

This project is a Regression Model project based on vehicle data. The goal is to build a model that predicts vehicle prices by utilizing various feature engineering and data preprocessing techniques. 

## 📂 2. Dataset Analysis 

For this project, the dataset is cleaned and transformed. 

1) Data Cleaning 

Records with the highest price and the oldest years were analyzed for excluding extreme outliers from the analysis. Because the higher the mileage, the lower the vehicle price, the average price of vehicles in the top 25% mileage range was calculated. Entries with condition or title_status as "salvage" or "missing" were removed to improve the accuracy of the analysis by removing unnecessary information. 

2) Data Transformation 

To reduce the skewness of the distribution through square root transformation and improve the accuracy of analysis and modeling, a new column, sqrt_price, was created by taking the square root of the price column, which was then dropped. Records with a year less than 1990 were removed for focusing on trends in the new or used car market under analysis. 

3) Reducing and Normalizing Categorical Data 

Since some brands appear infrequently in the data, the make column was simplified by grouping brands with frequencies below the median under "Other" for easier analysis. Hyphens and spaces in categorical data were replaced with underscores, and all text was converted to lowercase. 

4) Creating Dummy Variables 

Categorical variables were transformed into dummy variables using get_dummies(). Since machine learning and statistical models require numerical inputs, categorical data was converted into numerical format. Unnecessary dummy columns (e.g., co_unknown, mk_other) were dropped. 

5) Additional Work 

All dummy columns were stored as boolean type. This was because Python automatically saved them as Boolean for eifficiency. Therefore, I changed all boolean values to integers to ensure they are in a suitable format for modeling. 



## 📂 3. EDA 

<img width="437" alt="image" src="https://github.com/user-attachments/assets/b26b8530-5f7f-482d-a2c1-0ea7f07dee42" />  


Figure 1. Heatmap 


A heatmap(Figure 1.) showing the top 10 variables most correlated with sqrt_price was generated. Both year (0.58) and odometer (-0.52) exhibit a significant influence on vehicle price (sqrt_price). Furthermore, the correlation between year and odometer is -0.65, indicating a strong negative relationship. This suggests that older vehicles typically have higher mileage, implying that these two variables may offer redundant information. 

The heatmap provides a clear overview of the relationships between variables and helps identify potential multicollinearity. 

 

<img width="680" alt="image" src="https://github.com/user-attachments/assets/53a0412d-54c7-4ccd-a7ab-b84a3015580f" />  


Figure 2. Scatterplot 

Each scatter plot(Figure 2) clearly visualizes the relationship between year and vehicle price(sqrt_price) as well as odometer and vehicle price(sqrt_price). These scatter plots indicate that, in general, vehicle prices tend to increase with newer years and decrease with higher odometer readings. However, some data points deviate from these general trends. 

 

 

## 📂 4. Feature observation and hypothesis  

**Observation**  

It was confirmed that year and odometer are key features influencing vehicle price (sqrt_price). Generally, the newer the vehicle, the higher the price, and the more mileage a vehicle has, the lower the price tends to be. Additionally, a strong negative correlation of -0.65 between year and odometer indicates that older vehicles typically have higher mileage. 

**Hypothesis**   

Year and odometer play a crucial role in predicting vehicle prices, and based on the heatmap values, other features are also expected to have a meaningful impact on price prediction. However, to address potential multicollinearity issues, it is necessary to test various models and select the most appropriate one to build the final price prediction model. 

 

 

 

 

## 📂 5. Linear Regression Report  

**1) Feature Engineering Methods Used**

Data Transformation 
To reduce the distortion of price data, a variable called sqrt_price was created. This variable represents the square root of the price. 

Dummy Variable Creation 
Categorical variables were converted into dummy variables using get_dummies() to transform them into numerical inputs. 

Variable Type Conversion 
The dummy variables were initially stored as boolean types but were converted to integer types to adjust them to a suitable format for modeling. 

 

**2) Feature Selection Methods and List**

💡 Correlation-Based Selection

Selected features :   

<img width="698" alt="image" src="https://github.com/user-attachments/assets/a71b7a5a-d2ae-43f5-ae1b-f5296e5494f6" />


Features were selected based on their correlation with sqrt_price to enhance predictive performance and mitigate multicollinearity issues. 

 

💡 Select K-Best method

Selected features :  

<img width="693" alt="image" src="https://github.com/user-attachments/assets/6c647212-0b66-459f-9a8b-a8cec750e75b" />


Statistical tests were employed to select the top 10 features using the K-BEST method, resulting in a list similar to that obtained through correlation-based selection. 

 

**3) Regression Model Results** 

Lasso Alpha = 0.1 recorded the highest R² (0.598222) and the lowest RMSE (32.973553), demonstrating optimal performance while effectively addressing multicollinearity issues. 

<img width="641" alt="image" src="https://github.com/user-attachments/assets/089ed4aa-1b60-4fcb-83a1-1da469fc0ed1" />  

Figure 3. Result of Regression models 

Features Used: All features (including dummy variables) were used, with the target variable set as sqrt_price.   

<img width="514" alt="image" src="https://github.com/user-attachments/assets/4d2476b7-983a-43eb-8893-109ebe58454a" />  


 

 

 

 

 

 

 

## 📂 6. Analysis 

 <img width="603" alt="image" src="https://github.com/user-attachments/assets/75cff129-2efb-4cf9-be68-c3fd18fb9c30" />  

Figure 4. Scatter Plot of Lasso Model  


Lasso regression is a model with a feature selection capability, reducing some coefficients to zero to eliminate irrelevant variables. In this project, Lasso was chosen to mitigate multicollinearity and because it achieved the lowest RMSE score. The scatter plot shows that most of the points are close to the red line, indicating that the Lasso model demonstrates excellent predictive performance on the data.  
  
However, as some values deviate significantly from the actual values, it is important to account for potential outliers in the data. 

 

## 📂 7. Improving the Quality of Machine Learning Prediction  

In addition to tuning the alpha value, optimizing other parameters in the Lasso model can further enhance performance. For example, as Lasso regression is sensitive to feature scaling, applying MinMaxScaler or StandardScaler for data normalization can lead to a more accurate model.  

Moreover, outliers can adversely affect the model's predictive performance by increasing the RMSE. Thus, identifying and removing or adjusting these outliers can significantly improve the accuracy of the predictions. 

 
