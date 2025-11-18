# Mental Illness Detection Ontology Examples

This folder provides examples of representing **mental illness detection activities** using MIAO, including both **manual** and **automatic detection**. These examples are used to answer [competency questions](https://github.com/IDA-FBK/mental-health-ontology/tree/conceptualization-dev/reqs%26cqs), 
implemented in a [google colab notebook](https://github.com/IDA-FBK/mental-health-ontology/tree/conceptualization-dev/notebook), demonstrating how mental illness detection data can be queried and analyzed.
This folder contains two examples:

1. `ex1-manual.ttl` – manual detection by a clinical expert  
2. `ex2-automatic.ttl` – automatic detection using deep learning models  

---
## Example 1: Manual Detection

**File:** `ex1_manual.ttl`  

This example models a **manual mental illness detection activity** conducted by a clinical psychologist (Dr. Laura García) using patient-provided questionnaires 
and therapy session notes.

### Key Elements

- **Activity:** `ManualDetectionGarciaP00010`  
- **Input Data:**  
  - `PatientQuestionnaire` – PHQ-9 self-report survey  
  - `TherapySessionNotes` – Clinician notes from first two sessions  
- **Schema Used:** `DSM5_Schema` (DSM-5 categories)  
- **Detected Illness:** `DepressionP00010`  
- **Confidence Level:** 0.82 

## Example 2: Automatic Detection

**File:** `ex2_automatic.ttl`  

This example models **automatic detection of mental illnesses** using different machine learning and AI models on various datasets. 
Each detection activity is linked to its input data, model implementation, generated mental illness set, and evaluation metrics. 


### Detection Activities Overview

| Activity | Input Data | Model Implementation  | Generated Mental Illness Set 
|----------|------------|--------------------|-----------------------------|
| BERT-based depression detection | Social media text | PyTorch BERT | `DepressionSetBert` |
| GPT-4 depression detection | Social media text | OpenRouter GPT-4 | `DepressionSetGPT4` | 
| LSTM-based anxiety detection | EEG signals | PyTorch LSTM  | `AnxietySetLSTM` | 
| Multi-modal transformer detection (anxiety, depression, neurocognitive) | Social media text + wearable sensors | PyTorch Multi-Modal Transformer | `MentalIllnessSetMultiModalTransformer` | 


### Input Data

- **SocialMediaText** text posts from social media platforms  
- **EEGSignals** – EEG recordings for brain activity  
- **WearableSensors** – wearable sensor data for physiological measurements  

All datasets are represented as instances of `mls:Dataset` in the ontology.


### Models and Implementations

- **PyTorch Models**  
  - BERT for text-based depression detection  
  - LSTM for EEG-based anxiety detection
  - OpenRouter GPT-4 for text-based depression detection  
  - Multi-Modal Transformer for combined text + sensor depression and anxiety detection  


Each model is linked to its implementation (`mls:Implementation`) and its software package (`mls:Software`).


### Mental Illness Sets and Mental Illnesses Samlple Confidence Levels

- `DepressionSetBert` → detected depression from data sample `socialmedia_000001` with confidence 0.50 
- `DepressionSetGPT4` → detected depression from data sample `socialmedia_000001` with confidence 0.60  
- `AnxietySetLSTM` → detected anxiety from data sample `socialmedia_000001_wearable_000002
EEGSignals_000004`
' with confidence 0.70
- `MentalIllnessSetMultiModalTransformer` → detected depression, anxiety, and neurocognitive issues from data sample `socialmedia_000001_wearable_000002` with confidence 0.75  



### Evaluation Metrics

All models are evaluated using **predictive accuracy** (`mls:EvaluationMeasure`):

| Model | Accuracy |
|-------|----------|
| BERT | 0.80 |
| GPT-4 | 0.98 |
| LSTM | 0.90 |
| Multi-Modal Transformer | 0.95 |



> **Interact with those files in the Notebook:**
> 
><a href="https://github.com/IDA-FBK/mental-health-ontology/tree/conceptualization-dev/notebook" style="text-decoration: none;">
>  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab">
></a>
