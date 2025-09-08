📌 Overview

In the modern era of sports analytics, understanding player performance and characteristics through data is crucial for gaining competitive advantages.

This project applies Principal Component Analysis (PCA) to La Liga players from the 2023/2024 season. PCA reduces 150+ performance metrics per player into a concise set of principal components, helping uncover hidden patterns in playing styles, strengths, and weaknesses.

🎯 Objectives

Apply PCA to simplify high-dimensional player data (~150 stats → 4–10 components).

Compare individual players and teams via PCA scores.

Identify player archetypes (e.g., aerial defenders, ball-playing defenders, creative forwards).

Generate actionable insights for recruitment, tactical planning, and performance evaluation.

📂 Data

Source: Kaggle – La Liga Dataset

Players: 681 unique players (~3,600 total records → cleaned & deduplicated).

Features: 150+ characteristics (passes, duels, goals, saves, etc.).

🛠️ Tech Stack

Python: pandas, numpy, scikit-learn

Visualization: matplotlib, seaborn

Methods: PCA, Standardization, Feature Engineering

🔧 Data Cleaning & Preprocessing

Removed players not active in La Liga 2023/24 (transfers).

Dropped unnecessary columns (gender, nickname, player.url, etc.).

Engineered Age (from DOB).

Imputed: height, weight → mean values; other nulls → 0.

Filtered players with ≥900 minutes played (standard analysis cutoff).

Split by position (Defender, Midfielder, Forward, Goalkeeper).

Standardized all features (mean = 0, std = 1).

📊 Results
🛡️ PCA on Defenders

Explained Variance: 63% (PC1–PC4)

PC1 (32%): Consistent Starters vs. Irregular Players

PC2 (16%): Aerial Dominant vs. Ground Dominant

PC3 (9%): Ball-Playing vs. Defensive Liability

PC4 (6%): Goal-Scoring vs. Traditional Defenders

📌 Example:

Positive PC1 → Reliable defenders (e.g., S. Ramos, J. Koundé).

Negative PC1 → Injury-prone/inconsistent (D. Alaba, J. Giménez).


Variance explained by components


PC1 vs PC2: Archetypes of defenders

🎯 PCA on Forwards

Explained Variance: 63% (PC1–PC4)

PC1: Playmakers/Creators vs. Pure Finishers

PC2: Goal Hunters vs. Inefficient Attackers

PC3: Complete Attackers vs. Physical Ball-Winners

PC4: Advanced Dribblers vs. Deep-Half Forwards

📌 Example:

Positive PC1 → Chance creators (wingers).

Negative PC1 → Classic strikers relying on service.




🏟️ Team-Level Analysis

Aggregated PCA scores (weighted by minutes played) reveal team strengths:

Girona FC, RC Celta, Barcelona → strong attacking indices.

Almería, Villarreal → weaker defensive indices.


Aggregated team PCA scores (defensive and attacking dimensions)

🔎 Other Analyses

Player Comparison: Compare PCA vectors of players (Euclidean distance / clustering).

Clustering (future): KMeans or DBSCAN on PCA scores for player archetypes.

Recruitment Use Case: Identify undervalued players with similar PCA profiles to stars.

🚀 Future Work

Extend PCA to midfielders and goalkeepers.

Add clustering & role classification models (e.g., Random Forest).

Build an interactive dashboard for coaches and analysts (Plotly/Dash).
