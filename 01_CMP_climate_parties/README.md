README
================
Junhui Park
2026-06-14

# Environmental Protection Issues in Party Programmes in Western Europe

## Project Overview

This project examines how political parties in four Western European
countries (France, Germany, Sweden, and the United Kingdom) differ in
their environmental protection manifesto scores across time (1940–2020)
and depending on party family, using the Comparative Manifesto Project
(CMP) dataset obtained from the WZB Berlin Social Sciences Centre
(<https://manifesto-project.wzb.eu>).

## Research Question and Hypotheses

**Research question:** To what extent do party family and country
explain variation in environmental protection manifesto scores across
time?

**Hypotheses:**

- H1: Environmental protection manifesto scores are likely to increase
  when Green parties are integrated into party systems.
- H2: Nationalist and radical right parties (NAT) are expected to show
  the lowest environmental protection manifesto scores, while mainstream
  parties may exhibit moderate scores due to party competition dynamics.

## Data

The Comparative Manifesto Project (CMP) dataset, obtained from the WZB
Berlin Social Sciences Centre (<https://manifesto-project.wzb.eu>).

## Methods

### Operationalisation of Variables

**Independent variables:** - Year: 1940–2020 - Party family: ECO
(Ecological), SOC (Social democratic), CHR (Christian democratic), CON
(Conservative), NAT (Nationalist and radical right) - Country: France,
Germany, Sweden, United Kingdom

**Dependent variable:** per501 (Environmental Protection)

### Research Design

**OLS regression analysis** By controlling for party family and country,
the model isolates the effect of time on environmental protection
manifesto scores.

**Fixed-Effects analysis** OLS regression does not account for
unobserved time-invariant party characteristics. A fixed-effects model
absorbs such variables, producing less biased estimates of the time
effect.

**Hausman test** The choice between Fixed Effects and the more
efficient Random-Effects alternative is not made by default — it is
tested. The Hausman test evaluates whether unobserved, time-invariant
party characteristics are correlated with the model's predictors; if
they are, Random Effects is biased and Fixed Effects is the
statistically appropriate choice.

## Results

The time-series analysis by party family reveals important
cross-national variation. In Western Europe, Social Democratic and
Christian Democratic parties have historically dominated party systems.
Given the subsequent emergence of Green parties and radical right
parties, this analysis focuses on five party families: CHR (Christian
democratic), CON (Conservative), ECO (Ecological), NAT (Nationalist and
radical right), and SOC (Social democratic). With the exception of the
United Kingdom, environmental protection manifesto scores begin to
emerge between the 1980s and 1990s. Sweden reaches its peak in the late
1980s, followed by a substantial decline. Notably, in Germany, high
manifesto scores around the same period are observed across all three
major party families — CHR, SOC, and ECO — suggesting a broader
contagion effect beyond Green parties alone. By contrast, ECO parties’
environmental protection scores account for a comparatively smaller
share between the late 2010s and 2020s.

These figures suggest that Green parties emerged earlier in Sweden and
secured more prominent positions within the party system compared to
other countries. The stronger the presence of Green parties in party
systems, the higher the overall environmental protection manifesto
scores tend to be. The results of a multiple OLS regression analysis are
broadly consistent with these patterns. More specifically, per501 scores
for the ECO party family and Sweden are higher by 14.10 and 2.66 points
respectively, both statistically significant at p \< .001, relative to
NAT parties and the United Kingdom.

A subsequent fixed-effects regression analysis, which absorbs unobserved
time-invariant party-level characteristics, shows that per501 scores
increase by 0.037 per year (p \< .01). The OLS coefficient for year
(0.052) is likely overestimated, decreasing to 0.037 in the
fixed-effects model, suggesting that unobserved party-level
heterogeneity partially accounts for the OLS estimate.

The choice of Fixed Effects over Random Effects is supported by a
Hausman test (chi-squared = 5.96, df = 1, p = .015), which rejects the
null hypothesis that unobserved party characteristics are uncorrelated
with `year`. This indicates the Random-Effects assumption does not
hold in this data, and confirms Fixed Effects as the statistically
justified model rather than a conservative default.

## Limitations

**OLS assumption diagnostics.** Residual diagnostics for `model3`
(Residuals vs Fitted, Normal Q-Q, Residuals vs Leverage) indicate no
dominant high-leverage outliers and only minor, sample-size-tolerable
departure from normality. However, the model violates the
homoscedasticity assumption: residual variance is visibly larger for
the ECO party family than for other groups, plausibly because ECO
manifesto scores are both higher on average and more heterogeneous
across parties and countries. Heteroscedasticity-consistent (HC1)
standard errors were computed as a correction. Under this correction,
the ECO and Sweden coefficients remain statistically significant at
p \< .001, but the CHR coefficient crosses the conventional
significance threshold depending on specification (p = .117 classical
vs. p = .028 robust) and should therefore be read as a tentative
rather than confirmed finding.

**Variable coverage.** The model's predictors (party family and
country) capture only a small portion of the variation in
environmental protection manifesto scores. Party competition dynamics
— such as mainstream and challenger parties strategically mobilising
issues outside their traditional agendas — are not modelled directly
and warrant further consideration.

**Panel structure.** Because the data include repeated observations
per party over time, the independence-of-errors assumption of OLS is
unlikely to hold; this is a central motivation for the fixed-effects
analysis reported above, rather than a separate unresolved issue.

## File Structure

| Chunk | Content                          |
|-------|----------------------------------|
| 1     | Introduction                     |
| 2     | Data loading                     |
| 3     | Descriptive statistics           |
| 4     | Visualisation                    |
| 5     | OLS Regression                   |
| 5.1   | OLS Regression results           |
| 5.2   | OLS assumption diagnostics (residual plots, robust standard errors) |
| 6     | Fixed-Effects model              |
| 6.1   | Hausman test (Fixed Effects vs. Random Effects) |
| 6.2   | OLS and Fixed-Effects comparison |
| 7     | Discussion                       |

## Packages

- `manifestoR`
- `tidyverse`
- `ggplot2`
- `stargazer`
- `plm`
- `sandwich`
- `lmtest`

## Note

API key for the Manifesto Project database is required to run this
analysis. Register at <https://manifesto-project.wzb.eu> and store your
key locally via
`mp_setapikey(key.file = "~/.manifesto/manifesto_apikey")`.
