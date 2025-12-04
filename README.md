📊 **A Hypothesis-Driven Analysis of Daily Spending Patterns (Weekdays vs. Weekends)**

This project applies statistical hypothesis testing to understand whether personal spending behavior differs between weekdays and weekends. Using six months of credit-card transactions, the analysis explores a question I’ve been curious about:

Do I spend more money on weekends compared to weekdays — and is the difference large enough to influence budgeting decisions?

🧩 **Problem Statement**

The goal of this study is to test the assumption that people (myself included) tend to spend more during the week than on weekends.
Using personal transaction data, I evaluate whether weekday spending is actually higher, using a combination of exploratory analysis and hypothesis testing.

🧪 **Hypotheses**

Null Hypothesis (H₀):
Weekend median spending ≥ Weekday median spending

Alternative Hypothesis (H₁):
Weekend median spending < Weekday median spending

📂 **Data Description**

This study uses seven months of personal credit-card transactions (Feb 1, 2025 → Sept 30, 2025) from two banks.

After cleaning and aggregating at the daily level, the dataset contains:

Metric	Value
Total Observations	209 daily records
Features	4 (Date, Category, Type, Amount)
Weekday Records	151 days
Weekend Records	58 days
🔍 **Methodology**
1. Exploratory Analysis

Summary statistics and distribution comparisons

Histograms + Q–Q plots showed right-skewness and high-value outliers

2. Independence & Variance Checks

Durbin–Watson = 0.81 → Strong positive autocorrelation
→ Daily spending is not independent (typical for time-series data)

Levene’s Test → No significant variance difference
→ But due to skewness, non-parametric methods were used

<img width="220" height="150" alt="image" src="https://github.com/user-attachments/assets/d31e8c33-d55c-43b5-85da-9e96dbd3ff80" />
<img width="213" height="146" alt="image" src="https://github.com/user-attachments/assets/428b03f0-1a33-4932-a4df-51814d5654de" />


3. Hypothesis Testing Approach

Selected one-sided Mann–Whitney U test
(non-parametric, robust to skewness and outliers)

Significance level: α = 0.05

📈 **Key Findings**
1. Distribution Behavior

<img width="234" height="150" alt="image" src="https://github.com/user-attachments/assets/e8bfb695-7737-4321-9fce-4c2731d17dd6" />


Weekdays: more transactions with lower dollar amounts

Weekends: fewer transactions but higher amounts

2. Mann–Whitney U Test Results
Statistic	Value
U	2561.0
p-value	0.999

Since p > 0.05, we fail to reject the null hypothesis.

🧠 **Interpretation**

A one-sided Mann–Whitney U test showed no statistical evidence that weekend spending is lower than weekday spending.

Instead, the results suggest:

Weekend spending is generally higher, not lower.

Thus the common intuition (“I spend more on weekends”) is supported by the data.

⚠️ **Limitations**

Data excludes seasonal effects (holidays, tax-season, etc.)

Transactions via cash, Venmo, or other sources are not included

Mann–Whitney compares distributions, not magnitude of overspending

💡 **Recommendations**

Based on the results:

Implement weekend-specific budgeting controls — weekend spending is the real driver.

Break down spending by category (e.g., dining, entertainment) to pinpoint high-impact areas.

Reduce weekend discretionary spending by 10–20% to produce meaningful annual savings.

Further category-level analysis will refine where overspending occurs.
