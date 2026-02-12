# gofast-scooter-statistical-analysis
Statistical data analysis and hypothesis testing for GoFast scooter rental service (subscription vs non-subscription users), including revenue modeling and marketing probability tasks.

## Project overview
I worked as a data analyst for the scooter rental service **GoFast**. The company provides rides through a mobile app and offers two usage options:

- **No subscription (Free)**
  - no monthly fee
  - 8 RUB per minute
  - 50 RUB start fee per ride

- **Ultra subscription**
  - 199 RUB per month
  - 6 RUB per minute
  - start fee is free

This project analyzes user behavior and ride patterns and tests hypotheses that can support business growth and retention strategy.

## Tech stack
- **Python** (Jupyter Notebook)
- **pandas**, **numpy**
- **matplotlib**, **seaborn**
- **scipy.stats** (hypothesis testing)
- **binomial / normal approximations** for probability tasks

## Dataset
The analysis uses three CSV files:
- `users_go.csv` — user profile data (including city and age)
- `rides_go.csv` — ride logs (date, distance, duration, etc.)
- `subscriptions_go.csv` — subscription information (plan type)

> **Note:** The dataset is **not included** in this repository.  
> To run the notebook, place the files into `datasets/` or update the file paths inside the notebook.

### Expected structure
```text
.
├─ datasets/                  # not included in the repo
│  ├─ users_go.csv
│  ├─ rides_go.csv
│  └─ subscriptions_go.csv
├─ Project - Statistic.ipynb
└─ README.md
```
## What was done
- Data loading from three sources (users, rides, subscriptions)
- Preprocessing:
  - converted ride date to `datetime`
  - created a `month` feature
  - checked missing values
  - removed duplicates in user data
- Exploratory data analysis:
  - user distribution by cities
  - subscription share
  - age distribution
  - trip distance and duration distributions
- Data merging into a single table + comparison of Free vs Ultra behavior
- Revenue modeling:
  - ride duration rounding
  - monthly revenue calculation by user and month
- Hypothesis testing
- Probability tasks (promo codes and push notifications)
- Final conclusions and business recommendations

## Key results

### Hypothesis tests
1) **Do subscribers spend more time riding than non-subscribers?**  
- t-statistic: **12.62**  
- p-value: **≈ 2.36e-36**  
✅ Conclusion: subscribers spend significantly more time riding.

2) **Is the average subscriber ride distance greater than 3,130 meters?**  
- average distance: **3,115.45 m**  
- t-statistic: **-1.40**  
- p-value: **0.080**  
Conclusion: insufficient evidence at α=0.05 to claim that the average distance exceeds 3,130 m.

3) **Is monthly revenue from subscribers higher than from non-subscribers?**  
- t-statistic: **-63.73**  
- p-value: **1.0**  
✅ Conclusion: subscribers do **not** generate higher monthly revenue; non-subscribers bring more revenue.

### Probability tasks
- To achieve a **95% probability** of reaching **100 subscription renewals**, the campaign needs at least **850 promo codes**.
- Probability that a push notification will be opened by **no more than 399.5k users** is **≈ 15.37%**.

## How to run
### System requirements
- Python **3.9+**
- Jupyter Notebook / JupyterLab

### Installation
```bash
python -m venv .venv

# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -U pip
pip install pandas numpy matplotlib seaborn scipy jupyter
```

### Run the notebook
```bash
jupyter lab
```

Open Project - Statistic.ipynb.

## Future improvements

- Segment analysis by city and/or age groups to find retention opportunities.

- Add confidence intervals (bootstrap) for key metrics: duration, distance, revenue.

- Explore alternative pricing strategies for Ultra (e.g., extra benefits or pricing adjustments) and simulate revenue impact.

- Package the analysis into a reproducible structure:

  - requirements.txt

  - a clear src/ folder (optional)

  - automated reports/figures export

## License

For educational and portfolio use.
