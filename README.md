This repository website is available [here](https://obiwenobi.github.io/rprojet/#introduction).

This document investigates the relationships between macroeconomic variables and marriage rates in Mauritius over the period from 1964 to 2018, focusing on whether these relationships are endogenous. The analysis uses data on health, macroeconomics, and marital variables, including birth rates, death rates, inflation, GDP, growth rates, marriage, and divorce.

The first part of the analysis presents a summary of the dataset, including descriptive statistics and visualizations. The health-related variables show a decreasing trend, while macroeconomic variables (GDP, inflation, and growth rate) and marital data (marriage and divorce) are plotted to examine their trends. The code checks for potential correlations between these variables, showing no clear correlation between marriage and divorce, but indicating possible endogeneity between the health and macroeconomic variables.

The second part of the analysis focuses on modeling relationships between the variables. Two approaches are considered:

1. Linear Additive Model: Marriage is modeled as a function of other macroeconomic variables, assuming no endogeneity. The results suggest that the growth rate has no significant effect on marriage, while mortality has a significant effect.

2. Vector Auto-Regressive (VAR) Model: This method models the relationships between multiple variables and includes their lagged values to account for endogenous relationships. The VAR model estimates the impact of past values of economic variables on current marriage rates. The results show that past mortality and growth rates affect marriage, but the effects of inflation, divorce, and other variables appear over time.

The final part examines the Impulse Response Function (IRF), which simulates the effect of a shock in one variable (e.g., GDP or growth) on marriage. The IRF results suggest that growth and GDP shocks do not significantly affect marriage rates in the long term.

Overall, the analysis suggests that past economic variables influence marriage rates, but there is little evidence of strong, long-term effects from GDP or growth shocks.
