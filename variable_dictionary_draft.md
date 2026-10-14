# Climate policy research: variable definitions (draft)

Sample: 11 countries, annual data, 2000–2019 (220 country-year rows).
Current complete-case sample: 206 rows. Definitions and policy coding require review before analysis.

| Variable | Role | Definition and unit | Source |
|---|---|---|---|
| country_code, year | Panel keys | ISO3 country code and calendar year | Harmonized across sources |
| CPU | Moderator | Annual climate policy uncertainty index; original index units | CPU source file (`cpu_raw.csv`) |
| CarbonPrice_draft | Policy indicator | 1 if a selected carbon tax or ETS is coded as active in that country-year; 0 otherwise | World Bank Carbon Pricing Dashboard; provisional coding |
| renewable_share | Outcome | Renewable energy consumption as % of total final energy consumption | World Bank WDI, EG.FEC.RNEW.ZS |
| carbon_intensity | Outcome | kg CO₂e per 2021 PPP $ of GDP | World Bank WDI, EN.GHG.CO2.RT.GDP.PP.KD |
| green_patents | Alternative outcome | Environment-related patent inventions; fractional count; patent family size ≥2 | OECD Patents – technology development, ENV_PAT / PATN / TWO |
| climate_patents | Preferred climate-specific outcome candidate | Climate change mitigation patent inventions; fractional count; patent family size ≥2 | OECD Patents – technology development, CCM / PATN / TWO |
| gdp_per_capita | Control | GDP per capita, constant 2015 US$ | World Bank WDI, NY.GDP.PCAP.KD |
| trade_pct_gdp | Control | Exports plus imports as % of GDP | World Bank WDI, NE.TRD.GNFS.ZS |
| industry_pct_gdp | Control | Industry, including construction, value added as % of GDP | World Bank WDI, NV.IND.TOTL.ZS |

## Policy coding requiring review

- Germany, Spain, France, United Kingdom, Ireland, and Italy: EU ETS coded 1 from 2005.
- New Zealand: coded 1 from 2008.
- Mexico: coded 1 from 2014.
- Canada: federal policy coded 1 in 2019; earlier provincial systems are not included.
- Australia: coded 1 in 2012–2013, missing in the partial/repeal year 2014, and 0 from 2015.
- United States: coded 0 throughout; state and regional systems are not included.

## Missing values

- CPU: 13 early country-year observations are unavailable in the source.
- CarbonPrice_draft: Australia 2014 is intentionally missing.
- Other variables: no missing values in the 2000–2019 sample.

## Decisions TBD

1. Should the treatment include subnational carbon pricing in Canada and the United States?
2. Should EU ETS coverage count as the same treatment as a national carbon tax?
3. How should Australia's 2014 repeal year and subsequent untreated years be handled?


4. Should the patent outcome use all environment-related inventions (ENV_PAT), climate mitigation inventions (CCM), or both?

## Reference carbon price (draft)

- File: `processed_data/carbon_price_reference_observed_2000_2019.csv`
- Variable: `reference_price_apr1_usd_tco2e`
- Definition: Nominal price in US dollars per tCO2e for the selected reference
  carbon pricing instrument, generally measured on April 1 of each year
  (or the latest available date before April 1).
- Source: World Bank Carbon Pricing Dashboard, `Compliance_Price` sheet.
  Methodology: https://carbonpricingdashboard.worldbank.org/about-us
- This is an instrument-level reference price, not a national annual average
  or an economy-wide effective carbon price. EU ETS prices are shared across
  the six countries assigned `ETS_EU`; other instruments can coexist.
- Missing price means no price observation for this selected instrument.
  It must not automatically be converted to zero or to policy non-adoption.
- Australia 2014: a CPM price is observed, while `CarbonPrice_draft` is
  missing because 2014 is treated as a transition year.
- Mexico 2014: `CarbonPrice_draft` is 1, while this price is missing.
- The preliminary regression models use `CarbonPrice_draft`, not this
  reference-price variable.
