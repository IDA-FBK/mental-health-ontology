# Mental Illness Detection Ontology Requirements & Competency Questions

This document provides the requirements and competency questions (CQs) guiding the design of the MIAO ontology.  
The ontology is intended to unify representations of human and AI driven mental illness detection, ensuring semantic interoperability and enabling explainable analysis of detection results.

---

## ⚙ Ontology Requirements

The requirements are grouped as **Functional Requirements (FR)** and **Non-Functional Requirements (NFR)**.

### Functional Requirements (FR)

| ID | Requirement |
|----|------------|
| **FR1** | The ontology shall represent both human-driven and AI-driven mental illness detection processes. |
| **FR2** | The ontology shall link detection processes to their input data sources. |
| **FR3** | The ontology shall support integration of multiple mental illness schemas (e.g., DSM-5, SNOMED CT) and link detected illnesses to their defined categories. |
| **FR4** | The ontology shall represent detection results and include the confidence associated with each detection. |

---

### Non-Functional Requirements (NFR)

| ID | Requirement |
|----|------------|
| **NFR1** | The ontology shall be flexible and extensible, allowing addition of new detection methods, disorders, or mental health models without major restructuring. |
| **NFR2** | The ontology shall support traceability, enabling tracking of detection results back to their original data sources. |
| **NFR3** | The ontology shall comply with Semantic Web standards to maximize compatibility with existing tooling and knowledge graphs. |
| **NFR4** | The ontology shall include clear documentation and usage guidelines to ensure adoption by both AI researchers and mental health domain experts. |

---

## ❓ Competency Questions (CQs)

Competency Questions define what users should be able to query using the ontology.

| Competency Question (CQ) | Supported Requirements |
|---|:---:|
| Which data sources do human experts use to detect depression? | FR1, FR2 |
| Which mental illness schemas do experts reference during manual analysis? | FR1, FR3 |
| What confidence scores do human experts assign to their manual diagnoses? | FR1, FR4 |
| Which AI models can be used to detect depression? | FR1 |
| Which AI models have been applied to detect anxiety from EEG signals? | FR1, FR2 |
| Which AI models combine multiple data sources (e.g., text + sensors)? | FR1, FR2 |
| Which AI models can detect multiple disorders simultaneously? | FR1, FR3 |
| Are there AI models that can detect both depression and anxiety from the same data source? | FR1, FR2, FR3 |
| Which model achieved the highest accuracy in predicting depression? | FR1, FR4 |

---

## 🧠 How These Requirements Shape the Ontology

The requirements ensure that the ontology:

- Covers both clinical and automated AI detection workflows  
- Connects mental illness detection with datasets, models, schemas, and confidence values 
- Enables performance comparison and traceability of detection results  
- Can evolve as new diagnostic methods and machine learning models emerge

---

## 🔍 Implementation and Usage

These requirements and CQs are operationalized through example RDF/Turtle datasets:

| Example File | Description |
|--------------|------------|
| `ex1_manual.ttl` | Manual diagnosis by a clinical expert using DSM-5 and patient-provided data |
| `ex2_automatic.ttl` | Automatic detection using ML/AI models (BERT, GPT-4, LSTM, Multi-Modal Transformer) |

SPARQL queries that answer the competency questions available at [Google Coolab Notebook](https://github.com/IDA-FBK/mental-health-ontology/tree/conceptualization-dev/notebook)


