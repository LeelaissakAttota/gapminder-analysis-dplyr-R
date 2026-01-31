# 📊 Gapminder Data Analysis with R

![R](https://img.shields.io/badge/Language-R-blue.svg) 
![dplyr](https://img.shields.io/badge/Library-tidyverse-orange.svg) 
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

## 📋 Project Overview
This project explores the **Gapminder** dataset using the `dplyr` package. It focuses on tracking global health and wealth trends by continent and year, specifically looking at Life Expectancy and GDP per capita.

## 🚀 Key Features & Skills
* **Data Wrangling**: Utilized `filter()`, `group_by()`, and `summarise()` to distill large datasets.
* **Statistical Analysis**: Calculated median life expectancy and maximum GDP per capita.
* **Ranking**: Used `arrange(desc())` to identify top-performing regions.
* **Version Control**: Managed the project lifecycle using **Git** and **GitHub**.

## 🧬 Code Highlight
```r
# Finding the peak wealth by continent in 1962
gapminder %>%
  filter(year == 1962) %>%
  group_by(continent) %>%
  summarise(
    medianLifeExp = median(lifeExp),
    maxGdpPercap = max(gdpPercap)
  ) %>%
  arrange(desc(medianLifeExp))
