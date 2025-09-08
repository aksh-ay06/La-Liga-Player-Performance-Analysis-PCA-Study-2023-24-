In the modern era of sports analytics, understanding player performance and characteristics through data is crucial for gaining competitive advantages. This project applies Principal Component Analysis (PCA) to La Liga players from the 2023/2024 season.

PCA is a statistical technique used to reduce the dimensionality of large datasets while preserving as much variance as possible. By simplifying the complexity of player data, it becomes easier to identify patterns and actionable insights.

Objectives

Dimensionality Reduction: Apply PCA to reduce a multidimensional dataset (~150 features per player) into a concise set of principal components.

Player Comparison: Compare individual players or groups of players based on their PC scores to uncover similarities and differences in styles, strengths, and weaknesses.

Archetype Discovery: Identify distinct player types (e.g., aerial-dominant vs. ground-dominant defenders).

Actionable Insights: Generate performance indicators to support decisions in player development, recruitment, transfers, and tactical planning.

📂 Data

Source: Kaggle – La Liga Dataset

Size: 681 players × ~150 characteristics

🛠️ Python Libraries Used

Data Processing: pandas, numpy

Visualization: matplotlib, seaborn

ML / Stats: scikit-learn

🔧 Data Cleaning & Preprocessing

Removed players from teams not part of La Liga 2023/24 (e.g., transfers).

Dropped unnecessary columns (e.g., gender, nickname, player.url).

Engineered Age from Date of Birth relative to the season start date.

Removed duplicates.

Imputed missing height and weight with column means.

Replaced other nulls with 0 (interpreted as “no contribution”).

Filtered out players with <900 minutes played (standard cutoff = 10 full matches).

Split dataset by player position (Defender, Midfielder, Forward, Goalkeeper).

Standardized all numeric features to mean = 0 and std = 1.

📊 Results
PCA on Defenders (Explained Variance ≈ 63%)

PC1: Consistent vs. Irregular Starters (32%)

Positive: Highly involved, reliable defenders (e.g., S. Ramos, J. Koundé).

Negative: Injury-prone / inconsistent starters (e.g., D. Alaba, J. Giménez).

PC2: Aerial Dominant vs. Ground Dominant (16%)

Positive: Ground dominance (e.g., Y. Couto, J. Cancelo).

Negative: Aerial dominance (e.g., R. Le Normand, S. Ramos).

PC3: Ball-Playing vs. Defensively Liable (9%)

Positive: Strong passers, build from back (e.g., M. Gutiérrez, D. Carvajal).

Negative: Defensive vulnerabilities, lack of discipline (e.g., R. Marín, A. Abqar).

PC4: Goal-Scoring vs. Traditional Defenders (6%)

Positive: Attack-minded, scoring defenders (e.g., D. Carvajal, E. García).

Negative: Stay-back traditional defenders (e.g., D. Blind, M. Mármol).

👉 Similar PCA performed for forwards (notebooks included). Midfielder and goalkeeper analyses can be extended in the same way.

🔎 Other Analyses
1. Team Analysis

Aggregated player PCA scores into team-level scores using minutes-played weighted averages.

Enables comparison of defensive/attacking strengths across clubs.

2. Player Comparisons

Player PC vectors allow clustering or distance-based comparison.

Euclidean distances between PCA score vectors highlight similar vs. contrasting playing styles.

📈 Example Insights

Defenders like Sergio Ramos show high aerial dominance, while João Cancelo excels in ground playmaking.

Teams like Girona FC and Barcelona exhibit strong attacking indices, while Almería and Villarreal lag defensively.

PCA uncovers hidden archetypes (e.g., creators vs. finishers, ball-winners vs. possession stabilizers).

🚀 Future Work

Extend PCA analysis to midfielders & goalkeepers.

Apply clustering (KMeans, DBSCAN) to discover hidden player groups.

Build predictive models (e.g., Random Forest, XGBoost) for role classification.

Deploy insights in an interactive dashboard (Plotly/Dash).