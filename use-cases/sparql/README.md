# MIAO SPARQL Query Examples

This directory contains a comprehensive collection of SPARQL queries demonstrating the capabilities of the Mental Illness Assessment Ontology (MIAO) for mental health research and clinical practice applications.

## Overview

These queries are provided as supplementary material to the research article introducing MIAO. They illustrate practical applications across three main scenarios: manual expert annotation of depression severity, automatic machine learning-based detection from text and multimodal signals, and cross-dataset interoperability for multi-label analysis.

## Repository structure

The queries are organized into seven thematic files:

- `01-schema-queries.sparql` - Queries for exploring mental health classification schemas and diagnostic frameworks
- `02-manual-annotation-queries.sparql` - Queries for clinical assessment and expert annotation workflows
- `03-automatic-detection-queries.sparql` - Queries for machine learning pipeline analysis and model performance evaluation
- `04-cross-dataset-queries.sparql` - Queries for multi-label analysis and cross-corpus interoperability
- `05-statistical-queries.sparql` - Aggregate queries for statistical analysis and distribution patterns
- `06-advanced-queries.sparql` - Complex analytical queries for quality control and validation
- `07-integration-queries.sparql` - Queries for data export and system integration

## Prerequisites

To execute these queries, you will need:

1. A SPARQL query engine (e.g., Apache Jena ARQ, RDFLib for Python, or Stardog)
2. The MIAO ontology and example data loaded into a triple store
3. Basic familiarity with SPARQL 1.1 query language

## Running the queries

### Using Apache Jena ARQ

```

sparql --data=../data/usecases.ttl --query=01-schema-queries.sparql

```

### Using Python with RDFLib

```

from rdflib import Graph

g = Graph()
g.parse("../data/usecases.ttl", format="turtle")
g.parse("../ontology/miao.ttl", format="turtle")

with open("01-schema-queries.sparql", "r") as f:
results = g.query(f.read())

for row in results:
print(row)

```

### Using SPARQL Endpoint

If you have deployed MIAO data to a SPARQL endpoint, you can execute queries via HTTP:

```

curl -X POST http://your-endpoint/sparql \
--data-urlencode query@01-schema-queries.sparql \
-H "Accept: application/sparql-results+json"

```

## Query Categories

### 1. Schema and category queries

Queries for inspecting and navigating mental health classification frameworks such as DSM-5, ICD-11, and research-specific taxonomies. These queries enable exploration of diagnostic categories, severity scales, and schema metadata.

**Example use cases:**
- List all available mental health schemas
- Retrieve detailed information about specific diagnostic categories
- Identify ordinal severity scales for computational research
- Calculate schema complexity statistics

### 2. Manual annotation queries

Queries for analyzing clinical assessments and expert annotations. These support audit trails, provenance tracking, and validation of manual diagnostic processes.

**Example use cases:**
- Retrieve all diagnoses by a specific clinician
- Identify patients with comorbid conditions
- Track assessment instruments used in clinical evaluations
- Filter high-confidence manual diagnoses

### 3. Automatic detection queries

Queries for examining machine learning pipelines, comparing model architectures, and evaluating prediction performance. These enable systematic analysis of automatic mental health detection systems.

**Example use cases:**
- Compare accuracy across different ML models
- Retrieve hyperparameters for reproducibility
- Analyze predictions for specific samples
- Identify multimodal detection results
- Filter predictions by confidence thresholds

### 4. Cross-dataset interoperability queries

Queries demonstrating MIAO's capability to integrate annotations from multiple datasets with different labeling schemes. These support multi-label analysis and comorbidity pattern discovery.

**Example use cases:**
- Find samples annotated in multiple corpora
- Query co-occurring stress and depression labels
- Compare manual versus automatic annotations
- Track provenance across different detection methods

### 5. Statistical and aggregate queries

Queries for generating statistical summaries, distributions, and aggregate metrics across mental health annotations.

**Example use cases:**
- Calculate distribution of severity levels
- Compare average confidence by detection method
- Identify most frequently detected categories
- Analyze comorbidity patterns
- Generate model performance rankings

### 6. Advanced analytical queries

Complex queries for quality control, validation, and research insights including multimodal fusion analysis and inter-annotator agreement.

**Example use cases:**
- Quantify benefits of multimodal fusion
- Identify low-confidence predictions requiring review
- Map equivalent categories across different schemas
- Calculate inter-annotator agreement metrics
- Select high-quality data for model training

### 7. Integration and federated queries

Queries designed for system integration, data export, and federated analysis scenarios.

**Example use cases:**
- Export predictions in standardized formats
- Generate training datasets with labels
- Identify samples for active learning
- Construct queries for external system integration

## Data Requirements

These queries assume the presence of the following RDF datasets:

1. MIAO ontology (``miao.ttl``)
2. Example use case data (``usecases.ttl``)
3. Mental health classification schemas (DSM-5, research taxonomies)

The complete datasets are available in the repository's data directory.

## Namespace Prefixes

All queries use the following namespace prefixes:

```

PREFIX ex: [https://w3id.org/miao/ex\#](https://w3id.org/miao/ex#)
PREFIX miao: [https://w3id.org/miao\#](https://w3id.org/miao#)
PREFIX prov: [http://www.w3.org/ns/prov\#](http://www.w3.org/ns/prov#)
PREFIX dcterms: [http://purl.org/dc/terms/](http://purl.org/dc/terms/)
PREFIX mls: [http://www.w3.org/ns/mls\#](http://www.w3.org/ns/mls#)
PREFIX rdfs: [http://www.w3.org/2000/01/rdf-schema\#](http://www.w3.org/2000/01/rdf-schema#)
PREFIX xsd: [http://www.w3.org/2001/XMLSchema\#](http://www.w3.org/2001/XMLSchema#)

```



## License

These queries are released under the same license as the MIAO ontology. See the main repository LICENSE file for details.