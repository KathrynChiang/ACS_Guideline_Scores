# ACS-Guideline-Scores
*This is the in-development version. Please share comments, suggestions and errors/bugs found, either directly on the github page or by emailing kathryn.chiang@cancer.org.*

## Overview
`ACS-Guideline-Scores` is an R package designed to provide user-friendly, streamlined methods for calculating the [2020 American Cancer Society (ACS) Guideline for Diet and Physical Activity for Cancer Prevention](https://acsjournals.onlinelibrary.wiley.com/doi/full/10.3322/caac.21591) and [2022 ACS Guideline for Nutrition and Physical Activity for Cancer Survivors](https://acsjournals.onlinelibrary.wiley.com/doi/10.3322/caac.21721). 
It contains functions for operationalizing the 2020 ACS Guideline Score and each of the four individual lifestyle behavior components that make up the total score:
body weight (via body mass index, BMI), physical activity (PA), diet, and alcohol intake. The code provided here corresponds with *Scoring Alignment with the American Cancer Society Guidelines
for Cancer Prevention and Cancer Survivors (manscript under review)*. 

### What are the `ACS-Guideline-Scores`?
The ACS Guideline Scores were created to characterize concordance with the four lifestyle pillars of the ACS Guidelines to evaluate the potential association of overall adherence with disease outcomes *(ACS Guideline Score)* and for use in cancer survivorship research *(ACS Guideline Score for Cancer Survivors)*.

Current use of the ACS Guideline Scores has predominately taken place with the [ACS Cancer Prevention Study (CPS) cohorts](https://www.cancer.org/research/population-science/cancer-prevention-and-survivorship-research-team/acs-cancer-prevention-studies.html), but the scores can and should be used across cohorts and various populations. 

**Our goal is:**
- To increase the use of these standardized scoring methods for research within diverse study populations examining intermediate or long-term health outcomes.
- To provide methodological transparency for operationalizing the scores.

## How the `ACS-Guideline-Scores` works
The [ACS-Guideline-Scores](https://github.com/KathrynChiang/ACS_Guideline_Scores.git ) package preforms calculations in two steps:
1. Computation of each individual lifestyle component: body weight (via body mass index, BMI), physical activity (PA), diet, and alcohol intake. This includes prepping each variable and scaling it from 0-2.
2. Computation of the total ACS Guideline Score (0-8).

## Notes before applying the `ACS-Guideline-Scores` package to your data
All four individual lifestyle component scores can be used in isolation (on a scale of 0-2) or summed together as the total ACS Guideline Score (0-8). Below are considerations for each individual component:

Body Mass Index (BMI, kg/m2) 
- BMI variable must be pre-calculated using appropriate height and weight measurements.
- The BMI component is based on BMI measurements across two timepoints, instructions for application when only one BMI measurement is availiable is provided by Chiang et al (2026). 

Physical Activity (PA) 
- The function for classifying moderate-to-vigorous physical activity (MVPA) in this package is under the assumption that your variables for PA are already calculated in MET-hours/week according to the [Compendium of Physical Activity](https://pacompendium.com/).
  
Diet 
- The ACS Diet Score utilizes a more detailed scoring algorithm compared to the other 3 lifestyle factors. Given the [2020 ACS Guidelines for Cancer Prevention](https://acsjournals.onlinelibrary.wiley.com/doi/full/10.3322/caac.21591) does not provide specific cut-offs for what defines an optimal intakes of dietary factors in a healthy eating pattern; sex-specific, data-driven cutpoints for quartiles are used and recommended when data allows for it (i.e., normal distribution).
- It contains 6 food and beverage subgroups (each scaled 0-3): intake and variety of vegetables, intake and variety of fruits, whole grains, red/processed meats, sugar-sweetened beverages (SSBs), and highly processed foods (HPF)/refined grains (RG)
- The ACS Diet Score ranges from 0-12, with higher scores indicating greater dietary alignment. When used in isolation, the diet component can be described in quartiles or on a scale of 0-12.
- When apart of total ACS Guideline Scores, diet must be rescaled to 0-2 to ensure it recieves the same weight as the other factors in the score (i.e., BMI, PA, and alcohol intake).
- Therefore, the function for calculate diet is in two parts. Part 1 calculates the ACS Diet Score (0-12) across quartiles and part 2 rescales it to tertiles on a scale of 0-2.
- For more specifics regarding how the algorithm for the ACS Diet Score is calculated please refer to: *coming soon*

Alcohol Intake
- Daily averages for the amount an individual consumes of standard drink sizes are defined as 12 ounces of beer, 5 ounces of wine, or 1.5 ounces of 80-proof distilled spirits containing approximately 14 grams of ethanol.
- To operationalize this, alcohol variables that are captured off standard FFQ line items are used. Please note while 24-hour recall data can be used to calculate the scoring per Chiang et al 2026, *this function utilizes FFQ data only.*
- This includes servings per day of regular beer, light beer, red wine, white wine, and liquor.

## How can `ACS-Guideline-Scores` be used?
### Application Examples of the ACS Guideline Scores and Individual Lifestyle Components Within the ACS Cancer Prevention Study (CPS) Cohorts
- ACS Diet Score (only): [Associations of Socioeconomic and Geographic Factors With Diet Quality in US Adults](https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2793171)
- 2020 ACS Guideline Score (Coming soon)
- 2022 ACS Guidelines for Cancer Survivors: [Following the American Cancer Society Guideline for Cancer Survivors and Obesity-Related Cancer Survival](https://pubmed.ncbi.nlm.nih.gov/40174916/)

*Note: To promote research translation and comparability of research findings, we ask that clear documentation of any adaptations be shared should you decide to utilize the ACS Guideline Scores in your studies.*
## Future Plans & Updates as of 10/29/2025
This repo is in progress and we appreciate your patience as we thoroughly develop it. In our inital steps, we plan to publish functions and code for calculating the 2020 ACS Guideline Score for Cancer Prevention.
Following this, we hope to provide functions for calculating the 2022 ACS Guideline Score for Cancer Survivors and eventually strive to provide worked examples to increase reproducibility across cohorts.

In the meantime, thank you for your interest! We are excited to bring you the completed ACS-Guideline-Scores repo very soon!
