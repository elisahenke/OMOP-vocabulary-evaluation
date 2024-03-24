# OMOP-vocabulary-evaluation

This repository includes the evaluation of the prepared German claims data vocabularies for OMOP CDM regarding completeness and correctness.

## Preparation ##

### Input ###

Please place the input data in the folder */input/data*. You can navigate to this folder and check the readme file to verify the needed file names. They must comply with the defined requirements.


## Completeness evaluation ##

The aim of the completeness evaluation is to check whether all the codes present in the prepared dataset are present in the prepared vocabularies for OMOP CDM.

For this purpose, the codes extracted from the source dataset are searched in the column `source_code` (source_to_concept_map table) for vocabularies prepared using Usagi or in the column `concept_code` (concept table) for new 2-billion-concepts.

If the result of the search returns a `target_concept_id` or `concept_id`, it can be concluded that the code is available in the prepared vocabulary. Otherwise a corresponding code is missing, which can then only be represented in OMOP CDM by a concept_id = 0 (No matching concept).


## Correctness evaluation ##

The correctness evaluation focuses on checking the correct specification of the validity periods of the prepared codes for OMOP CDM.

During the evaluation, it is checked whether the date associated with the code is within the validity period ([valid_start_date, valid_end_date]).

Codes that receive the status `valid` consequently have a correct indication of the validity period. Codes that receive the status `invalid` lead to a loss of data when harmonizing the source data in OMOP CDM.