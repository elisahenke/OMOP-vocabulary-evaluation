# OMOP-vocabulary-evaluation

This folder contains the CSV files of the results of the vocabulary evaluation regarding completeness and correctness.

For each evaluation, two CSV files are exported:

**Completeness:**
- `*_available_concepts.csv`: list of all unique codes and their frequency in the source data for a specific vocabulary for which **a _concept_id_** was found in the vocabularies prepared for OMOP CDM
- `*_missing_concepts.csv`: list of all unique codes and their frequency in the source data for a specific vocabulary for which **no _concept_id_** was found in the vocabularies prepared for OMOP CDM

**Correctness:**
- `*_valid_concepts.csv`: list of all unique code-date combinations and their frequency in the source data for a specific vocabulary for which a concept_id could be found in the vocabularies prepared for OMOP CDM and whose **date is within the validity period**
- `*_invalid_concepts.csv`: list of all unique code-date combinations and their frequency in the source data for a specific vocabulary for which a concept_id could be found in the vocabularies prepared for OMOP CDM and whose **date is not within the validity period**
