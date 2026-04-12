# 🌍 Gapminder Data Analysis — Data Manipulation with dplyr in R

![Language](https://img.shields.io/badge/Language-R-276DC3?style=flat-square&logo=r&logoColor=white)
![Library](https://img.shields.io/badge/Library-dplyr-FF6B35?style=flat-square)
![Dataset](https://img.shields.io/badge/Dataset-Gapminder-0052CC?style=flat-square)
![IDE](https://img.shields.io/badge/IDE-RStudio-75AADB?style=flat-square&logo=rstudio&logoColor=white)
![Focus](https://img.shields.io/badge/Focus-Data%20Manipulation-2E7D32?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

---

## 📌 Project Overview

This project demonstrates **core data manipulation techniques** using 
the `dplyr` package in R — the most widely used tool for data wrangling 
in the R ecosystem.

Applied to the **Gapminder dataset** (142 countries, 1952–2007), the 
project covers all 5 essential dplyr verbs through **8 structured tasks** 
— building from basic column selection to complex multi-group aggregations.

**Domain:** Data Manipulation & Exploratory Analysis  
**Language:** R  
**Libraries:** dplyr · gapminder  
**Dataset:** Gapminder — 1,704 rows × 6 columns  

---

## 📂 Project Structure

```
gapminder-analysis-R/
│
├── gapminder_analysis.R    # Main R script — 8 tasks, all 5 dplyr verbs
└── README.md
```

---

## 🛠️ Tech Stack

| Tool / Library | Purpose |
|---|---|
| **R** | Core programming language |
| **RStudio** | Development environment |
| **dplyr** | Data manipulation — all 5 core verbs |
| **gapminder** | Global development dataset |

---

## 📊 Gapminder Dataset

| Variable | Type | Description |
|---|---|---|
| `country` | Factor | 142 countries |
| `continent` | Factor | 5 continents |
| `year` | Integer | 1952–2007 (12 years) |
| `lifeExp` | Numeric | Life expectancy at birth |
| `pop` | Integer | Population |
| `gdpPercap` | Numeric | GDP per capita (USD) |

---

## 🚀 Project Workflow — 8 Tasks

---

### ✅ Task 1 — Getting Started
Install and understand the `dplyr` and `gapminder` packages

---

### ✅ Task 2 — Import & Explore Dataset
```r
library("dplyr")
library("gapminder")

gapminder          # View full dataset
glimpse(gapminder) # Structure overview
str(gapminder)     # Data types & dimensions
```

---

### ✅ Task 3 — SELECT Verb
Select specific columns from the dataset:
```r
# Select country and continent columns
gapminder %>% select(country, continent)

# Store result
country_con <- gapminder %>% select(country, continent)
```

---

### ✅ Task 4 — FILTER Verb
Filter rows based on conditions:
```r
# Filter for year 1962
gapminder %>% filter(year == 1962)

# Filter for China in 2002
gapminder %>% filter(year == 2002, country == "China")
```

---

### ✅ Task 5 — ARRANGE Verb
Sort data in ascending or descending order:
```r
# Sort by life expectancy ascending
gapminder %>% arrange(lifeExp)

# Top 15 countries by highest life expectancy
gapminder %>%
  arrange(desc(lifeExp)) %>%
  slice(1:15)

# Filter 1962 + sort by population descending
gapminder %>%
  filter(year == 1962) %>%
  arrange(desc(pop))
```

---

### ✅ Task 6 — MUTATE Verb
Create and transform columns:
```r
# Convert lifeExp to months
gapminder %>% mutate(lifeExp = 12 * lifeExp)

# Add new column lifeExpMonths
gapminder %>% mutate(lifeExpMonths = 12 * lifeExp)

# Combined pipeline — filter + mutate + arrange
gapminder %>%
  filter(year == 2007) %>%
  mutate(lifeExpMonths = 12 * lifeExp) %>%
  arrange(desc(lifeExpMonths))
```

---

### ✅ Task 7 — SUMMARISE Verb
Aggregate data into summary statistics:
```r
# Overall median life expectancy
gapminder %>% summarise(median_lifeExp = median(lifeExp))

# Median life expectancy for 1962
gapminder %>%
  filter(year == 1962) %>%
  summarise(median_lifeExp = median(lifeExp))

# Multiple summaries — median lifeExp + max GDP
gapminder %>%
  filter(year == 1962) %>%
  summarise(
    median_lifeExp = median(lifeExp),
    maxGdpPercap = max(gdpPercap)
  )
```

---

### ✅ Task 8 — GROUP_BY Verb
Group data and compute summaries by category:
```r
# Median life expectancy + max GDP per year
gapminder %>%
  group_by(year) %>%
  summarise(
    medianLifeExp = median(lifeExp),
    maxGdpPercap = max(gdpPercap)
  )

# By continent in 1962 — sorted by life expectancy
gapminder %>%
  filter(year == 1962) %>%
  group_by(continent) %>%
  summarise(
    medianLifeExp = median(lifeExp),
    maxGdpPercap = max(gdpPercap)
  ) %>%
  arrange(desc(medianLifeExp))

# By year AND continent combined
data <- gapminder %>%
  group_by(year, continent) %>%
  summarise(
    medianLifeExp = median(lifeExp),
    maxGdpPerCap = max(gdpPercap)
  )
```

---

## 🔑 5 Core dplyr Verbs Mastered

| Verb | Purpose | Example |
|---|---|---|
| `select()` | Choose columns | `select(country, continent)` |
| `filter()` | Filter rows | `filter(year == 2007)` |
| `arrange()` | Sort rows | `arrange(desc(lifeExp))` |
| `mutate()` | Add/change columns | `mutate(lifeExpMonths = 12 * lifeExp)` |
| `summarise()` | Aggregate data | `summarise(median_lifeExp = median(lifeExp))` |
| `group_by()` | Group for aggregation | `group_by(year, continent)` |

---

## 🎓 Skills Demonstrated

- dplyr data manipulation — all 5 core verbs
- Pipe operator (`%>%`) for chained operations
- Multi-condition filtering
- Sorting with `arrange()` + `desc()`
- Row selection with `slice()`
- Column creation with `mutate()`
- Statistical aggregation — `median()`, `max()`
- Multi-group analysis with `group_by()`
- Exploratory data analysis on Gapminder
- `glimpse()` + `str()` for dataset inspection

---

## 📜 Certifications

| Certification | Issuer | Platform |
|---|---|---|
| IBM Data Science Professional Certificate | IBM | Coursera |
| IBM Generative AI Professional Certificate | IBM | Coursera |
| IBM Agentic AI with RAG Certificate | IBM | Coursera |
| IBM RAG and Agentic AI Professional Certificate | IBM | Coursera |

---

## 🤝 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Leela%20A-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/leela-a)
[![Gmail](https://img.shields.io/badge/Gmail-attotaleelaissak@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:attotaleelaissak@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Leelaissakattaota-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Leelaissakattaota)
