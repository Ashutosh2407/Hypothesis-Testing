
A Hypothesis-Driven Analysis of Daily Spending Patterns Across Weekdays and Weekends  
Context
This project applies formal hypothesis testing to compare weekday and weekend daily spending using six months of credit card data. The goal is of this analysis is to answer the question that has bugging me for a while, “Do I tend to spend more money on weekends compared to weekdays, and if so, is this difference large enough that I should adjust my budgeting habits for better financial control?”

Problem Statement
The objective of this study is to test the common assumption that we spend more during the week than on weekends. Using six months of personal credit card data, this analysis evaluates whether weekday spending is actually higher through exploratory analysis and hypothesis testing. 

Hypotheses
Null Hypothesis (H₀): Median weekend spending is greater than or equal to median weekday spending.
Alternative Hypothesis (H₁): Median weekend spending is less than median weekday spending.

Data Description
For this analysis, I used seven months of personal credit card transaction history collected from two different banks, covering the period from February 1, 2025 to September 30, 2025. The dataset includes the following fields: Transaction Date, Description, Category, Type, and Amount. After data cleaning and aggregation to the daily level, the dataset was reduced to 209 observations across 4 variables. Of these daily records, 151 correspond to weekdays and 58 to weekends.

Methodology
Exploratory analysis included summary statistics and visual inspection of weekday vs. weekend spending patterns. Distributional checks using histograms and Q–Q plots indicated strong right-skewness and the presence of high-value outliers.To check data independence, distribution and variances across group I used the following tests. 
1)	Durbin–Watson = 0.81 indicated strong positive autocorrelation, suggesting daily spending is not fully independent. So, the data is NOT independent which actually aligns with the nature of time-series data.
2)	Levene’s test showed NO significant difference in variances. However, as the data is skewed, so even though variances are equal, I went ahead with Mann–Whitney U test.
3)	Because both groups are non-normal with significant tail deviation (skewness), I selected a non-parametric a one-sided Mann–Whitney U test instead of a t-test. I set the significance level set at α = 0.05 and interpreted the results using the test statistic and corresponding p-value.
  
Key Findings
1)	Looking at the distribution of the spendings on weekdays and weekends, it can be comfortably deduced that the weekdays have a higher number of transactions with lower dollar amounts. Conversely, the weekends have lower number of transactions with higher dollar amount.
2)	Results from the test: 
a.	Stat: 2561.0
b.	P value: 0.999
c.	With alpha 0.05 and since p > alpha, we do not have enough evidence to reject the null hypothesis.

Interpretations
A one-sided Mann–Whitney U test was performed to evaluate whether weekend spending is lower than weekday spending. The results were not statistically significant (U = 5800, p = 0.99986). We therefore fail to reject the null hypothesis. The direction and magnitude of the test statistic provide strong evidence that weekend spending is not lower; rather, weekend spending is generally higher than weekday spending.
Limitations
1)	Since the data is not for the year, seasonal variations are ignored like tax seasons, holidays (Thanksgiving) etc.
2)	The data does not consider transactions from other sources such as cash, Venmo etc.
3)	The Mann–Whitney U test compares distributions rather than means, so the results indicate directional differences but not the magnitude of overspending.
Recommendations
The results of the Mann–Whitney U test indicate that weekend spending is significantly higher than weekday spending. This pattern provides actionable insights for personal budgeting. 
First, setting my weekend-specific spending limits would produce more financial control than adjusting my weekday habits. 
Second, breaking down spending categories on weekends can pinpoint discretionary areas such as dining and entertainment that contribute to overspending. (Further analysis to be conducted.)
Finally, small reductions in weekend spending (10–20%) can compound to significant annual savings, suggesting targeted behavioral adjustments on weekends would yield the highest financial impact.


<img width="468" height="658" alt="image" src="https://github.com/user-attachments/assets/e8349921-101b-4dc7-bcb0-b33ea5721c5b" />
