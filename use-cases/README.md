# MIAO Use Cases

This directory contains supplementary materials demonstrating practical applications of the Mental Illness Assessment Ontology (MIAO) in mental health research and clinical practice.

## Directory structure

### Data Files

- `usecases.ttl` - Complete RDF dataset with example instantiations of MIAO components including schemas, manual annotations, automatic ML-based detections, and cross-dataset scenarios

### Code

The `code/` directory contains Jupyter notebooks and generated RDF outputs:

- `stress-detection-ml-pipeline-model.ipynb` - Automated generation of MIAO annotations for binary stress detection experiments
- `stress_detection_experiment.ttl` - Generated RDF output from stress detection pipeline
- `depression-detection-ml-pipeline-model.ipynb` - Automated generation of MIAO annotations for depression severity classification
- `depression_severity_experiment.ttl` - Generated RDF output from depression severity pipeline

### SPARQL Queries

The `sparql/` directory contains example queries organized by functionality:

1. `01-schema-queries.sparql` - Exploring mental health classification schemas
2. `02-manual-annotation-queries.sparql` - Clinical assessment and expert annotation workflows
3. `03-automatic-detection-queries.sparql` - ML pipeline analysis and model evaluation
4. `04-cross-dataset-queries.sparql` - Multi-label analysis and cross-corpus interoperability
5. `05-statistical-queries.sparql` - Aggregate statistics and distribution patterns
6. `06-advanced-queries.sparql` - Quality control and validation queries
7. `07-integration-queries.sparql` - Data export and system integration