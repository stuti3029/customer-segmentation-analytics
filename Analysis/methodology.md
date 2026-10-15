# Analytical Methodology — Luna7

## Version of the analysis

This documentation follows **“Using Customer Segmentation and Predictive Analytics to Evaluate the Commercial Viability of Clothing Rental Services at Luna7”**, the version reporting **two clusters plus multiple regression**.

Another uploaded draft reports **three clusters**. It is a different analytical specification and must not be silently merged with the results here. The original submitted version and any published portfolio reanalysis should be clearly identified.

## 1. Study design and data

- **Business context:** Fictional US-based retailer exploring a possible rental offering.
- **Initial sample:** 265 customer observations.
- **Complete-case sample:** 223 records after listwise deletion for the relevant variables.
- **Data type:** Customer survey/behavioural and perception variables supplied for coursework.
- **Software evidenced in project:** IBM SPSS Statistics.

Variables discussed in the original report include months since last purchase, purchase frequency, website usage, online purchasing behaviour, social-platform engagement, service quality perception and expenditure at most recent purchase. The dependent outcome for regression is **intention to rent clothing**.

## 2. Cleaning and descriptive analysis

- Screened missing values and restricted multivariate analyses to complete cases.
- Calculated descriptive summaries to understand customer activity and ratings.
- Interpreted sample composition before attempting segmentation and explanatory models.

**Missing-data caveat:** Listwise deletion may change the sample's composition. The analysis does not demonstrate that missingness is random.

## 3. Customer segmentation

1. Selected behavioural and perception features relevant to engagement and commercial activity.
2. Standardised variables using **z-scores**, avoiding dominance by variables measured on larger numeric scales.
3. Explored possible structures with hierarchical clustering and a dendrogram.
4. Applied **K-means clustering**, choosing an interpretable **two-cluster solution**.
5. Reviewed final cluster centres and ANOVA comparisons as descriptive aids to interpretation.

### Interpreted groups

| Report label | Interpretation |
|---|---|
| **Digitally Engaged Premium Renters** | Higher online engagement, stronger purchasing activity and spending behaviour |
| **Low Engagement Traditional Buyers** | Less online engagement and weaker purchasing activity |

The labels summarise relative patterns in this dataset; they are not verified customer personas or externally validated market segments. K-means solutions depend on feature selection, scaling, random initialisation and chosen k. ANOVA performed after selecting clusters from the same variables should **not** be treated as independent proof of external predictive validity.

## 4. Multiple regression

The project estimated an ordinary multiple-regression model with **rental intention** as the dependent variable and customer behaviours/engagement indicators as predictors.

| Statistic reported | Value |
|---|---:|
| R² | 0.249 |
| Adjusted R² | 0.221 |
| F statistic | 8.858 |
| Model-level p-value | < 0.001 |
| Durbin–Watson | 2.201 |

Selected standardised coefficients reported as notable positive predictors:

| Variable | Reported standardised beta |
|---|---:|
| Online purchasing behaviour | 0.257 |
| Facebook engagement | 0.239 |
| Recent-purchase expenditure | 0.217 |

The assignment describes residual, normality and multicollinearity checks. Full statistical outputs and original input files are not presently included, so the coefficients and diagnostics cannot be independently recalculated here.

## 5. Interpretation and limits

- The model accounts for **about one quarter** of the variation in reported rental intention; much remains unexplained.
- Reported regression associations are **not causal estimates**.
- Expressed intention is not equivalent to observed rental adoption or revenue.
- The sample size, missing-data treatment and cluster-selection procedure limit generalisability.
- The findings support **hypotheses for pilot targeting**, not proof that any segment will be most profitable in a real launch.

## 6. Reproduction plan, if data become available

A future reproducible extension could retain the same business questions while publishing only authorised data:

- Recreate feature cleaning and missingness analysis.
- Implement scaled K-means, document random seed, compare cluster stability and alternative k.
- Fit a transparent regression model, report complete diagnostics and uncertainty intervals.
- Test practical implications using held-out or follow-up customer behaviour where available.

Do not list Python, SQL or `scikit-learn` as tools *used in the current project* unless such a reanalysis has actually been implemented.

