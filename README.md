![Avatar](sample_pic/bender_hex_mini.png)

# Model Interpretation: Insights, Pitfalls, and Advanced SHAP Techniques

This repository explores key aspects of model interpretability, offering practical examples and discussions on common techniques and challenges.

## Understanding Model Interpretation: Pitfalls and Scope

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ThomasBury/interpreter/blob/main/interpret.ipynb)

This notebook provides a presentation on model interpretation, covering:

- Core definitions and an introduction to the field.
- A discussion on the feasibility, utility, and nuances of model interpretation versus real-world understanding.
- Practical, reproducible examples using:
  - Linear regression with interaction terms (illustrating the impact of increasing predictors and interactions).
  - LightGBM.
- An overview of various interpretation methods and their pitfalls:
  - Coefficient interpretation
  - Partial Dependence Plots (PDP)
  - Individual Conditional Expectation (ICE) curves
  - VINE
  - Shapley values

## Reconstructing SHAP Values in Natural Units

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ThomasBury/interpreter/blob/main/shap_exp.ipynb)

This notebook delves into obtaining SHAP attributions in the natural units of your target variable, particularly for models with exponential family distributions (e.g., Poisson, Gamma).

- **Goal**: To achieve exact additive SHAP attributions directly in the natural, interpretable units of the target, rather than multiplicative attributions that arise from exponentiating link-scale SHAP values.
- **Problem Addressed**: Standard SHAP values for such models are often on the link function's scale (e.g., log-scale). Converting these to natural units via exponentiation leads to multiplicative, not additive, feature importance.
- **Method Explored**: The notebook introduces and demonstrates an alternative approach for deriving these additive attributions in the original target scale.
- **Key Consideration**: It highlights that this alternative method for exact additive attribution in natural units is path-dependent, meaning the calculated SHAP values can vary depending on the order in which predictors are considered.
