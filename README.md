# Causal impact analysis of marriage to depression
Analysis of how marriage effects the chances of having depression based on NLS (National Longitudinal Survey) data. Analysis was done using traditional methods (simple logistic regression, PSM, IPW) and newer methods (t-learner, double machine learning) w/ DoWhy & EconML.

## Defined estimand
In the US national longitudinal survey (NLS97) respondents, what is the probability (or odds) difference to scoring 9 or higher (i.e. sig. chance in having depression) for CESD-7</span> in the 2019 survey between the respondents that are married VS never married at the time of the survey?

## Notebooks
   * [NLS-prep](https://github.com/kiroah/marriage_and_depression/blob/main/NLS-prep.ipynb) - Preliminary analysia and processing of the NLS data to decide on the estimand and feasibility
   * [NLS-nonml](https://github.com/kiroah/marriage_and_depression/blob/main/NLS-nonml.ipynb) - Causal impact analysis using non-ML methods iteratively, starting from simple logistic regression to using PSM (Propensity Score Matching) to IPW (Inverse Probability Weighting) and adding more features
   * [NLS-ml](https://github.com/kiroah/marriage_and_depression/blob/main/NLS-ml.ipynb) - Causal impact analysis using ML methods, using logistic regression and LGBM as the classifier and using meta-learner techniques S-Learner, T-Learner, and DML (Double Machine Learning)

## Results 
   * At a high level, getting married will decrease the odds of scoring 9 or higher in CES-D7 (i.e. sig chance in having depression per [research](https://www.mdpi.com/1660-4601/18/3/1361)] by at least by 20%, depending on the impact analysis method
      * For non-ML methods, it was 40~60% (though 60% came from very naive model)
      * For ML methods, about 20%
   * That being said, if you look at probability difference (basically Average Treatment Effect), it is 2% (or more) decrease when getting married.
      * For non-ML methods, it was 3-5%
      * For ML methods, about 2%
      * Since there were only 10% of responders scoring 9 or higher in CES-D7, this makes sense
   * Some refutation and model validations were done, but if this was for a real research beyond demo purposes, further model testing, variable selection and causal model (DAG) building is needed
