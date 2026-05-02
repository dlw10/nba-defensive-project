# NBA Defensive Position Classification

## Project Overview

This project investigates whether NBA player positions can be predicted using only defensive box score statistics. We build and compare multiple machine learning models, including logistic regression, decision trees, random forests, neural networks, k-means clustering, and a large language model (Gemini), to evaluate how well defensive performance reflects positional roles.

We also examine whether defensive statistics better capture traditional positions (Guard, Forward, Center) or underlying defensive archetypes (e.g., interior vs perimeter defenders).

---

## Research Questions

1. Can a player’s defensive statistics alone be used to accurately identify their NBA position?
2. How do defensive box-score statistics profile NBA players’ defensive archetypes and/or playstyles?

---

## Dataset

- Source: NBA.com
- Season: 2025-2026
- Sample size: 165 players
- Features: 26 defensive box score statistics (e.g., rebounds, blocks, opponent points)
- Target variable: Player position (Guard, Forward, Center)

We filtered players to include only those who played at least 65 games to ensure statistical reliability of season-level defensive metrics.

---

## Methods

We implemented a machine learning pipeline consisting of four stages:

1. Data construction  
2. Preprocessing  
3. Model development  
4. Comparative evaluation

### Preprocessing
- Removed non-statistical identifiers (player names, team info)
- Applied Box-Cox transformation to skewed features
- Standardized features using z-score normalization
- Simplified hybrid position labels into three classes:
  - Guard (0)
  - Forward (1)
  - Center (2)

---

## Models

We evaluated multiple modeling approaches:

### Supervised Models
- Logistic Regression (baseline)
- Decision Tree
- Random Forest
- Neural Network

### Unsupervised Model
- K-Means Clustering

### Large Language Model
- Gemini (zero-shot classification using structured prompts)

---

## Evaluation

Due to class imbalance (guards are the majority class), we use:

- Weighted F1 Score (primary metric)
- Accuracy (secondary reference only)

Weighted F1 is preferred because it accounts for imbalance across positional classes.

---

## Key Findings

- Defensive statistics are more effective at distinguishing **interior vs perimeter defenders** than strict positional labels.
- Centers form the most distinct cluster across models.
- Guards and forwards show substantial overlap in defensive profiles.
- Ensemble and neural models do not significantly outperform simpler models.
- Random Forest feature importance highlights rebounding and blocking metrics as key predictors.

---

## Limitations

- Dataset size is relatively small (~165 players)
- LLM evaluation is limited due to API cost constraints
- Position labels may not fully reflect modern “positionless basketball”

---

## Technologies Used

- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- Google Gemini API
- Jupyter / Google Colab

---

## Authors

- Kairi Mano  
- Dylan Wall  
- Advisor: Dr. Akane Sano (Rice University)
