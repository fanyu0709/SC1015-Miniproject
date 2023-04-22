# SC1015 Miniproject: B137_team 5

## 01: Motivation/Rationale

We believe that this dataset as well as question is relevant to our society today as many of us may be looking to attain a high economic well being to escape the rising cost of living. However, our quest for a high economic wellbeing may have potentially caused elevated stress levels and deteriorating mental health, resulting in the increasing suicide rates. NTU also has a university wellbeing office to take care of students' mental wellbeing. Hence, as NTU students who will be entering the workforce in a short few years, we are concerned about this issue.

Hence, we found the dataset: **Suicide_Rates_Overview** which compiles data on countries' economic wellbeing and their suicide rates. From this, we hope to acheive a better understanding on whether our quest for a high economic wellbeing will affect the suicide rates.
Dataset link: ttps://www.kaggle.com/code/chingchunyeh/suicide-rates-overview-1985-to-2016/input

Question: 
**How does a country's economic well being affect suicide rates among different demographic categories?**

## 02: Data Preperation and Cleaning

1. import dataset and put relevant variable in DataFrame (sData)

sData = suicideData[[
    'country',
    'year',
    'sex',
    'age',
    'suicides/100k pop',
    'HDI for year',
    'gdp_per_capita ($)'
]]

To determine a country's economic wellbeing, we need the variables (GDP & HDI). Hence, we chose HDI per year. For GDP, we chose GDP per capita instead of GDP per year as each country's population is different. GDP Per Capita makes it relatively easier to compare across countries and to adjust for different levels of purchasing power from one country to the next.

Gross Domestic Product (GDP) per capita : Measures the economic output of a nation per person to determine the standard of living and quality of life of a population.

Human Development Index (HDI) : Measures a country's level of social and economic development that comprises of mean years of schooling, expected years of schooling, life expectancy at birth, and gross national income per capita.

To have a more accurate basis of comparison of the suicide rates between countries, we shall use Suicides/100k pop instead of Suicides_no as each country has a different population. (E.g. A high suicide number is not indicative of a high suicide rate if a country has a high population.)

2. Drop data that are not in the year 2014 and without HDI in the year 2014

As countries calculate their HDIs at different time periods, we filtered out the year where it coincides for most countries. Hence, we chose 2014 as the most recent year that most countries calculated their HDI.

## 03: Exploratory Data Analysis

There are a total of 75 countries in our dataset. Hence, we proceed to take the top 20% of countries with the highest/lowest GDP per capita and HDI per year and the top 20% of countries with the highest/lowest suicide rates per 100k population. This indicates that we will take the top 15 countries of the total 75 countries.

Since we do not know the relationship between a country's economic wellbeing and its suicide per 100k population, we have to consider both the top/bottom 16 countries with the highest/lowest economic wellbeing as well as the highest/lowest suicide per 100k population.

This aids us in finding out if there is a inverse or positive correlation, if any, between a country's economic wellbeing and its suicide rate per 100k population.

### Find the Country Economic Wellbeing: GDP & HDI

- **Countries with the Highest Economic Wellbeing**
Dropped countries with GDP per capita < 50000 and HDI < 0.85. Doing so would result in only the top 15 countries out of the 75 with the highest economic wellbeing.

- **Countries with Lowest Economic Wellbeing**
Dropped countries with GDP per capita > 32000 and HDI > 0.70. Doing so would result in only the top 15 countries out of the 75 with the lowest economic wellbeing.

### Find the Country Suicide Rate

- **Countries with the lowest suicide rate**
Dropped countries with Suicide/100k pop > 60. Doing so would result in only the top 15 countries out of the 75 with the lowest suicide rate.

- **Countries with the highest suicide rate**
Dropped countries with Suicide/100k pop < 210. Doing so would result in only the top 15 countries out of the 75 with the highest suicide rate.

### ECONOMIC WELLBEING VS SUICIDE
Compare the Economic Wellbeing and the Suicide Rate

Countries with the highest economic wellbeing and lowest suicide rate
['Qatar']

Countries with the highest economic wellbeing and highest suicide rate
[] (NONE)

Countries with the lowest economic wellbeing and highest suicide rate
['Suriname']

Countries with the lowest economic wellbeing and lowest suicide rate
['Guatemala', 'South Africa', 'Turkmenistan']


## 04: Use of machine learning techniques to solve specific problem

## 05: Data driven insights & recommendations

### Project Outcome
There is a very weak correlation between a country's economic wellbeing and its suicide rate. However, since a relationship exists, a country's economic wellbeing can be considered a contributor towards suicide rate. For that, it answer our question on how economic wellbeing of the country affect the suicide rates across different demographic categories.

### Something interesting
Through this project, we also found out something interesting, for the 5 countries that we used to determine the relationship between the two variables, we observed that the distribution of suicide/100k pop varies greatly across countries. This means there are other factors that are likely to be intangible that contribute to this difference.

### Based on Machine Learning results
Based on the results provided by our machine learning techniques on our data, we found that generally, men are more likely to die by suicide than women. This may be due in part to the fact that men are more likely to work in industries that are vulnerable to economic downturns, such as construction and manufacturing. Therefore, policies that aim to support men's mental health and reduce the stigma associated with seeking help can be effective in reducing suicide rates.
