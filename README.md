[![Open the analysis paper](https://img.shields.io/badge/Open%20as-PDF-red.svg?logo=adobeacrobatreader)](https://github.com/NBeibarys/CapstoneProject-Assessing-Professor-Effectiveness-APE--Using-Python/blob/main/analyses/capstone_project_report.pdf)
[![Open Notebook](https://img.shields.io/badge/Open-Jupyter-orange.svg?logo=jupyter)](https://github.com/NBeibarys/CapstoneProject-Assessing-Professor-Effectiveness-APE--Using-Python/blob/main/analyses/analyses.ipynb)

# Capstone project - Assessing Professor Effectiveness (APE)
In this project, I apply statistical inference and supervised learning techniques to analyze patterns in student evaluations of professors using a large-scale, real-world dataset from `RateMyProfessor`. The analysis addresses 10 hypothesis-driven questions on rating behavior, gender differences, teaching difficulty, and qualitative teaching attributes, with the goal of extracting insights relevant to academic assessment, recommendation systems, and audience segmentation.

Because the data are observational, survey-based, and contain ordinal and non-Gaussian variables, non-parametric statistical methods are used throughout, including Mann-Whitney U, Kolmogorov-Smirnov, and Kruskal-Wallis tests. Effect sizes are quantified using Cliff's delta with 95 percent confidence intervals obtained via bootstrapping. To control false positives across multiple hypothesis tests, a conservative per-test significance threshold of α = 0.005 is applied.

Beyond hypothesis testing, the project extends the analysis using supervised learning models for regression and classification. These models predict average ratings, perceived difficulty, and “pepper” status using numerical features and normalized tag-based indicators. Model performance is evaluated using cross-validation and appropriate metrics such as R², RMSE, ROC-AUC, and class-balanced measures. Feature importance and SHAP values support interpretability.

Overall, the project demonstrates a principled end-to-end workflow combining rigorous statistical testing, effect size estimation, and machine learning, with an emphasis on reproducibility, interpretability, and methodological correctness when working with observational rating data.

## Questions: 
1) Activists have asserted that there is a strong gender bias in student evaluations of professors, with male professors enjoying a boost in rating from this bias. While this has been celebrated by ideologues, skeptics have pointed out that this research is of technically poor quality, either due to a low sample size – as small as n = 1 (Mitchell & Martin, 2018), failure to control for confounders such as teaching experience (Centra & Gaubatz, 2000) or obvious p-hacking (MacNell et al., 2015). We would like you to answer the question of whether there is evidence of a pro-male gender bias in this dataset.  
2) Is there a gender difference in the spread (variance/dispersion) of the ratings distribution? 
3) What is the likely size of both of these effects (gender bias in average rating, gender bias in spread of average rating), as estimated from this dataset? Please use a 95% confidence and make sure to report 
each/both. 
4) Is there a gender difference in the tags awarded by students? Make sure to teach each of the 20 tags for a potential gender difference and report which of them exhibit a statistically significant difference. Comment on the 3 most gendered (lowest p-value) and least gendered (highest p-value) tags.  
5) Is there a gender difference in terms of average difficulty? Again, a significance test is indicated.
6) Please quantify the likely size of this effect at 95% confidence.  
7) Build a regression model predicting average rating from all numerical predictors (the ones in the rmpCapstoneNum.csv) file. Make sure to include the R2 and RMSE of this model. Which of these 
factors is most strongly predictive of average rating? 
8) Build a regression model predicting average ratings from all tags (the ones in the rmpCapstoneTags.csv) file. Make sure to include the R2 and RMSE of this model. Which of these tags is 
most strongly predictive of average rating? Also comment on how this model compares to the previous one. 
9) Build a regression model predicting average difficulty from all tags (the ones in the rmpCapstoneTags.csv) file. Make sure to include the R2 and RMSE of this model. Which of these tags is 
most strongly predictive of average difficulty? 
10) Build a classification model that predicts whether a professor receives a “pepper” from all available factors (both tags and numerical). Make sure to include model quality metrics such as AU(RO)C and also address class imbalance concerns.  

**EXTRA WORK DONE BEYOND PAPER:** feature engineering, complexity reduction, metrics maximization. 

## Project Structure: 
- `analyses` - Jupyter notebook with code and analysis done, and project paper.  
- `data` - main datasets used for analysis. 
- `project_guidelines` - project guidelines and scientific papers used for analysis.

## Tools, Technologies, and Statistics:
- **Python**
- **Jupyter Notebook**
- **Non-parametric testing** (Mann-Whitney U, Kruskal-Wallis, Kolmogorov-Smirnov tests)
- **Effect size analysis** [(Cliff's delta)](https://github.com/NBeibarys/intro-to-data-science-capstone/blob/main/project_guidelines/Using%20Cliff%E2%80%99s%20Delta%20as%20a%20Non-Parametric%20Effect%20Size%20Measure.pdf)
- **Effect size 95% CI bootstrapping**
- **Supervised learning** (Linear Regression, Logistic Regression, LightGBM Regressor and Classifier)
- **Exploratory data analysis**
- **Feature engineering** (scaling, imputation, polynomial features, domain-based features) 
- **Cross-validation** (Kfold and StratifiedKFold)
- **Hyperparameter optimization** (Optuna with TPE Sampler) 
- **Model evaluation metrics** (ROC-AUC, precision, recall, F1, accuracy, confusion matrix, R2, RMSE)
- **Regularization** (Lasso, Ridge, ElasticNet)
- **Model Interpretability** (feature importance, SHAP value analysis) 

## How to Run
1. Clone the repository. 
2. Install dependencies with `pip install -r requirements.txt`
3. Open `analyses\project_code.ipynb`
4. Run all cells before Q1. This includes imports, helper functions, data loading, and preprocessing.
5. After step 4, each question is independent.
6. For any question QX, run all cells in that section starting from the cell that defines qX_df. Skipping that first cell breaks the rest of the section.

## Project Members
1. Beibarys Nyussupov
2. Joseph Tadros
3. Luke Ducker
