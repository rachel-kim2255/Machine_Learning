**This repository is dedicated to archiving and showcasing my Machine Learning projects.**
<br>
<br>


# 1) 🚙 Vehicle Price Prediction Using Regression Models  
**🛠️ Linear, Lasso Regression Model**  
<br>
📎 Rachel Kim  
📚 Individual Project  
📅 Date: 2024.11  
<br>
This project is a Regression Model project based on vehicle data. The goal is to build a model that predicts vehicle prices by utilizing various feature engineering and data preprocessing techniques.  
<br>
<br>
📖 Notebook Link: https://github.com/rachel-kim2255/Machine_Learning/blob/11e1e50623e929c2ae10501b30d0e5dba3205b51/1-2.%20Vehicle%20Price%20Prediction.ipynb
<br>

---

# 2) 🏡 Finding Factors Influencing Vancouver Airbnb Price 
**🛠️ Linear, Ridge, Lasso Regression Model, Random Forest**  
<br>
📎 Rachel Kim and 3 others  
📅 Date: 2024.11  
📚 Team Project  
👩‍💻 Role: Primarily contributed to model selection and development, Jupyter Notebook implementation, and data visualization. Worked alongside teammates who handled data collection and data cleaning.  
<br>
This analysis aims to extract insights from public data provided by Airbnb, which is considered the largest accommodation company today, even though it does not own any hotels! In this project, we will explore which factors influence Airbnb pricing in Vancouver, one of the largest cities in Canada.
<br>
<br>
<br>
📖 Notebook Link: https://github.com/rachel-kim2255/Machine_Learning/blob/93046335499d5e11e2c128ded2c005a00e563e6c/2.%20Vancouver_Airbnb.ipynb
<br>
<br>

## Model Performance Summary

We tested several regression models including Linear Regression, Decision Tree, and Random Forest to predict Airbnb listing prices in Vancouver. Among them, **Random Forest Regressor** achieved the best performance with:

- **R² Score**: 0.737938
- **MAE (Mean Absolute Error)**: 0.280318

This suggests the model can reasonably predict listing prices within a small margin of error for most cases.
<br>
<br>

## Feature Importance & Key Drivers

The top predictors influencing Airbnb listing prices were:

1. **Neighbourhood Group**: Listings in downtown and waterfront areas had significantly higher prices.
2. **Room Type**: Entire homes/apartments are priced higher than private or shared rooms.
3. **Accommodates & Beds**: Listings with more capacity are generally more expensive, though with diminishing returns.
4. **Review Scores**: Higher-rated listings showed a mild increase in price, indicating reputation matters—but to a limited extent.
<br>
<br>

## Interpretation of Results

The data shows that **location and property type are the strongest indicators of price**, while quality metrics like reviews play a secondary role. Interestingly, we observed a **plateau effect** where increasing the number of beds does not proportionally increase the price—possibly due to market saturation in certain listing types.

This suggests that **perceived value and positioning** are more critical than just physical attributes.
<br>
<br>

## Business Suggestions

### For Hosts:
- Listings outside of premium zones can still compete by improving review scores or offering full-unit rentals.
- Hosts can benchmark their pricing based on similar listings in their neighbourhood group and property type.

### For Airbnb:
- This model could power **personalized pricing recommendations** for hosts, or support a **"smart pricing advisor"** feature.
- It also suggests which types of listings to promote more in certain areas, enhancing conversion and guest satisfaction.

### For Travelers:
- Users can make better decisions by understanding how price is affected by location and room type.
- A "value-for-money" filter could help highlight listings that offer more for less.
<br>

## Conclusion

This project highlights how machine learning can provide actionable insights not only for price prediction but also for platform and host strategy. With further tuning and integration, such models can contribute to smarter pricing, better user experiences, and more transparent market behavior.
