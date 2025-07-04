# 🏀 NBA Hall of Fame Prediction Project

This project uses **data analysis** and **machine learning** techniques to predict whether an NBA player is likely to be inducted into the Hall of Fame (HOF). The prediction is based on a range of statistical features such as points per game, assists, rebounds, and shooting percentages. Visualization and logistic regression are applied to gain insights and build a predictive model.

---

## 📂 Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Preprocessing](#preprocessing)
- [Feature Selection](#feature-selection)
- [Modeling](#modeling)
- [Evaluation](#evaluation)
- [Chris Paul Prediction](#chris-paul-prediction)
- [Installation](#installation)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [License](#license)

---

## 🧠 Overview

The goal of this project is to answer the question:

> **Will a given NBA player make it into the Hall of Fame?**

To answer this, the project:
- Visualizes trends and patterns among Hall of Fame (HOF) and non-HOF players
- Applies logistic regression to classify players based on their stats
- Evaluates the performance of the model using accuracy, confusion matrix, and classification metrics
- Predicts the probability of induction for custom player data (including Chris Paul)

---

## 📊 Dataset

The dataset used is `NBA_PLAYERS.csv`. Each row represents an NBA player, and each column contains statistical and career information such as:

- `G`: Games played  
- `PTS`: Points per game  
- `TRB`: Total rebounds  
- `AST`: Assists per game  
- `FG%`, `FG3%`, `FT%`, `eFG%`: Shooting percentages  
- `WS`: Win Shares (advanced stat estimating total contribution)  
- `HOF`: Whether the player made the Hall of Fame (`True`/`False`)  
- Other attributes like `Position`, `Birthday`, `Active`, etc.  

Only the most relevant features were retained for model building.

---

## 📈 Exploratory Data Analysis

Several visualizations were created to explore the distribution of Hall of Famers across different attributes:

### 🎯 HOF Players by Position
A bar chart showing the number of HOF players by their position.

### 📊 Points Per Game Distribution
Players were grouped into scoring bins to show how PPG affects HOF likelihood.

### 📦 Win Shares Comparison
Boxplot comparing `WS` between HOF and non-HOF players.

### 🔥 FG% Distribution
KDE plots visualizing shooting efficiency by HOF status.

---

## 🧹 Preprocessing

1. **Dropped Irrelevant Columns**: `Birthday`, `Active`, `Debut`, `Final`, `PER`  
2. **Removed Missing Values**: `dropna()` used to clean the dataset  
3. **Encoded HOF Label**: Converted `True`/`False` → `1`/`0`  
4. **Created `Pts_avg_range`**: Binned `PTS` to analyze HOF likelihood

---

## 🎯 Feature Selection

The following features were selected for training the model:

```python
features = ['G', 'PTS', 'TRB', 'AST', 'FG%', 'FG3%', 'FT%', 'eFG%', 'WS']
