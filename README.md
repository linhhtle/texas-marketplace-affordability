# Texas Health Insurance Affordability and Coverage Fairness (2015–2016)

**Healthcare analytics | SQL | BigQuery ML | Tableau**

## Research question

**Why it matters:** Monthly premiums are only one part of health insurance affordability. Consumers may pay similar premiums but face very different out-of-pocket costs, while age-based pricing and tobacco surcharges can create additional financial burdens.

**Business question:** How do insurer competition, age, tobacco status and plan benefit design relate to affordability in the Texas ACA Marketplace, and do higher premiums reliably purchase more generous coverage?

## Data and methodology

This academic team project uses the CMS Marketplace Rate and Benefits and Cost Sharing Public-Use Files for 2015–2016, comparing Texas with other Marketplace states.

- **Data engineering:** Profiled missing values in SQL, selected relevant fields, standardized plan identifiers and cost-sharing measures, and joined rate and benefit records in BigQuery.
- **Market analysis:** Compared premium distributions, age-rating curves, issuer participation, year-over-year price changes and in-/out-of-network cost-sharing.
- **Predictive analysis:** Used BigQuery ML linear regression to estimate premium differences associated with tobacco status while holding age constant.
- **Segmentation:** Applied BigQuery ML K-means to identify four covered-plan archetypes based on average premiums, copays and coinsurance.

## Key findings

- Texas had moderate premiums for age-34 consumers but one of the steepest age-rating curves nationally. Premiums remained relatively stable despite substantial issuer participation.
- Premiums of $250–$450 accounted for over 60% of observations in the reported distribution.
- At age 34, the regression estimated monthly premiums of $277.97 for non-tobacco users versus $358.82 for tobacco users, a difference of approximately $81 (29.1%).
- Higher premiums did not consistently translate into more generous cost-sharing.

### Plan segmentation

The four clusters reveal substantial differences in financial protection even among plans with similar premiums.

| Cluster | Average premium | Average copay | Coinsurance |
| --- | ---: | ---: | ---: |
| 1 | ~$394 | ~$417 | 31.6% |
| 2 | ~$390 | ~$238 | 20.2% |
| 3 | ~$560 | ~$204 | 22.0% |
| 4 | ~$423 | ~$487 | 20.0% |

Clusters 1 and 2 together accounted for 56.8% of covered plans. Despite similar premiums, their average cost-sharing differed substantially.

## Business implications and limitations

Insurers and policymakers can use plan-level comparisons to improve benefit transparency and identify potential affordability gaps. Consumers should compare premiums alongside cost-sharing and network coverage rather than treat price as a proxy for value.

The analysis is historical and observational. Average benefit-level copays and coinsurance are not estimates of actual annual patient spending; utilization, subsidies, deductibles and individual circumstances also matter. The regression does not establish a causal effect.

## Explore the analysis

- [Project notebook](notebooks/texas-marketplace-affordability.ipynb)
- [Original Tableau dashboard 1](https://public.tableau.com/views/BA775_Team_BigQuery_DashBoard/Dashboard1)
- [Original Tableau dashboard 2](https://public.tableau.com/app/profile/yun.hsuan.ku5753/viz/775teamproject1/Dashboard1)
- [CMS Marketplace Public-Use Files](https://www.cms.gov/marketplace/resources/data/public-use-files)

Tools: SQL, Google BigQuery, BigQuery ML, Tableau.
