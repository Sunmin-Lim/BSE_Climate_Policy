# Research progress memo — draft

## Data assembled

- Scope: 11 countries, 2000–2019.
- Full country-year panel: 220 rows.
- Preliminary analysis sample: 206 rows. Thirteen early CPU observations
  and Australia 2014 are excluded because required values are missing.
- Outcomes examined: renewable energy share, climate mitigation patents,
  and carbon intensity.
- The carbon pricing indicator is a provisional 0/1 policy definition.
  Instrument-level April 1 reference prices are stored separately.

## Preliminary analysis

Country and year fixed effects were included. Standard errors were clustered
by country. The CPU–policy interaction results were:

- Renewable energy share: 상호작용 계수 0.0744, p값 0.3615
- Log climate patents: 상호작용 계수 0.0030, p값 0.7892
- Carbon intensity: 상호작용 계수 -0.0001, p값 0.7961

These are exploratory associations, not causal estimates. The current models
do not provide clear evidence that the CPU–outcome relationship differs by
the provisional carbon pricing indicator.

## Data and design issues

- Six countries share the EU ETS start year of 2005.
- The US is coded 0 throughout because subnational policies are outside
  the current policy definition.
- Australia 2014 is a transition year with a recorded CPM reference price,
  but its provisional policy indicator is missing.
- Mexico 2014 is coded as a policy year, but its reference price is missing.
- Canada has only one treated year in the 2000–2019 analysis period.
- Reference prices are instrument-level nominal prices generally observed
  on April 1, not national annual average prices.
- Leave-one-country-out checks suggest that the interaction estimates
  for patents and carbon intensity can change sign. Results involving
  the policy indicator are also sensitive to the comparison sample.

## Decisions TBD

1. Confirm the policy indicator's geographic scope and treatment of
   overlapping instruments.
2. Decide whether the main question is about policy adoption, price level,
   or both; keep these as separate variables.
3. Select a defensible comparison and inference strategy before making
   any causal claim.
4. Agree on the primary outcome and any lag between policy, uncertainty,
   and outcomes.

## EU-group sensitivity

Excluding the six countries assigned the EU ETS leaves five countries
(Australia, Canada, Mexico, New Zealand, and the United States) and
91 observations.

- Renewable share CPU–policy interaction: 0.0744 with all 11 countries;
  -0.0469 without the EU group.
- Log climate patents interaction: 0.0030 with all 11 countries;
  -0.0044 without the EU group.
- Carbon intensity interaction: approximately -0.0001 with all 11
  countries; -0.0011 without the EU group.

The change in direction for the first two outcomes shows that the
exploratory interaction estimates are sensitive to including the
shared EU ETS group. The five-country estimates are diagnostic only.
Neither set of estimates establishes a causal policy effect.

## Proposed research framing

**Working question:** Across 11 countries in 2000–2019, how is climate
policy uncertainty (CPU) associated with renewable energy share,
climate mitigation patents, and carbon intensity? Does this association
differ according to the provisional national/supranational carbon
pricing indicator?

**Interpretation:** Current regressions describe conditional
associations. They do not identify the causal effect of CPU or carbon
pricing.

**Outcome roles (draft):**
- Renewable energy share: main outcome for the first analysis.
- Climate mitigation patents: complementary innovation outcome.
- Carbon intensity: complementary environmental outcome.

**Next design checks:**
1. Validate the geographic coverage and timing of the policy indicator.
2. Decide how to handle the six countries sharing EU ETS adoption.
3. Assess whether the small number of independently timed policy changes
   permits a credible causal design; otherwise retain a descriptive study.
4. Specify whether outcomes should respond in the same year or with a lag.

## CPU timing and sample sensitivity

- Same-year CPU is available for 206 complete analysis rows.
- One-year lagged CPU leaves 195 rows; two-year lagged CPU leaves 184.
  All three samples retain 11 countries.
- On the same 184-row sample, the renewable-share CPU–policy interaction
  coefficients are 0.1410 for same-year CPU, 0.1638
  for one-year lagged CPU, and 0.1449 for two-year lagged CPU.
- The same-year coefficient is 0.0744 on the earlier 206-row sample
  but 0.1410 on the common 184-row sample. Sample selection
  therefore matters when comparing specifications.
- These timing checks report coefficient stability only; they do not
  establish statistical significance or causal effects.

## Climate patent share check

The OECD total-patent series (`TECH=TOT`) was extracted using the same
country, year, unit, family-size, and sex filters as the climate patent
count. Climate patent share is climate patents divided by total patents,
multiplied by 100.

All 220 country-year rows have a valid denominator. The climate patent
share rose between 2000 and 2019 in all 11 countries, including the US,
which is coded 0 throughout under the provisional policy definition.

In the exploratory 206-row fixed-effects model, the CPU–policy
interaction coefficient for climate patent share is
0.0300 percentage points
(p = 0.6349).
This does not establish a policy effect. Both the patent count and share
are retained as distinct outcomes.
