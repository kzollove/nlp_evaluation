# nlp_evaluation
Towards a reporting standard for NLP-assisted observational research

This work is an example implementation of Daniel G Smith's proposed reporting standard, in which he notes:
>We therefore encourage the use of reporting standards, heavily influenced by the work of the
Hongfang lab and their collaborators (Fu et al., 2023; Wang et al., 2022) in an effort to support
FAIR and RITE principals in methods promoting evidence generation using datasets containing
NLP.

## Implementation: OHDSI NLP PoC Brain Cancer Study
PoC study details: https://github.com/OHDSI/NLPTools/wiki/NOTE-NLP-Proposal-POC

### Methodological Details
#### Describing evaluation environment, data source, and cohort
1. Detailed Cohort Definition (Atlas)
```{
  "ConceptSets": [
    {
      "id": 0,
      "name": "Simple brain",
      "expression": {
        "items": []
      }
    },
    {
      "id": 1,
      "name": "Simple brainer",
      "expression": {
        "items": [
          {
            "concept": {
              "CONCEPT_ID": 443588,
              "CONCEPT_NAME": "Malignant neoplasm of brain",
              "STANDARD_CONCEPT": "S",
              "STANDARD_CONCEPT_CAPTION": "Standard",
              "INVALID_REASON": "V",
              "INVALID_REASON_CAPTION": "Valid",
              "CONCEPT_CODE": "428061005",
              "DOMAIN_ID": "Condition",
              "VOCABULARY_ID": "SNOMED",
              "CONCEPT_CLASS_ID": "Clinical Finding"
            },
            "includeDescendants": true,
            "includeMapped": true
          }
        ]
      }
    }
  ],
  "PrimaryCriteria": {
    "CriteriaList": [
      {
        "ConditionOccurrence": {
          "CodesetId": 1,
          "OccurrenceStartDate": {
            "Value": "2010-01-01",
            "Extent": "2020-01-01",
            "Op": "bt"
          }
        }
      }
    ],
    "ObservationWindow": {
      "PriorDays": 0,
      "PostDays": 0
    },
    "PrimaryCriteriaLimit": {
      "Type": "First"
    }
  },
  "QualifiedLimit": {
    "Type": "First"
  },
  "ExpressionLimit": {
    "Type": "First"
  },
  "InclusionRules": [],
  "CensoringCriteria": [],
  "CollapseSettings": {
    "CollapseType": "ERA",
    "EraPad": 0
  },
  "CensorWindow": {},
  "cdmVersionRange": ">=5.0.0"
}
```
2. Methods for creating cohort
- Generation in Atlas on the Tufts Medical Center TRDW "TMC_RED" database

3. Evaluation of Individuals in Cohort
- NA (CohortDiagnostics results?)
4. Validity of Cohort screen methods reported
- NA
#### Corpus annotation evaluation
#### NLP Algorithm and Framework Definition
1. Definitions of context
2. Synonym normalization (e.g., UMLS, ICD‐O‐3, NAACCR, CAP)
3. Definitions of rules, patterns, and logic
4. References and code access to any published part of pipeline
5. generic text processors and statistical models
6. Primary NLP model utilized (see definition of note_nlp.nlp_system guidance)
#### NLP Evaluation and Refinement
1. Measurement level (e.g., concept, document, patient)
2. Duration of NLP evaluation
3. Refinement procedures based on error analysis
