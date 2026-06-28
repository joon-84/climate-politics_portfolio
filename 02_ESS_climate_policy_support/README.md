README
================
Junhui Park
2026-06-28

# Individual characteristics and the level of support for regulatory climate policy across Europe

## Project Overview

This project examines how different socio-demographic and political
characteristics influence the level of support for regulatory climate
policies across Europe between 2016 and 2017 using the ESS data (ESS8).

## Research Question and Hypotheses

**Research question:** How do socioa-demographic and political
characteristics influence the level of support for regulatory climate
policies?

**Hypotheses:** **(H1. Socio-demographic hypotheses)** - H1a:
Respondents who have higher education level are more likely to support
regulatory climate policies. - H1b: Respondents who are younger are more
likely to support regulatory climate policies. - H1c: Respondents who
live in urban areas are more likely to support regulatory climate
policies. - H1d: Female respondents are more likely to support
regulatory climate policies. - H1e: Respondents who have higher income
level are more likely to support regulatory climate policies. **(H2.
Political characteristics)** - H2: Respondents who are self-associated
with left parties are more likely to support regulatory climate policies

## Data

- This project uses ESS Round 8 data (ESS8e02_3), which is not included
  in this repository due to file size and licencing terms. To reproduce
  the analysis, download the dataset from [ESS Data
  Portal](https://ess.sikt.no/en/datafile/ffc43f48-e15a-4a1c-8813-47eda377c355)
  and place it in ‘02_ESS_climate_policy_support/data/’.

- 2016-2017

- 23 countries

## Methods

### Operationalisation of Variables

**Independent variables:** - Gender (gndr) - Education (eisced) - Age
(agea) - Residence (domicil) - Household income (hinctnta) - Political
orientation (lrscale)

**Dependent variable:** - Favour increase taxes on fossil fuels to
reduce climate change (inctxff) - Favour subsidise renewable energy to
reduce climate change (sbsrnen) - Favour ban sale of least energy
efficient household appliances to reduce climate change (banhhap)

### Research Design

**Multilevel Regression** The multilevel regression (MLR) is a suitable
model to examine random effects for individuals nested in countries,
assuming that individuals from the same country cannot be considered
independent of one another. Unlike the OLS model, which assumes all
observations are independent of each other, the MLR accounts for the
nested structure of individuals within countries, providing more
accurate standard errors and thus more reliable statistical inference.

## Results

The ICC for all three models ranges between 4 and 6 percent (tax: 6%,
subsidy: 6%, ban: 4%), indicating that a meaningful share of variance in
policy support is attributable to country-level differences. This
justifies the use of MLR over a standard OLS approach.

Across the three models, gender, education, household income, and
political orientation show consistent and statistically significant
effects in the hypothesised direction (H1a, H1d, H1e, H2). Age (H1b) and
residence (H1c) show significant effects in the tax model, but these
effects are either not statistically significant (residence, in the
subsidy and ban models) or reversed in direction (age, in the ban
model).

It is also worth noting that the intercepts across the three models
suggest that overall support for these policies is moderate at best:
respondents lean toward opposing the tax policy, while subsidy and ban
policies receive close to neutral levels of support on average. This
indicates that even where certain socio-demographic and policial groups
are more supportive than others, none of the three policies enjoys
strong support across the Europeean sample as a whole.

## File Structure

| Chunk | Content                         |
|-------|---------------------------------|
| 1     | Setup                           |
| 2     | Data loading and cleaning       |
| 3     | Null model and ICC calculation  |
| 4     | Null models (tax, subsidy, ban) |
| 5     | Model comparison table          |
| 6     | Visualisation: tax + subsidy    |
| 7     | Visualisation: ban              |
| 8     | Discussion                      |
| 9     | Limitations                     |

## Packages

- `tidyverse`
- `here`
- `lme4`
- `sjPlot`
- `patchwork`

## References

- Aklin, Michaël, and Matto Mildenberger. 2020. “Prisoners of the Wrong
  Dilemma: Why Distributive Conflict, Not Collective Action,
  Characterizes the Politics of Climate Change.” *Global Environmental
  Politics* 20(4):4–27.
- European Social Survey European Research Infrastructure (ESS
  ERIC). 2023. ESS8 - integrated file, edition 2.3 \[Data set\]. Sikt -
  Norwegian Agency for Shared Services in Education and Research.
  <https://doi.org/10.21338/ess8e02_3>.
- Halikiopoulou, Daphne, Christos Vrakopoulos, and Christoph
  Arndt. 2026. “Far-Right against Green: The Re-Emergence of
  Geographically Defined Voting Patterns and the New Environment
  Cleavage in Western Europe.” *European Political Science Review*
  18(1):67–86. <doi:10.1017/S1755773925100155>.
- Inglehart, Ronald. 1990. *Culture Shift in Advanced Industrial
  Society*. Princeton University Press.
- Inglehart, Ronald. 1997. *Modernization and Postmodernization:
  Cultural, Economic, and Political Change in 43 Societies*. Princeton
  University Press.
- Kriesi, Hanspeter, Edgar Grande, Romain Lachat, Martin Dolezal, Simon
  Bornschier, and Timotheos Frey. 2006. “Globalization and the
  Transformation of the National Political Space: Six European Countries
  Compared.” *European Journal of Political Research* 45(6):921–956.
- Kriesi, Hanspeter, Edgar Grande, Romain Lachat, Martin Dolezal, Simon
  Bornschier, and Timotheos Frey. 2008. *West European Politics in the
  Age of Globalization*. Cambridge University Press.
