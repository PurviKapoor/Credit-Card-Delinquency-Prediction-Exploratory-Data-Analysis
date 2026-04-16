# Credit Card Delinquency Prediction - Exploratory Data Analysis

## Project Overview
Every bank and credit card company faces the same costly problem: some customers stop paying their bills. When a customer misses payments and falls into delinquency, the company loses money and the customer's financial health suffers too.

This project dives deep into a dataset of credit card customers to uncover who is most at risk of becoming delinquent, and why. Using Exploratory Data Analysis (EDA), I examined patterns across customer income, credit scores, employment status, loan balances, and spending habits to surface actionable insights.

Think of it like this: instead of waiting for a customer to default, the goal is to spot the warning signs early; like a doctor running tests before a patient falls seriously ill.

## Problems I Set Out to Solve
#### **1. Who is likely to miss payments?** 
Can customer demographics and financial behavior reliably signal delinquency risk?

#### **2. What are the strongest warning signs?** 
Which factors — income, credit score, missed payments, debt load — matter most?

#### **3. Are there patterns across customer segments?** 
Does location, employment status, or credit card type influence the risk?

#### **4. How clean is the data?** 
Are there inconsistencies, missing values, or duplicates that could mislead analysis or future predictive models?

## Analysis Approach
The project follows a structured EDA pipeline:

#### **1. Understanding the Data**
Examined dataset shape, data types, and statistical summaries


Identified missing values and duplicate records


Computed correlations between all numerical features and the target variable (Delinquent_Account)

#### **2. Data Cleaning**
Standardised inconsistent entries in Employment_Status (e.g., 'EMP' and 'employed' were unified into 'Employed')


Dropped rows with missing Credit_Score values — only 2 records were affected, so deletion was safe without biasing the dataset (validated visually by overlaying distributions before and after)

#### **3. Univariate Analysis**
Studied individual variables in isolation:

Categorical: Employment status distribution, credit card type breakdown (pie chart), location spread

Numerical: Income, loan balance, credit score, and credit utilisation distributions — checking for skewness and outliers using histograms and box plots

#### **4. Multivariate Analysis**
Explored how variables interact with each other and with delinquency:

Delinquency rates across credit card types, locations, and employment statuses

Income and credit score distributions split by delinquency status

Scatter plots and regression lines for: Income vs Loan Balance, Credit Utilization vs Missed Payments, Credit Score vs Loan Balance

Pair plots for a holistic view of all numerical relationships

KDE (density) plots to compare age distributions between delinquent and non-delinquent customers

Heatmap of missed payments vs delinquency status

## Key Findings & Insights
#### **1. Missed Payments is the Strongest Predictor**
Customers with a higher number of missed payments in the past 12 months showed a dramatically higher rate of delinquency. The heatmap made this relationship unmistakably clear — this is the single most direct warning sign.

#### **2. High Credit Utilisation Correlates with Delinquency**
Customers using a large proportion of their available credit limit were disproportionately represented among delinquent accounts. High utilisation often signals financial stress — customers are leaning heavily on credit, likely because they're cash-strapped.

#### **3. Lower Income Customers Face Higher Risk**
Box plots comparing income by delinquency status revealed that delinquent customers tend to have lower incomes. However, income alone is not a definitive predictor — the relationship is moderate, not absolute.

#### **4. Credit Score Separates the Groups**
As expected, delinquent customers tended to have lower credit scores. This validates the dataset's integrity and confirms that credit scores do carry meaningful signal — but they aren't the whole story.

#### **5. Employment Status Matters**
Unemployed customers appeared more frequently in the delinquent category compared to employed ones. This makes intuitive sense — without steady income, meeting payment obligations becomes harder.

#### **6. Location and Card Type Show Variation**
Certain locations had noticeably different delinquency distributions, and some credit card types were associated with higher delinquency rates. This may reflect differences in customer demographics or product targeting rather than direct causation — but worth investigating further.

#### **7. Age Distribution is Similar Across Both Groups**
The KDE plot showed that age distributions for delinquent and non-delinquent customers largely overlap. Age alone is not a reliable predictor of delinquency in this dataset.

## Recommendations
Based on the analysis, here is what a business could act on:

#### **1. Build an Early Warning System**
Flag customers who start missing payments (even just 1–2) and have rising credit utilisation. These two signals together are a strong precursor to full delinquency.

#### **2. Segment Risk by Employment Status**
Unemployed customers warrant closer monitoring and could benefit from proactive outreach or flexible payment options before they fall behind.

#### **3. Review Credit Limits for High-Utilisation Customers**
Rather than waiting for missed payments, identify customers consistently using 80%+ of their credit limit. Engage them early with financial health resources or restructured products.

#### **4. Investigate Location-Based Patterns**
Regional delinquency variation may reflect economic conditions. A location-specific strategy (e.g., targeted support programmes in higher-risk areas) could be more effective than a one-size-fits-all approach.

#### **5. Leverage Credit Score as a Screening Tool, Not a Sole Criterion**
Credit scores help, but they are a lagging indicator. Combining them with real-time behavioural signals (missed payments, utilisation trends) gives a more complete and timely risk picture.

#### **6. Invest in a Predictive Model**
This EDA lays the groundwork for a machine learning classification model. The features identified here — missed payments, credit utilisation, debt-to-income ratio, and employment status — would serve as strong model inputs to predict delinquency before it occurs.
