Netflix Customer Satisfaction Analysis
Business Question
What combination of user traits is associated with the highest customer satisfaction?
Dataset

Source: Netflix Large User Data (synthetic dataset)
Size: 1,000 users × 16 columns
Features: Demographics (Age, Income, Region), behavior (Watch Time, Engagement, Support Queries), and subscription details (Plan, Genre Preference, Device)

Project Structure
├── netflix_large_user_data.xlsx   # Original dataset
├── netflix_cleaned.csv            # Cleaned dataset (13 columns)
├── Netflix_Project.ipynb          # Full analysis notebook (Google Colab)
├── README.md
Methodology
Step 1 — Business Question
Initially explored churn prediction, but EDA revealed no feature significantly predicted churn (all p > 0.05). Pivoted to customer satisfaction analysis where genre preference and engagement showed meaningful variation.
Step 2 — Data Understanding
Audited all 16 columns for missing values, duplicates, outliers, and logical consistency. Dataset was fully clean with zero issues found.
Step 3 — Data Cleaning

Dropped 3 columns: Customer ID (identifier), Churn Status (outcome, not predictor), Payment History (no relationship with satisfaction, p = 0.81)
Renamed remaining 13 columns for cleaner syntax
Verified: 0 missing values, 0 duplicates

Step 4 & 5 — EDA & Visualizations
Built 6 visualizations using Python (Matplotlib + Seaborn) to explore satisfaction patterns:

Satisfaction Distribution — Scores spread evenly across 1–10
Satisfaction by Genre — Action fans most satisfied (5.85), Comedy fans least (4.92)
Satisfaction by Plan — Premium slightly higher (5.54) vs Basic (5.18)
Correlation Analysis — Engagement is the only significant predictor (r = −0.072, p = 0.023)
Genre × Plan Interaction — Best: Basic + Action (6.17), Worst: Premium + Comedy (4.56)
High vs Low Profiles — Action overrepresented among satisfied users (15.5% vs 9.6%)

Key Findings
FindingDetailGenre matters mostAction (5.85) vs Comedy (4.92) — largest gap across all featuresEngagement hurts satisfactionOnly significant predictor (r = −0.072, p = 0.023), negative directionPlan tier barely mattersPremium vs Basic difference not significant (p = 0.264)Best combinationBasic plan + Action genre (mean = 6.17)Demographics irrelevantAge, Income, Region, Device show near-zero correlation
Bottom line: What you watch matters far more than who you are or what you pay.
Recommendations

Increase Action/Thriller content budget — these genres drive the highest satisfaction
Audit the Comedy catalog — investigate why Comedy fans are consistently the least satisfied
Improve content discovery UX — negative engagement correlation suggests users browse too long without finding content
Collect richer behavioral data — current features are insufficient; track completion rates, skip frequency, and rewatch behavior

Tools Used

Python 3 — pandas, matplotlib, seaborn, scipy
Google Colab — notebook environment
Canva — presentation design
