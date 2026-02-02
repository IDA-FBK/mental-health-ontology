# Validation Case for MIAO

The goal of this validation is to demonstrate the applicability of MIAO to a real-world mental health detection scenario based on social media data and deep learning models.

## Validation Study Overview

The validation is based on a published research study on the detection of mental illnesses from Reddit data using machine learning and deep learning techniques ([Kim et al., 2020](https://www.nature.com/articles/s41598-020-68764-y)). In the study:

- **488,472 social media posts** were collected from Reddit communities related to six mental illnesses:
  - Depression  
  - Anxiety  
  - Bipolar Disorder  
  - Borderline Personality Disorder (BPD)
  - Schizophrenia  
  - Autism  

- Two binary classification models were trained:
  - **Distributed gradient-boosted decision trees (XGBoost)** 
  - **Convolutional Neural Network (CNN)**

The models aim to identify individuals potentially affected by mental health conditions based on their social media activity, as a supplementary tool for monitoring mental health states.

## Mapping to MIAO

The validation case contains a **complete semantic mapping of the study to MIAO**, showing how AI detection processes, data, models, results, and evaluations are represented using the ontology. The figure above presents a **simplified view** of this mapping for clarity:

- Focuses on a single mental illness (autism)  
- Highlights a subset of hyperparameters (epoch and learning rate)
- Shows one evaluation metric (accuracy)  
- Omits concepts not directly involved in the example  

### Contents

- **`miao-validation.ttl`**  
  A Turtle file containing the full MIAO-based representation of the study, including:  
  - Datasets and their characteristics  
  - Extracted features (TF-IDF and Word2Vec)  
  - Detection processes modeled as instances of `miao:AutomaticMentalIllnessesDetection`  
  - AI models (XGBoost and CNN) and their configurations  
  - Hyperparameters (e.g., number of epochs, learning rate)  
  - Detection results as `miao:MentalIllnessesSet`  
  - Confidence values associated with each detected mental illness  
  - Evaluation specifications, procedures, metrics (e.g., accuracy and F1), and computed values  

The TTL file includes **all mental illnesses, hyperparameters, and evaluation metrics** considered in the original study.

### Modeling Assumptions

Since the original study does not explicitly specify software libraries, **XGBoost** and **PyTorch** are assumed as representative implementations.

## Purpose and Reuse

This validation case demonstrates how MIAO can:
- represent heterogeneous AI-based detection workflows,
- preserve provenance and confidence information,
- support interoperability with machine learning and semantic web standards.

The provided resources can be reused as:
- an example for ontology evaluation,
- a template for modeling similar mental health detection studies,
- a basis for extending MIAO to other datasets or AI models.

## References

[Kim et al., 2020] Kim, J., Lee, J., Park, E., Han, J.: *A deep learning model for detecting mental illness from user content on social media*. Scientific Reports 10(1), 11846 (2020), https://www.nature.com/articles/s41598-020-68764-y.
