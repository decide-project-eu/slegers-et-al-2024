# Slegers et al. (2024)

Link to article: https://doi.org/10.1016/j.psj.2024.104197

## Abstract
In the Netherlands, the number of broiler production systems with higher welfare standards, using slower-growing broilers and decreased stocking densities, has increased over the last decade. This study aimed to investigate the effect of this change on antibiotic treatments, mortality, and footpad lesions. Data from national monitoring databases from 2013 to 2021 were used, resulting in 113,380 included flocks from 917 farms. Flocks were divided into conventional (CONV), medium-growing (MED), and slow-growing (SLOW), based on breed and slaughter age (median age: CONV 42 d; MED 50 d; SLOW 56 d). Generalized mixed-effect models were created to compare antibiotic treatments in and after the first week, total on-farm mortality, and footpad lesion scores between these 3 production systems. Year, quarter, flock size, thinning, number of houses, and regional density of poultry farms were included as fixed effects. Random effects were farm and veterinary practice in all models, with an additional random slaughterhouse effect to describe footpad lesions. Probability of treatment in the first week of age in CONV flocks overall years (7.2%, 95% CI [5.9, 8.7]) was higher than in MED (2.0%, 95% CI [1.6, 2.5]) and SLOW flocks (1.3%, 95% CI [1.0, 1.7]). Treatment probability after the first week was similarly higher in CONV flocks (14.7%, 95% CI [12.1, 17.6]) than in MED (3.2%, 95% CI [2.5, 4.0]) and SLOW flocks (2.2%, 95% CI [1.7, 2.9]). CONV flocks had a higher mean mortality (3.2%, 95% CI [3.0, 3.4]) than MED (2.0%, 95% CI [1.9, 2.1]) and SLOW flocks (1.9%, 95% CI [1.8, 2.0]). Regarding footpad lesions, CONV flocks had the highest mean scores (range 0–200) over all years, whereas SLOW flocks had the lowest scores (CONV: 46.1, 95% CI [42.1, 50.6]; MED: 21.3, 95% CI [18.9, 24.0]; SLOW: 13.2, 95% CI [11.5, 15.1]). This analysis of data from flocks over a 9-yr period indicates that switching from conventional to alternative production systems with higher welfare standards could positively affect broiler health and antibiotic use.


## Notes on scripts

Data on flock level from different sources was used to combine into one dataset for the analyses. Data processing was performed in PySpark through the data processing platform Databricks.

All statistical analyses were performed using R version 4.2.2, also in Databricks. The following R packages were installed on the cluster:
- lme4
- glmmTMB
- dplyr
- ggplot2
- lsmeans
- multcomp
- multcompView
- performance
- car
- insight (optional, for additional graphs)
- ggsignif (optional)

## Data processing scripts
[Clean CRA data (antibiotics registrations)](data-processing/1_1%20Data%20CRA.ipynb)
[Clean PMP data (poultry flock monitoring)](data-processing/1_2%20PMP%20data.ipynb)
[Clean KIP slaughter transport data](data-processing/1_3%20Data%20Slaughter.ipynb)
[Merge datasets on house level](data-processing/2_1%20Merging%20Events.ipynb)
[Create flocks and select flocks for final dataset](data-processing/2_2%20Create%20flocks%20and%20final%20dataset.ipynb)

## Models
[Week 1 antibiotic treatments](analysis/Analysis%20Slow-growing%20-%20AB%20WK1.Rmd)
[Antibiotic treatments after week 1](analysis/Analysis%20Slow-growing%20-%20AB.Rmd)
[Footpad lesion scores](analysis/Analysis%20Slow-growing%20-%20FPL.Rmd)
[Mortality](analysis/Analysis%20Slow-growing%20-%20Mort.Rmd)
[Create graphs with combined results from antibiotic models](analysis/AB%20Plots.Rmd)

