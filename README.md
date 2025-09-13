# quora-question-pairs
Dataset Link - https://www.kaggle.com/c/quora-question-pairs

website: https://divya-tiwari-13.github.io/NLP-Quora/

# Quora Question Pair Similarity Competition
  This repository contains the code and analysis for the Quora Question Pairs competition. The goal of this competition is to identify whether a pair of questions asked on Quora are duplicates or not. This is a binary classification problem.

  This project explores various approaches, starting from a simple Bag of Words (BoW) model and progressively adding more complex features to improve the classification accuracy.

### Files Overview
  • [initial_EDA.ipynb](https://github.com/divya-tiwari-13/quora-question-pairs/blob/main/initial_EDA.ipynb): This notebook performs an initial Exploratory Data Analysis on the Quora Question Pairs dataset. It delves into the distribution of duplicate and non-duplicate pairs, analyzes the question lengths, and explores the text data to gain insights before feature engineering and modeling.

  • [only_bow.ipynb](https://github.com/divya-tiwari-13/quora-question-pairs/blob/main/only_bow.ipynb): This notebook implements a baseline model using a simple Bag of Words (BoW) approach. The questions are converted into a sparse matrix of token counts, which is then used to train various classification models.

  • [bow_with_basic_features.ipynb](https://github.com/divya-tiwari-13/quora-question-pairs/blob/main/bow_with_basic_features.ipynb): This version builds upon the simple BoW model by incorporating several basic, handcrafted features. These features provide more information about the lexical and structural relationship between the two questions.

  • [bow_with_preprocessing_and_advanced_features.ipynb](https://github.com/divya-tiwari-13/quora-question-pairs/blob/main/bow_with_preprocessing_and_advanced_features.ipynb): This is the most comprehensive approach. It includes text preprocessing steps (like removing stopwords, stemming) and adds more advanced features related to word overlap, fuzzy string matching, and token-based statistics before applying the Bag of Words vectorization.

### Methodology and Results
  The project follows an iterative approach to model building. We started with a simple baseline and gradually added complexity in the form of feature engineering to see how it impacts performance. The primary metric used for evaluation is Accuracy.

### Model Performance Comparison
  Here is a summary of the accuracy achieved by different models across the various notebooks. The models were trained on a sample of the data.

<img width="713" height="431" alt="Screenshot 2025-09-13 at 4 01 28 PM" src="https://github.com/user-attachments/assets/1baf3e35-ea65-4555-b731-0f0677c3aaba" />


### Key Findings
1. Baseline Performance: A simple Bag of Words model provides a decent baseline, with Logistic Regression performing slightly better than tree-based models on this sparse feature set, achieving around 75% accuracy.

2. Impact of Basic Features: Adding basic, manually engineered features provided a significant boost in performance. The accuracy jumped by approximately 8-10% when using an XGBoost model, demonstrating the value of providing the model with more explicit signals about the relationship between the questions.

3. Advanced Features and Preprocessing: The best performance was achieved by combining text preprocessing with a richer set of advanced features. Cleaning the text and adding fuzzy matching and more detailed token-based features allowed the Random Forest model to reach nearly 86% accuracy. This highlights that a combination of NLP techniques and thoughtful feature engineering is crucial for this task.

### Conclusion
The project demonstrates a clear path to improving model performance on the Quora Question Pairs task. While a simple BoW model is a good starting point, the most significant gains come from creating meaningful features that capture the semantic and structural similarities between questions. The final model in bow_with_preprocessing_and_advanced_features.ipynb stands out as the most effective approach among the ones tested.
