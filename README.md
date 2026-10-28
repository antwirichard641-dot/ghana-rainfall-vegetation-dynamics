# Rainfall Variability and Vegetation Dynamics in Ghana (2000–2024)

## Project Overview

Rainfall variability influences vegetation growth, agricultural production systems, and the availability of natural resources across different ecological environments. Understanding how rainfall patterns relate to vegetation dynamics is particularly relevant to agricultural research in regions where crop and livestock production depend partly on seasonal rainfall.

This project investigates the relationship between rainfall variability and satellite-derived vegetation greenness in Ghana between 2000 and 2024. It combines precipitation estimates from the Climate Hazards Group InfraRed Precipitation with Station data (CHIRPS) with vegetation observations from the Moderate Resolution Imaging Spectroradiometer (MODIS) Normalized Difference Vegetation Index (NDVI) product.

The analysis examines annual rainfall variability, rainfall seasonality, long-term trends in rainfall and vegetation greenness, and the statistical association between annual rainfall and NDVI. It also evaluates the robustness of the observed rainfall–NDVI association through detrending and leave-one-year-out sensitivity analysis.

Using Python, Google Colab, and Google Earth Engine, the project demonstrates an agricultural research workflow involving geospatial data processing, data validation, exploratory analysis, statistical testing, visualization, and reproducible documentation.

The primary focus is on understanding the relationship between precipitation and vegetation greenness at the national scale. Although these variables are relevant to agricultural and ecological research, NDVI is not a direct measurement of forage biomass, forage quality, or livestock-accessible feed. The results are therefore interpreted within the limits of the satellite-derived indicators and the study design.

## Research Question

**How has rainfall varied in Ghana between 2000 and 2024, and what statistical relationship exists between annual rainfall and satellite-derived vegetation greenness over the same period?**

### Research Objectives

The project was designed to:

1. Validate and summarize rainfall observations for Ghana.
2. Characterize annual rainfall variability and monthly seasonality from 2000 to 2024.
3. Examine annual vegetation greenness patterns using MODIS NDVI.
4. Evaluate the association between annual rainfall and annual mean NDVI.
5. Assess whether the observed rainfall–NDVI association remains after removing linear time trends.
6. Evaluate the sensitivity of the correlation to the exclusion of individual years.
7. Interpret the results in the context of national aggregation, satellite-derived measurements, and observational research limitations.
8. Establish a reproducible analytical workflow for investigating environmental patterns relevant to agricultural systems.

## Agricultural and Environmental Research Context

Rainfall is an important environmental driver of vegetation dynamics. Changes in precipitation can influence soil moisture, plant growth, seasonal vegetation development, and the timing of vegetation responses.

However, vegetation greenness is also influenced by other factors, including temperature, soil properties, vegetation type, land management, land-cover change, and the timing and distribution of rainfall.

Satellite-derived NDVI provides a useful indicator of vegetation greenness over large geographic areas. Combining NDVI with precipitation estimates makes it possible to investigate environmental relationships across time without relying exclusively on ground-based observations.

For agricultural research, this approach can help identify patterns that warrant more detailed investigation. For example, rainfall–vegetation relationships may be relevant to understanding seasonal crop development, rangeland conditions, and environmental variability affecting livestock production systems.

Nevertheless, a national-level correlation cannot establish the mechanisms driving vegetation responses or demonstrate how much forage is available to livestock. These questions require additional environmental data and, where possible, field-based validation.

## Study Area and Period

| Component | Description |
|---|---|
| Study area | Ghana |
| Study period | 2000–2024 |
| Temporal coverage | 25 calendar years |
| Rainfall dataset | CHIRPS precipitation |
| Vegetation dataset | MODIS MOD13Q1 NDVI |
| Main analytical variables | Annual rainfall and annual mean NDVI |
| Analytical approach | Descriptive, correlational, and sensitivity analysis |
| Programming environment | Python and Google Colab |
| Geospatial processing | Google Earth Engine |

The analysis focuses on national-level summaries for Ghana. Consequently, the results describe broad patterns across the retained spatial observations rather than the behavior of every location or ecological zone.

## Data Sources

### 1. Rainfall: CHIRPS

The Climate Hazards Group InfraRed Precipitation with Station data (CHIRPS) product provides precipitation estimates combining satellite information and station observations.

CHIRPS was used to investigate rainfall patterns over Ghana during the study period.

**Source:** [CHIRPS — Climate Hazards Center](https://www.chc.ucsb.edu/data/chirps)

The rainfall analysis includes annual summaries and monthly seasonality, providing a basis for examining variation across years and within the annual cycle.

The interpretation of rainfall estimates depends on the spatial coverage, aggregation procedure, and units used in the processed dataset.

### 2. Vegetation: MODIS MOD13Q1 NDVI

The MODIS MOD13Q1 product provides vegetation indices derived from satellite observations. This project uses the Normalized Difference Vegetation Index (NDVI) to examine temporal patterns in vegetation greenness.

**Source:** [NASA LP DAAC — MODIS Vegetation Indices](https://lpdaac.usgs.gov/products/mod13q1v061/)

NDVI is a spectral indicator derived from reflected red and near-infrared radiation. It is widely used to characterize vegetation greenness and monitor vegetation conditions over time.

In this project, annual mean NDVI is used as a broad indicator of vegetation greenness across the retained spatial observations.

NDVI should not be interpreted as a direct measure of forage biomass, nutritional quality, crop yield, or livestock-accessible vegetation.

### Data integration

The project combines national annual rainfall estimates with annual mean NDVI observations for the 2000–2024 period.

Combining these datasets requires consistent year alignment and careful consideration of spatial aggregation, valid observation coverage, and the differences between precipitation measurements and satellite-derived vegetation indices.

The exact spatial aggregation and valid-pixel procedures should be documented in the analytical notebook to ensure that the integrated results can be reproduced.

## Methods

The analysis was conducted using Python, pandas, SciPy, Google Colab, and Google Earth Engine.

### 1. Rainfall data validation and preparation

Rainfall observations were inspected and summarized to evaluate data coverage and prepare annual and monthly precipitation statistics.

The validation workflow included checks on the structure and consistency of the retained observations.

### 2. Rainfall variability and seasonality

Annual rainfall summaries were used to examine interannual variability over the 25-year period.

Monthly summaries were also used to characterize seasonality and investigate how rainfall is distributed across the calendar year.

These analyses provide descriptive context for interpreting the relationship between rainfall and vegetation greenness.

### 3. Vegetation greenness analysis

MODIS NDVI observations were processed to derive annual mean vegetation greenness values for Ghana.

The resulting annual series was examined for temporal variation and a potential linear trend.

Interpretation of the NDVI series depends on the processing procedure, the treatment of invalid observations, and the spatial coverage retained in each year.

### 4. Linear trend analysis

Linear regression was used to estimate the direction and magnitude of annual rainfall and NDVI trends.

The estimated slopes summarize average linear change over time. Statistical significance was assessed using the reported regression results.

A non-significant linear trend does not demonstrate that a variable was constant. It indicates that the analysis did not provide sufficient evidence of a non-zero linear trend under the fitted model and its assumptions.

### 5. Pearson and Spearman correlation

Pearson correlation was used to assess the strength and direction of the linear association between annual rainfall and annual mean NDVI.

Spearman correlation was also included in the analytical workflow to assess monotonic association using ranked observations.

Correlation measures describe statistical relationships; they do not establish causation.

### 6. Detrending analysis

The rainfall–NDVI relationship was examined after removing linear time trends from the annual series.

Detrending helps investigate whether the association remains after accounting for linear temporal trends in both variables.

This procedure does not automatically eliminate every source of confounding or temporal dependence.

### 7. Leave-one-year-out sensitivity analysis

The correlation analysis was repeated while excluding one year at a time.

This procedure evaluates whether the observed association depends disproportionately on any single annual observation.

The resulting range of correlations provides a measure of sensitivity to individual years. It does not, by itself, establish that the association is causal or that all sources of statistical uncertainty have been addressed.

## Research Figures and Results

### Figure 1. Annual Rainfall Trend in Ghana (2000–2024)

![Annual rainfall trend in Ghana from 2000 to 2024.](figures/figure1_annual_rainfall_trend.png)

*Figure 1. Annual rainfall estimates for Ghana between 2000 and 2024, showing year-to-year variability and the estimated linear trend.*

The reported mean annual rainfall estimate across the retained grid cells was approximately **1,204.5 mm**.

The estimated linear trend was **+1.053 mm per year**, with a p-value of **0.7692**.

Although the estimated slope was positive, the trend was not statistically significant at the 5% level. The analysis therefore did not provide sufficient evidence of a non-zero linear rainfall trend over the study period.

This result does not imply that rainfall remained unchanged from year to year. Annual rainfall can fluctuate substantially even when a fitted linear trend is not statistically significant.

### Figure 2. Annual Vegetation Greenness Trend (2000–2024)

![Annual mean MODIS NDVI trend in Ghana from 2000 to 2024.](figures/figure2_annual_ndvi_trend.png)

*Figure 2. Annual mean NDVI for Ghana between 2000 and 2024, illustrating the estimated temporal trend in satellite-derived vegetation greenness.*

The reported annual mean NDVI trend was approximately **−0.000570 NDVI units per year**, with a p-value of **0.3431**.

The estimated slope was negative, but the trend was not statistically significant at the 5% level.

This result does not establish that vegetation greenness declined consistently throughout the study period. It indicates that the fitted linear model did not provide sufficient evidence of a non-zero linear trend.

Annual mean NDVI may conceal important differences between ecological zones, vegetation types, and seasons. National aggregation is therefore useful for describing broad patterns but cannot fully characterize local vegetation dynamics.

### Figure 3. Relationship Between Rainfall and Vegetation Greenness

![Relationship between annual rainfall estimates and annual mean NDVI in Ghana from 2000 to 2024.](figures/figure3_rainfall_ndvi_relationship.png)

*Figure 3. Association between annual rainfall and annual mean NDVI across the 25-year study period.*

The reported Pearson correlation between annual rainfall and annual mean NDVI was **r = 0.5003**, with **p = 0.0109**.

This indicates a moderate positive linear association in the analyzed annual observations. Years with higher rainfall estimates tended, on average, to coincide with higher annual mean NDVI values.

However, this relationship should not be interpreted as proof that rainfall alone determined vegetation greenness. Vegetation dynamics can also be influenced by temperature, soil conditions, land-cover change, vegetation type, management practices, and other environmental factors.

NDVI is an indicator of vegetation greenness rather than a direct measurement of forage production or quality.

## Statistical Findings

### Summary of reported results

| Analysis | Reported result | Interpretation |
|---|---|---|
| Mean annual rainfall | Approximately 1,204.5 mm | Average rainfall estimate across the retained grid cells |
| Annual rainfall trend | +1.053 mm/year; p = 0.7692 | Positive estimated slope, not statistically significant |
| Annual mean NDVI trend | −0.000570 units/year; p = 0.3431 | Negative estimated slope, not statistically significant |
| Rainfall–NDVI correlation | Pearson r = 0.5003; p = 0.0109 | Moderate positive association in the annual observations |
| Detrended rainfall–NDVI correlation | Pearson r = 0.5238; p = 0.0072 | Positive association remained after removing linear time trends |
| Leave-one-year-out correlations | 0.4219 to 0.5574 | The estimated correlation remained positive across the sensitivity checks |
| Leave-one-year-out significance | All 25 tests reportedly p < 0.05 | The reported association remained statistically significant when each individual year was omitted in turn |

*These figures reproduce the results supplied for the project. They should be checked against the exported statistical outputs before publication.*

### 1. Rainfall trends were not statistically significant

The estimated rainfall trend was positive, but its p-value was substantially greater than 0.05.

The analysis therefore did not establish a statistically significant linear increase in annual rainfall over the study period.

This does not rule out changes in rainfall variability, seasonality, or localized rainfall patterns that may not be captured by a single national linear trend.

### 2. The annual mean NDVI trend was not statistically significant

The estimated NDVI slope was slightly negative, but the trend was not statistically significant.

Consequently, the analysis did not establish a statistically significant linear decline in national mean vegetation greenness during the period.

Other forms of variation, including seasonal differences and regional patterns, may not be adequately represented by this national annual summary.

### 3. Rainfall and vegetation greenness were positively associated

The reported Pearson correlation of 0.5003 indicates a moderate positive linear association between annual rainfall and annual mean NDVI.

The reported p-value of 0.0109 indicates that the association was statistically significant at the 5% level under the test used.

This finding supports the conclusion that rainfall and vegetation greenness varied together in the annual observations. It does not establish that rainfall was the sole driver of NDVI variation.

### 4. The positive association remained after detrending

After removing linear time trends, the reported Pearson correlation was 0.5238, with a p-value of 0.0072.

The positive association therefore remained statistically significant in the detrended analysis.

This suggests that the reported relationship was not explained solely by the fitted linear time trends.

However, detrending does not control for all environmental variables or automatically resolve possible temporal autocorrelation.

### 5. The association was robust to omitting individual years

The leave-one-year-out correlations ranged from 0.4219 to 0.5574, and all 25 reported tests remained statistically significant at p < 0.05.

This indicates that the positive correlation was not dependent on any single year under the reported sensitivity procedure.

The sensitivity analysis strengthens confidence that the observed positive association is not driven solely by one annual observation. It does not prove causation or replace a full assessment of model assumptions and statistical uncertainty.

## Discussion

### Interpreting rainfall and vegetation greenness together

The positive rainfall–NDVI association is consistent with the possibility that wetter years tend to coincide with greener vegetation at the national scale.

Water availability can influence plant growth, but the strength and timing of vegetation responses depend on other factors, including soil moisture, temperature, vegetation type, and land management.

The association observed in this project therefore provides a basis for further investigation rather than a complete explanation of vegetation dynamics.

### Why the trend results and correlation results can differ

The rainfall and NDVI trends were individually non-significant, while their correlation was positive and statistically significant.

These results are not inherently contradictory.

Trend analysis evaluates whether an individual variable exhibits a detectable linear change over time. Correlation analysis evaluates whether two variables tend to vary together across the observations.

Two variables can have no statistically significant linear trend individually and still exhibit a positive association with one another.

### What detrending contributes

The positive detrended correlation indicates that the reported rainfall–NDVI association persisted after removing fitted linear trends from both series.

This is useful because shared linear trends can sometimes create misleading correlations between time-series variables.

Nevertheless, the detrended result should not be interpreted as a causal effect. Other environmental factors, temporal dependence, and spatial aggregation may still influence the association.

### Agricultural interpretation

The findings are relevant to agricultural and environmental research because rainfall and vegetation greenness are useful indicators for examining environmental variability.

However, the analysis does not directly measure crop yield, pasture biomass, forage quality, or livestock feed availability.

Further research using crop-specific observations, ecological-zone comparisons, and direct vegetation or forage measurements would be needed to address those questions.

## Limitations

### 1. National spatial aggregation

National annual averages can conceal differences among Ghana's ecological zones, vegetation types, and agricultural production systems.

The results should not be assumed to apply equally to every location in the country.

### 2. NDVI is a proxy for vegetation greenness

NDVI does not directly measure biomass, forage nutritional value, or vegetation accessible to livestock.

The results therefore support conclusions about satellite-derived vegetation greenness, not direct estimates of forage production.

### 3. Observational design

The analysis examines statistical associations rather than controlled experimental effects.

The positive rainfall–NDVI relationship does not establish that rainfall alone caused the observed vegetation patterns.

### 4. Temporal autocorrelation

Annual rainfall and NDVI observations may exhibit temporal dependence. The reported correlation tests and linear regressions should be interpreted in light of the statistical procedures used and whether those procedures account for such dependence.

Detrending and leave-one-year-out sensitivity analysis address specific concerns but do not eliminate all time-series limitations.

### 5. Spatial coverage and valid-pixel handling

The calculation of valid spatial coverage for NDVI requires further verification, as noted in the original project description.

The number and distribution of valid satellite observations may affect annual means. The processing workflow should document quality filtering, valid-pixel coverage, and the handling of missing or invalid observations.

### 6. Limited explanatory variables

The analysis does not explicitly control for temperature, soil moisture, land-cover change, land management, or other environmental influences.

The rainfall–NDVI relationship may therefore reflect multiple interacting processes.

### 7. Statistical significance and practical importance

Statistical significance does not automatically indicate that an association is large enough to have substantial practical importance.

The correlation estimates should be interpreted alongside their uncertainty, the measurement scales, the spatial aggregation procedure, and the intended agricultural application.

## Future Research Directions

Potential extensions include:

### 1. Ecological-zone comparisons

Examine rainfall and NDVI relationships separately across Ghana's ecological zones to identify spatial differences concealed by national averages.

### 2. Seasonal rainfall–NDVI relationships

Investigate whether rainfall during particular seasons is more strongly associated with vegetation greenness than annual rainfall totals.

### 3. Additional environmental variables

Integrate temperature, soil moisture, land-cover change, or other relevant environmental observations to investigate whether they help explain variation in NDVI.

### 4. Spatial validation

Verify the valid-pixel coverage and spatial aggregation procedures used to calculate annual mean NDVI.

### 5. Field-based validation

Where suitable data are available, compare satellite-derived vegetation indicators with direct field observations of vegetation condition or forage characteristics.

### 6. More robust time-series inference

Investigate methods that account for temporal autocorrelation and assess whether the reported associations remain under alternative statistical specifications.

These are potential research directions rather than completed analyses.

## Repository Structure

The repository is intended to organize the analysis notebooks, processed datasets, statistical outputs, and methodological documentation.

```text
rainfall-vegetation-dynamics-ghana/
├── notebooks/
│   └── [analysis notebooks]
├── data/
│   └── [processed rainfall and rainfall-NDVI datasets]
├── figures/
│   ├── figure1_annual_rainfall_trend.png
│   ├── figure2_annual_ndvi_trend.png
│   └── figure3_rainfall_ndvi_relationship.png
├── results/
│   └── [statistical and sensitivity-analysis outputs]
├── docs/
│   └── [methods, interpretation, and limitations]
├── requirements.txt
├── LICENSE
└── README.md
```

*Replace bracketed entries with the actual filenames in your repository before publication.*

### Repository contents

| Directory | Purpose |
|---|---|
| `notebooks/` | Analysis notebooks documenting the workflow |
| `data/` | Processed rainfall and integrated rainfall–NDVI datasets |
| `figures/` | Figures illustrating rainfall trends, NDVI trends, and their association |
| `results/` | Statistical summaries and robustness-analysis outputs |
| `docs/` | Research methods, interpretation, and limitations |
| `requirements.txt` | Python dependency list |
| `LICENSE` | Repository licensing information |

## Tools and Technologies

- **Python:** Data analysis and scientific computing.
- **pandas:** Data preparation and tabular analysis.
- **SciPy:** Statistical analysis.
- **Google Colab:** Notebook-based analysis.
- **Google Earth Engine:** Satellite data processing.
- **CHIRPS:** Precipitation estimates.
- **MODIS MOD13Q1:** Satellite-derived vegetation indices.
- **GitHub:** Research documentation, version control, and portfolio presentation.

These tools support the investigation of environmental relationships relevant to agricultural research. The primary focus remains rainfall variability and vegetation greenness in Ghana.

## Reproducibility

Reproducibility is essential for evaluating environmental data analysis.

The repository is intended to contain the analytical notebooks, processed datasets, statistical outputs, figures, and methodological documentation required to inspect the workflow.

### Steps to reproduce the analysis

1. Clone or download the repository.
2. Review the notebooks and their data-loading instructions.
3. Access the corresponding CHIRPS and MODIS source data.
4. Follow the documented Google Earth Engine processing procedures where required.
5. Install the dependencies specified in `requirements.txt`.
6. Run the notebook cells in sequence.
7. Compare the generated figures and statistical outputs with the exported results.

Reproduction depends on the actual notebook implementation, data-loading procedures, geospatial filters, quality-control rules, and file paths documented in the repository.

All source datasets should be attributed to their respective providers.

## Conclusion

This project investigates rainfall variability and satellite-derived vegetation greenness in Ghana between 2000 and 2024 using CHIRPS precipitation estimates and MODIS NDVI observations.

The reported rainfall and NDVI trends were not statistically significant, while their annual values exhibited a moderate positive association. The association remained statistically significant after detrending, and the leave-one-year-out sensitivity analysis indicated that it was not dependent on any single year under the reported procedure.

These findings suggest that annual rainfall and vegetation greenness varied together over the study period, even though neither variable exhibited a statistically significant linear trend in the reported analyses.

The results do not establish causation, and NDVI should not be treated as a direct measure of forage production or quality. Further research involving ecological-zone comparisons, seasonal analysis, additional environmental variables, and field-based validation could improve understanding of the processes underlying the observed relationship.

The project forms part of my agricultural research portfolio and demonstrates the application of reproducible data analysis and statistical reasoning to environmental questions relevant to agricultural systems.

## About the Author

**Richard Antwi**

BSc in Agriculture, majoring in Animal Science

Research interests include agricultural production systems, sustainable agriculture, environmental variability, livestock production, and quantitative approaches to agricultural research.

This project explores how rainfall and satellite-derived vegetation indicators can be used to investigate environmental patterns relevant to agricultural research.

---

**Data sources:** CHIRPS precipitation and MODIS MOD13Q1 NDVI.

**Study area:** Ghana.

**Study period:** 2000–2024.

**Research approach:** Exploratory observational analysis with detrending and sensitivity testing.

*All findings should be interpreted in the context of the data sources, spatial aggregation, statistical methods, and limitations documented above.*# Rainfall Variability and Vegetation Dynamics in Ghana (2000–2024)

## Project Overview

This project investigates the relationship between rainfall variability and satellite-derived vegetation greenness in Ghana from 2000 to 2024. It combines CHIRPS precipitation data with MODIS Normalized Difference Vegetation Index (NDVI) observations to explore how annual rainfall patterns relate to vegetation dynamics.

The project demonstrates an agricultural research workflow involving data validation, cleaning, exploratory analysis, statistical testing, visualization, and reproducible documentation using Python and Google Earth Engine.

## Research Objectives

1. Validate and summarize rainfall observations for Ghana.
2. Characterize annual rainfall variability and monthly seasonality from 2000 to 2024.
3. Examine annual vegetation greenness patterns using MODIS NDVI.
4. Evaluate the association between annual rainfall and NDVI.
5. Test the robustness of this association using detrending and leave-one-year-out sensitivity analysis.

## Data Sources

- **Rainfall:** CHIRPS precipitation data.
- **Vegetation:** MODIS MOD13Q1 NDVI product.
- **Study period:** 2000–2024.
- **Geographic scope:** Ghana.

## Methods and Tools

- Python and pandas for data processing.
- SciPy for statistical analysis.
- Google Colab for notebook-based analysis.
- Google Earth Engine for satellite data processing.
- Pearson and Spearman correlation.
- Linear trend analysis and leave-one-year-out sensitivity testing.

## Key Findings

- Mean annual rainfall estimate across the retained grid cells was approximately 1,204.5 mm.
- The estimated rainfall trend was +1.053 mm per year, but it was not statistically significant (p = 0.7692).
- Annual mean NDVI showed a slight negative linear trend of approximately −0.000570 NDVI units per year; this trend was not statistically significant (p = 0.3431).
- Annual rainfall and NDVI showed a moderate positive association (Pearson r = 0.5003, p = 0.0109).
- The positive association remained statistically significant after removing linear time trends (Pearson r = 0.5238, p = 0.0072).
- Leave-one-year-out correlations ranged from 0.4219 to 0.5574, with all 25 tests remaining significant at p < 0.05.
- ## Research Figures

### Figure 1. Annual Rainfall Trend in Ghana (2000–2024)

![Annual rainfall trend](figures/figure1_annual_rainfall_trend.png)

Annual rainfall estimates show year-to-year variability. The estimated linear trend was not statistically significant (p = 0.7692).

### Figure 2. Annual Vegetation Greenness Trend (2000–2024)

![Annual NDVI trend](figures/figure2_annual_ndvi_trend.png)

Satellite-derived annual mean NDVI showed a slight negative trend that was not statistically significant (p = 0.3431).

### Figure 3. Relationship Between Rainfall and Vegetation Greenness

![Rainfall and NDVI relationship](figures/figure3_rainfall_ndvi_relationship.png)

Annual rainfall estimates and annual mean NDVI showed a moderate positive association (Pearson r = 0.5003, p = 0.0109). This association does not establish causation, and NDVI is not a direct measure of forage biomass or quality.

## Repository Structure

- `notebooks/` — Research analysis notebooks.
- `data/` — Processed rainfall and integrated rainfall–NDVI datasets.
- `results/` — Statistical summaries and robustness results.
- `docs/` — Research methods, interpretation, and limitations.

## Limitations

Correlation does not establish causation. National annual averages may conceal regional differences, and the analysis does not explicitly account for possible temporal autocorrelation.

NDVI measures vegetation greenness, not forage biomass, nutritional quality, or livestock-accessible forage. The NDVI valid-spatial-coverage calculation also requires further verification. Therefore, findings should be interpreted as evidence about rainfall and vegetation greenness, not as direct measurements of forage production.

## Reproducibility

The notebooks document the analytical workflow and the processed datasets and statistical outputs are provided in the repository. Source data should be attributed to their respective providers.

## Future Work

Potential extensions include spatial comparisons among Ghana's ecological zones, seasonal rainfall–NDVI analysis, evaluation of additional environmental variables, and validation against direct forage or field measurements.
