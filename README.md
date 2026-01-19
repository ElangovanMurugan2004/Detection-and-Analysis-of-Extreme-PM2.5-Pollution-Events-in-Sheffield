# Detection and Analysis of Extreme PM2.5 Pollution Events in Sheffield

## Project Overview

This research investigates extreme PM2.5 (particulate matter ≤2.5 micrometers) pollution events in Sheffield, United Kingdom, during 2024. The analysis uses 5,990 hourly measurements from the Sheffield Devonshire Green monitoring station to identify temporal patterns, define threshold concentrations, and characterize the frequency and severity of pollution episodes. This work provides a foundation for understanding pollution dynamics and supporting evidence-based air quality management strategies.

**Student Registration Number:** 250196960  
**Module Code:** IJC437  
**Module Title:** Introduction to Data Science  
**Word Count:** 2,984 words

---

## Research Objectives

### Primary Aim
To identify and characterise extreme PM2.5 pollution events in Sheffield during 2024 by analysing their temporal patterns and defining threshold concentrations.

### Research Questions
1. What defines extreme PM2.5 pollution in Sheffield's urban environment, and how often do such conditions occur?
2. How does PM2.5 pollution in Sheffield vary across different time scales during 2024?
3. What patterns characterize extreme pollution episodes in Sheffield during 2024?

---

## Dataset Specifications

| Parameter | Description |
|-----------|-------------|
| Data Source | OpenAQ Platform / European Environment Agency |
| Monitoring Station | Sheffield Devonshire Green (Station ID: 2508) |
| Geographic Coordinates | 53.378622°N, 1.478096°W |
| Pollutant Measured | PM2.5 (particulate matter ≤2.5 μm) |
| Temporal Coverage | January 1 – October 27, 2024 |
| Total Observations | 5,990 hourly measurements |
| Study Duration | 300 days |
| Data Completeness | 100% (zero missing values) |
| Measurement Units | μg/m³ (micrograms per cubic meter) |

---

## Principal Findings

### Extreme Event Characterization

The 95th percentile threshold for extreme PM2.5 events was established at 19.00 μg/m³. A total of 329 extreme hours (5.5% of observations) were identified, with the maximum concentration reaching 39.00 μg/m³ during a sustained 14-hour episode on March 9-10, 2024.

### Statistical Summary

| Metric | Value (μg/m³) |
|--------|---------------|
| Mean | 7.41 |
| Median | 6.00 |
| Standard Deviation | 5.33 |
| Range | 1.00 – 39.00 |
| Interquartile Range | 4.00 – 9.00 |
| 95th Percentile | 19.00 |
| Coefficient of Variation | 0.72 |

### Temporal Patterns

**Seasonal Variation:** March recorded the highest monthly mean concentration (10.52 μg/m³), while July recorded the lowest (4.39 μg/m³), representing a 2.4-fold seasonal difference driven by winter-spring heating emissions and reduced atmospheric dispersion.

**Diurnal Variation:** Concentrations peaked at 23:00 (8.27 μg/m³) and reached minimum levels at 03:00 (7.26 μg/m³), showing a modest 14% diurnal amplitude that indicates dominance of regional background pollution over local traffic sources.

**Extreme Event Distribution by Month:**
- September: 124 events (37.7%)
- March: 106 events (32.2%)
- May: 75 events (22.8%)
- February: 20 events (6.1%)
- June: 4 events (1.2%)
- January, April, July, August, October: 0 events

The bimodal seasonal clustering, with peaks in spring (March-May) and late summer (September), represents an atypical pattern that warrants further meteorological investigation.

---

## Technical Requirements

### Software Dependencies
- R version 4.0 or higher
- RStudio (recommended)

### Required R Packages
```r
packages <- c("dplyr", "tidyr", "lubridate", "ggplot2", "stats", "corrplot")
```

All required packages are automatically installed by the analysis script if not already present in the R environment.

---

## Execution Instructions

### Setup Procedure

1. Clone or download the repository to your local machine
2. Place the PM2.5 data CSV file in the `data/` directory as `data.csv`
3. Open `analysis_complete.R` in RStudio
4. Modify the working directory path on line 25:
   ```r
   setwd("your/path/to/project/directory")
   ```
5. Execute the entire script using the Source button or `Ctrl+Shift+S` (Windows) / `Cmd+Shift+S` (Mac)

### Expected Runtime
Approximately 2-3 minutes on standard hardware.

### Output Generation
The script automatically generates:
- Six publication-quality visualizations (PNG format, 300 DPI) in `figures/`
- Four processed datasets (CSV format) in `data/processed/`
- Comprehensive statistical summaries in the R console

---

## Methodology

### Analytical Pipeline

The analysis follows a six-phase systematic workflow:

**Phase 1: Data Acquisition**  
Air quality data obtained from the OpenAQ platform, which aggregates measurements from official government monitoring networks including the European Environment Agency.

**Phase 2: Data Preprocessing**  
Five-step procedure including column standardization, datetime conversion to POSIXct format, variable selection, missing value treatment, temporal alignment to hourly intervals, and aggregation of duplicate timestamps.

**Phase 3: Exploratory Data Analysis**  
Calculation of summary statistics, distribution analysis, time series visualization, and assessment of temporal variability using coefficient of variation.

**Phase 4: Extreme Event Detection**  
Application of 95th percentile threshold methodology for binary classification of extreme versus normal pollution hours, with frequency and severity characterization.

**Phase 5: Temporal Pattern Analysis**  
Examination of diurnal cycles through hourly averaging, seasonal patterns through monthly aggregation, and identification of extreme event clustering patterns.

**Phase 6: Visualization and Reporting**  
Generation of professional-grade visualizations using ggplot2, data export for reproducibility, and comprehensive statistical reporting.

---

## Results and Discussion

### Research Question 1: Extreme Event Definition and Frequency

Extreme PM2.5 pollution events in Sheffield are defined as hourly concentrations at or above 19.00 μg/m³, representing the 95th percentile of the distribution. During the study period, 329 extreme hours occurred (5.5% of observations), averaging 1.1 hours per day but exhibiting strong temporal clustering. The episodic rather than chronic nature of extreme pollution enables targeted intervention strategies during high-risk periods.

### Research Question 2: Temporal Variation Patterns

PM2.5 concentrations demonstrated pronounced seasonal variation with a 2.4-fold difference between the March peak (10.52 μg/m³) and July minimum (4.39 μg/m³). This pattern reflects elevated winter-spring heating emissions, reduced atmospheric mixing heights, and decreased precipitation, with cleaner conditions during summer months. Diurnal variation was modest (14% amplitude), indicating that regional background pollution dominates over local traffic sources. No long-term trend was detected, suggesting stable baseline air quality throughout the study period.

### Research Question 3: Extreme Episode Characteristics

Extreme events exhibited highly non-uniform distribution with pronounced bimodal seasonal clustering. September recorded 124 events (37.7%), March recorded 106 events (32.2%), and May recorded 75 events (22.8%), while five months recorded zero extreme events. This pattern contradicts typical UK urban pollution profiles and suggests anomalous meteorological conditions during September 2024. The most severe pollution occurred during a sustained 14-hour episode on March 9-10, with concentrations of 36-39 μg/m³ exceeding WHO annual guidelines by 7.8 times and 24-hour guidelines by 2.6 times.

---

## Visualizations

All visualizations are generated in high-resolution PNG format (300 DPI) suitable for publication or presentation:

**PM25_TimeSeries.png** – Complete hourly time series with extreme events highlighted, demonstrating episodic pollution pattern and temporal clustering.

**PM25_Histogram.png** – Frequency distribution showing positive skewness, with approximately 80% of observations below 10 μg/m³.

**PM25_HourlyPattern.png** – Diurnal cycle visualization with mean concentrations and standard error bands across 24-hour periods.

**PM25_MonthlyPattern.png** – Seasonal pattern bar chart revealing pronounced variation between winter-spring and summer months.

**PM25_MonthlyBoxplot.png** – Distribution comparisons across months showing median values, interquartile ranges, and outliers.

**PM25_ExtremeByMonth.png** – Stacked bar chart illustrating the temporal distribution of extreme versus normal pollution hours, revealing bimodal clustering.

---

## Study Limitations

1. **Spatial Coverage:** Analysis relies on a single urban background monitoring location and does not capture spatial heterogeneity across Sheffield.

2. **Temporal Coverage:** The ten-month monitoring period excludes November-December, potentially underrepresenting winter extreme events.

3. **Chemical Speciation:** Absence of compositional data prevents source-specific attribution and limits health risk assessment specificity.

4. **Statistical Testing:** Temporal patterns lack formal hypothesis testing (ANOVA, t-tests) to quantify statistical significance.

5. **Meteorological Integration:** Weather influences are inferred but not quantified through direct correlation with measured meteorological variables.

6. **Threshold Validation:** The 95th percentile threshold was not validated against alternative percentile thresholds to assess classification robustness.

---

## Future Research Directions

### Recommended Extensions

**Meteorological Integration:** Incorporate wind speed and direction, temperature, precipitation, and boundary layer height data to quantify weather-pollution relationships and develop predictive models for early warning systems.

**Spatial Expansion:** Deploy monitoring across multiple Sheffield sites to characterize spatial gradients and distinguish local versus regional pollution sources.

**Chemical Speciation:** Analyze PM2.5 composition (sulfates, nitrates, organic compounds, black carbon) to enable source apportionment and identify specific emission sectors for targeted interventions.

**September 2024 Investigation:** Conduct detailed analysis of the atypical September extreme event cluster to determine whether this represents recurring seasonal patterns or anomalous meteorological conditions.

**Health Impact Assessment:** Integrate epidemiological methods to quantify population exposure estimates and calculate attributable health burden from identified extreme pollution episodes.

**Advanced Statistical Methods:** Apply time-series modeling, change-point detection, and machine learning algorithms for improved pattern recognition and forecasting capabilities.

---

## Compliance with WHO Guidelines

| Guideline | Threshold | Sheffield Performance |
|-----------|-----------|----------------------|
| WHO Annual Mean | 5.0 μg/m³ | 7.41 μg/m³ (48% exceedance) |
| WHO 24-hour Mean | 15.0 μg/m³ | 493 hours exceeded (8.2%) |
| 95th Percentile (Study) | 19.0 μg/m³ | 329 hours exceeded (5.5%) |

While Sheffield's annual mean exceeds WHO annual guidelines, concentrations remain below UK regulatory limits. The episodic nature of extreme events suggests meteorological control rather than persistent emission sources.

---

## References

- World Health Organization (2021). WHO global air quality guidelines: Particulate matter
- European Environment Agency (2022). Air quality in Europe 2022
- Department for Environment, Food & Rural Affairs (2023). Air quality statistics in the UK
- Tai et al. (2010). Correlations between PM2.5 and meteorological variables
- Katsouyanni et al. (2001). Short-term effects of ambient particles on mortality (APHEA2)
- Peng et al. (2005). Seasonal analyses of air pollution and mortality in 100 US cities

## License

This project is submitted as academic coursework. All rights reserved for educational purposes.
