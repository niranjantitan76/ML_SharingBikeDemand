# Project Name
> Multiple Linear Regression - Bike-sharing case study


# Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)


# General Information
- Provide general information about your project here.
     BoomBikes a US bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.
  
- What is the background of your project?

    BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

    This project is  a Machine Learning project and tries understand which factors significantly affect the demand for shared bikes. And build a Muliple Lenear Regression Model to predict the demand for shared bikes.

- What is the business probem that your project is trying to solve?

    Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors. 
    BoomBikes have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

    - Which variables are significant in predicting the demand for shared bikes.
    - How well those variables describe the bike demands

 # Problem Statement

> BoomBikes, a US bike-sharing provider, has faced significant revenue declines due to the COVID-19 pandemic. To recover and gain a competitive edge post-lockdown, BoomBikes aims to understand the factors influencing the demand for shared bikes. The company seeks insights into which variables significantly predict bike demand and how well these variables explain the fluctuations in demand in the American market. This analysis will help BoomBikes prepare to meet customer needs effectively and drive future profitability.

> It wishes to use the data to optimise the the demand for shared bikes in the American market based on important factors such as humidity, windspeed, weathersit, etc.

> Here are the key points of what BoomBikes wants:

- **Identify significant variables:** Understand which factors significantly affect the demand for shared bikes.
- **Predict bike demand:** Determine how well these variables can predict the demand for shared bikes.
- **Prepare for post-pandemic recovery:** Use the insights to prepare for increased demand after the COVID-19 lockdown ends.
- **Gain a competitive edge:** Stand out from other service providers by better understanding and meeting customer needs.
- **Increase profitability:** Develop strategies to accelerate revenue growth and achieve higher profits.

- What is the dataset that is being used?

    The dataset contains information about daily bike demands across the American market based on some factors.

    **Columns**

- instant: record index
- dteday : date
- season : season (1:spring, 2:summer, 3:fall, 4:winter)
- yr : year (0: 2018, 1:2019)
- mnth : month ( 1 to 12)
- holiday : weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
- weekday : day of the week
- workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
- weathersit : 
	- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
	- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
	- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
	- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
- temp : temperature in Celsius
- atemp: feeling temperature in Celsius
- hum: humidity
- windspeed: wind speed
- casual: count of casual users
- registered: count of registered users
- cnt: count of total rental bikes including both casual and registered

## Objective

- **Importing necessary Modules**:
Import the modules necessary for Data Manipulation and Visualization.

- **Reading dataset**:
Read the dataset containing bike demand.

- **Exploring the Dataset**:
Understand the Structure and various datatypes of the attributes within the dataset.

- **Missing value analysis**:
Identify and analyze missing values in the dataset.

- **Analysing categorical and numerical columns**:
Analyze categorical and numerical columns to understand the statistical properties and relationships within the dataset.

- **Univariate Analysis**:
Conduct univariate analysis to explore the distribution and characteristics of individual variables.

 -   **Outliers**:
Identify and analyze outliers within the dataset to understand their impact on the analysis.

- **Bivariate analysis**:
Conduct bivariate analysis to explore relationships between different variables and their impact on bike demand.

- **If there is some obvious multicollinearity going on**
- **Model Building and Evaluation**
Also identify if some predictors directly have a strong association with the outcome variable

# Conclusions
 These three features contributing significantly towards explaining the demand of the shared bikes:

**Temperature (0.5211):** For every unit increase in temperature, bike demand increases by 0.5211 units, holding all other factors constant. (Strong positive impact) bike-sharing service.

**Year (0.2328):** Demand increases significantly in 2019 compared to the reference year (2018), suggesting increased bike usage in the second year. with an increase of 0.2328 unit

**Winter (0.1374):** Winter has a slightly higher positive impact compared to summer, with demand increasing by 0.1374 units.

**We can see that the equation of our best fitted line is:**

$ cnt = 0.1264 + 0.236  \times  temp + 0.5211  \times  windspeed -0.1516 \times summer + 0.1016 \times winter + 0.1374 \times year + 0.2328 \times aug + 0.0557 \times  sept + 0.1133 \times misty\_cloudy - 0.0809 \times light\_snow\_rain - 0.2786   $

## Inference from the OLS Regression Model Statistics:
### Model Fit:
**R-squared (0.830):** The model explains 83% of the variability in the dependent variable (cnt). This is a strong fit.

**Adjusted R-squared (0.827):** After accounting for the number of predictors, the model still explains 82.7% of the variance, confirming the robustness of the fit.

**F-statistic (270.8, p-value = 6.57e-186):** The model is statistically significant as a whole, indicating that the predictors collectively explain a significant portion of the variation in bike demand.

### Interpretation of Coefficients:

**Intercept (0.1264):** When all other variables are at their reference levels, the bike demand (cnt) starts from a small positive baseline value.

**Temperature (0.5211):** For every unit increase in temperature, bike demand increases by 0.5211 units, holding all other factors constant. (Strong positive impact)

**Windspeed (-0.1516):** For every unit increase in windspeed, bike demand decreases by 0.1516 units, holding other factors constant. (Negative impact)

#### Seasonal Effects:

**Summer (0.1016):** Bike demand increases by 0.1016 units during the summer compared to the reference season, holding other factors constant.

**Winter (0.1374):** Winter has a slightly higher positive impact compared to summer, with demand increasing by 0.1374 units.

#### Yearly Effects:

**year (0.2328):** Demand increases significantly in 2019 compared to the reference year (2018), suggesting increased bike usage in the second year.

#### Monthly Effects:

**August (0.0557):** Demand increases by 0.0557 units in August compared to the reference month.

**September (0.1133):** September sees a stronger positive effect compared to August, with an increase of 0.1133 units.

#### Weather Effects:

**Mist/Cloudy (-0.0809):** Weather conditions like mist or cloudy skies reduce bike demand by 0.0809 units compared to clear weather.

**Light Snow/Rain (-0.2786):** Snow or rain has a significantly negative impact, reducing demand by 0.2786 units. (Largest negative impact)

### Model Diagnostics:

**Omnibus (64.857) and Jarque-Bera (151.244):** Both tests suggest that the residuals deviate from normality. While linear regression is somewhat robust to this assumption, a transformation or more flexible model might improve results.

**Durbin-Watson (2.000):** Indicates no significant autocorrelation in residuals, which is a positive sign for the model.

## Technologies Used
- numpy
- pandas
- seaborn
- matplotlib
- statsmodels
- sklearn
- Visual Studio Code
- Anaconda
- Python Notebook
- Python 3.12.4

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here. https://www.upgrad.com/
- This project was inspired by...http://dx.doi.org/10.1007/s13748-013-0040-3,
- References if any...
- This project was based on Upgrad and IIIT Banglore facultie's recommendation.


## Contact
Created by [@[niranjansingh](https://www.linkedin.com/in/niranjan-singh-56659151?)]- - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->