# When Waste Becomes Risk: Modeling the Drivers of Toxic Chemical Release Occurrence in U.S. Facilities

## Author(s) and Date of Submission
**Author:** Prasanna Sai Rohit Durbha  
**Date of Submission:** 10th December 2025

## Project Structure

- `data/`  
  Contains the 2024 EPA TRI Basic Data File used in the analysis (cleaned facility–chemical records).

- `paper/`  
  Main Quarto `.qmd` document, rendered PDF, references, figures, and supporting files.

- `.gitignore`  
  Excludes system files and intermediate objects from version control.

- Additional diagnostic plots, notes, or exploratory analysis files as needed.

## Description

This project examines the conditions under which U.S. industrial facilities report **any on-site release of toxic chemicals** to the EPA’s **2024 Toxics Release Inventory (TRI)**.

Two statistical models were evaluated:

### 1. Multiple Linear Regression (MLR)
An initial MLR model attempted to predict the **continuous on-site release total** using production activity, waste-management quantities, hazard classifications, and industry sector.  
However, the TRI release distribution is **zero-inflated, highly skewed, and heavy-tailed**, leading to violations of linearity, normality, and homoscedasticity.  
Diagnostic plots showed that the MLR model collapsed predictions near zero and failed to explain variation in release quantity.

### 2. Logistic Regression
To align the model with the structure of the data, the response was reformulated as a binary indicator of **whether any release occurred**.

A logistic regression model was then fit using the same predictors.  
Key findings include:

- Facilities with **higher production-related waste**, **larger one-time releases**, and **higher production ratios** have substantially higher odds of reporting a release.  
- Hazard classifications such as **PBT**, **Clean Air Act chemical**, and certain **industry sectors** are strong predictors of release probability.  
- The model showed good calibration and fit, capturing real structure in release behavior that the linear model could not.

### Key Takeaway
Logistic regression provides a far more appropriate and interpretable framework than multiple linear regression for analyzing release occurrence in TRI data.  
The results highlight operational intensity and chemical hazard status as central drivers of whether facilities report any on-site releases.

## Use of External Resources (including LLMs)

External resources were used in preparing this project.

- **LLM-based chatbots** (such as ChatGPT) assisted with Quarto formatting and compilation issues.  
- No external datasets beyond the EPA 2024 TRI Basic Data File were used.  
- The project repository is available at:  
  **https://github.com/rohitDurbha/MATH261A_Paper2_RohitDurbha**

## License for Dataset

The analysis uses publicly available data from the **U.S. Environmental Protection Agency’s Toxics Release Inventory (TRI)**.  
**License:** TRI data are publicly accessible for research and non-commercial use. Refer to the EPA TRI Program for details on data access and permitted use.

## R

Analysis, modeling, and visualization were conducted in **R 4.5** using RStudio.  
Packages used include **tidyverse**, **ggplot2**, **broom**, and **kableExtra** for data wrangling, modeling, diagnostics, and reporting.

