# SES and Digital Engagement in Precision Diabetes Care (DiaLA)

MSc Modelling for Global Health | Dissertation Code | University of Oxford.

Author: Shan Lateef. Supervisors: Dr. R. M. Anjana, Dr. V. Baskar, and Ms. AnandaPerumal Lavonya (Madras Diabetes Research Foundation)

## What is in this repository

Analysis notebooks exploring the relationship between socioeconomic status (as captured in the Kuppuswamy occupational score) and engagement with the DiaLA diabetes application, the relationship between digital engagement and clinical outcomes, and whether there is any interaction between socioeconomic status and clinical outcomes in a retrospective cohort drawn from Dr. Mohan's Diabetes Specialities Centre and the Madras Diabetes Research Foundation (MDRF), Chennai, India (October 2022 to October 2025).

Since I was inexperienced with Python programming at the start of this project, my data mentor and co-workers at MDRF taught me Python and pandas and collaborated with me to develop the analysis code in these notebooks. 

## Data

Actual patient data does not appear in this repository and is not publicly available; it is subject to MDRF security (see Data Availability Statement in the dissertation).

In place of real data, this repository holds a mock dataset (`mock-data/`) with the same file structure, sheet names, and column names as the real data, but with randomly generated non-identifying data, so the full analysis pipeline can be completed without access to the actual records.

`mock-data/SES_Mastersheet.xlsx`: one line per patient, in all three engagement groups (occupation, age, gender), for use in notebook 01 (SES mapping and engagement-group comparisons).

`mock-data/Active_Inactive_Non-Diala_Mock.xlsx`: three sheets, `Active_Users`, `Inactive_Users`, and `Non_DiaLA_Users`, each holding the mock laboratory values (HbA1c, BMI, HDL, triglycerides, serum cholesterol) before and after intervention, for use in notebooks 02 through 07. Different sheets will have different columns, mirroring the real data, such as the lack of diabetes duration for the Non-DiaLA users and little lab data other than HbA1c and BMI for the Inactive users.

## Running the analysis

Open the `notebooks/` folder in VS Code and run each notebook in numbered order, 01 through 07. Each is set to read from the `mock-data/` folder by default.

Pre-run outputs are available in the outputs folder.

## Software version and packages

Python 3.14.16
Packages used: pandas, numpy, scipy, statsmodels, matplotlib, openpyxl (required by pandas to read .xlsx files)

## References

A few general references I drew on for the statistical approach used throughout these notebooks:

- Baron, R. M., & Kenny, D. A. (1986). The moderator-mediator variable distinction in social psychological research: Conceptual, strategic, and statistical considerations. *Journal of Personality and Social Psychology*, 51(6), 1173-1182. (Basis for the mediation analysis approach in the SES-to-engagement-to-outcome models.)
- Cohen, J. (1988). *Statistical Power Analysis for the Behavioral Sciences* (2nd ed.). Lawrence Erlbaum Associates. (Effect size conventions used for Cohen's D and correlation interpretation throughout.)
- SciPy documentation, `scipy.stats`: https://docs.scipy.org/doc/scipy/reference/stats.html (Kruskal-Wallis, Mann-Whitney U, Shapiro-Wilk, and Spearman correlation implementations.)
- statsmodels documentation: https://www.statsmodels.org/stable/index.html (Multinomial logistic regression, OLS, and ANCOVA implementations.)
