# Gym Churn Analysis — Gym Model Fitness

Customer churn analysis for Gym Model Fitness, a gym chain: predicting membership cancellations and identifying customer profiles with clustering, to propose retention strategies.

TripleTen Data Analyst program project — Mara Torres Blanco.

## What this project does

1. **Explores customer behavior** (churn vs. no churn) with distributions and correlations.
2. **Segments customers with KMeans clustering** and measures churn per cluster.
3. **Trains churn prediction models** (Logistic Regression and Random Forest) and compares them, prioritizing recall so at-risk customers are not missed.
4. **Closes with retention recommendations** per customer segment.

## Tools

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- SciPy
- scikit-learn (KMeans, Logistic Regression, Random Forest)

## Key findings

### Main churn drivers

1. **Short contract period** — customers on a 1-month contract have **57% churn** (Cluster 3).
2. **Low visit frequency** — fewer than 1 visit per week is the strongest abandonment signal.
3. **Short tenure** — customers with less than 3 months are the most vulnerable.
4. **Few months left on the contract** — when 1 month or less remains, risk spikes.

### Customer segments (clustering)

- **Cluster 3** — urgent intervention (churn 57%).
- **Clusters 4 and 0** — preventive retention (churn 25–27%).
- **Clusters 1 and 2** — the most loyal; keep them satisfied. Cluster 2 (contracts of ~12 months) has only **2% churn**.
- Churning customers tend to be younger (~27 years vs. ~30), have very short tenure (~1 month vs. ~4.7 months) and visit much less often (~1 time/week vs. ~2 times/week). At-risk customers have contracts expiring soon (~1.7 months left).

### Models

- **Logistic Regression wins by a small margin** on accuracy and precision. Recall is identical in both models — out of every 10 customers who actually leave, both correctly detect ~8.
- Since recall matters most here (we do not want to miss at-risk customers), and both models perform the same on it, **Logistic Regression is the recommended model** for being simpler and more interpretable.

### Recommendations

1. **Promote annual contracts from sign-up** — offer a 10–15% discount for 6- or 12-month contracts.
2. **Onboarding program for new customers** — the first 3 months are critical: a welcome coach, weekly goals and visit tracking.
3. **Automatic inactivity alert** — if a customer drops below 2 visits/week for 2 weeks in a row, trigger proactive contact (message + free group class).
4. **Boost group classes and the referral program** — customers with group visits and friend referrals show lower churn; group participation builds community and raises the cost of leaving.

## Data

- `gym_churn_us.csv` — gym customer data (contract, visits, tenure, churn).

**The dataset is not included in this repository** — it was provided on the TripleTen learning platform. The notebook will not run without it; the code and outputs are preserved as delivered.

## Files

- `gym_churn_analysis.ipynb` — the analysis notebook (17 cells).
- `README.md` — this file.

## How to run

Open `gym_churn_analysis.ipynb` in Jupyter Notebook or JupyterLab and run the cells top to bottom. It expects `gym_churn_us.csv` in the same folder (not included — see Data above).
