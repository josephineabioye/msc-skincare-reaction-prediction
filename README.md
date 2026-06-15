# Tittle: Comparison and Evaluation of Machine Learning Approaches for Predicting Adverse Skincare Reactions from Product Ingredient Lists

MSc Computer Science Project | University of Hertfordshire | 

## Overview

This project investigates whether established machine learning approaches can predict adverse skincare reactions from product ingredient lists using consumer review data as the source of reaction labels. It compares three approaches: a rule-based ingredient blacklist, logistic regression, and gradient boosting. The work also examines how predictive performance varies across different skin types.

## Research questions

1. Which of the three approaches achieves the highest classification performance?
2. Does predictive performance vary across skin types, and which approach performs most equitably?
3. How do the results compare with published findings in related research?
4. What recurring error categories does the best-performing approach produce?

## Methodology

The project uses publicly available skincare product and consumer review data from Kaggle. Adverse reaction labels are extracted from review text using a combination of keyword matching, sentiment analysis, and selective use of a pre-trained language model. The three approaches are evaluated using accuracy, precision, recall, F1 score, and AUC-ROC.

## Repository structure

- `notebooks/` - Jupyter and Colab notebooks for exploratory work and experiments
- `src/` - Python scripts and modules
- `data/` - Data directory (note: actual datasets are not included in this repository; see Dataset section below)
- `results/` - Output files, figures, and evaluation results
- `references/` - Background documents and key references

## Dataset

The datasets used in this project are publicly available through Kaggle. Due to their size and licence terms, they are not included in this repository. To reproduce this work, download the relevant datasets from Kaggle and place them in the `data/` directory.

## Status

This project is in active development as part of an MSc dissertation. Work runs from May 2026 to September 2026.

## Author

Josephine Abioye  
MSc Computer Science  
University of Hertfordshire

## Licence

This project is licensed under the MIT License. See the LICENSE file for full terms.
