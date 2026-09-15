# FrenchyShona

This folder contains the notebooks, datasets, model information, experimental results and reproducibility artefacts used for the journal paper:

**FrenchyShona: Building and Evaluating a Multilingual Sentiment Lexicon with a Shona Focus**

## Resource Overview

FrenchyShona builds on the FrenchyLuba multilingual sentiment resource line.

Original FrenchyLuba contains 6,963 rows. The immediate starting point for this study was a separately supplied 6,632-row multilingual working resource, referred to in the paper as Extended FrenchyLuba.

The Shona layer was constructed in the present study by comparing the existing Shona field with a Google Translate Shona rendering of the English field and consolidating the results into `expanded_shona` and `expanded_shona_class`.

A subsequent resource-quality audit quarantined 17 structurally or sentiment-score-invalid rows, leaving a clean FrenchyShona experimental base of 6,615 rows.

Five Shona expressions were retained through the build-only candidate procedure and added after multilingual enrichment, producing the final FrenchyShona resource of **6,620 rows**.

## Shona Evaluation Boundary

The Shona experiments use three separate partitions:

- **Build:** 7,880 instances
- **Validation:** 876 instances
- **Strict unseen test:** 1,224 instances

The strict unseen test was constructed after auditing the released ShonaSenti data for repeated normalised text identities, training-test overlap and conflicting labels.

Candidate discovery, corpus association analysis and model fitting use the build partition. Threshold, checkpoint and hybrid selection use the validation partition. The strict unseen test is reserved for final evaluation and post hoc analysis.

## Folder Structure

Files are organised as follows:

- `Notebooks` — executable notebooks for resource construction, multilingual enrichment, strict Shona evaluation and the grounding audit.
- `Datasets` — inherited, intermediate and final FrenchyShona resource files together with construction and review records.
- `Models` — model configurations, tokenizer files, training settings, manifests and checksums for AfroLM, AfroXLMR and AfriBERTa.
- `Results` — statistical results, evaluation outputs, bootstrap analyses, runtime information, XAI outputs and figures used in the paper.
- `Results/Grounding_Audit` — files supporting the grounding-based hallucination rate, model-reviewer disagreement analysis, language-screen compliance check and Ciluba source-reference audit.

## Notebook Order

The notebooks should be followed in this order:

1. `01_FrenchyShona_V7_4_Construction.ipynb`
2. `02_FrenchyShona_Multilingual_Enrichment.ipynb`
3. `03_FrenchyShona_Shona_Evaluation.ipynb`
4. `04_FrenchyShona_Grounding_Audit.ipynb`

### Notebook 1: FrenchyShona Construction

Contains the main resource-construction and source-data workflow, including:

- ShonaSenti data audit and strict evaluation boundary;
- Shona-layer construction;
- final resource-quality audit;
- candidate discovery and contextual recovery;
- PMI, Fisher exact testing, Benjamini-Hochberg correction, bootstrap and Wilson screening;
- structured native-speaker review;
- final retention decisions; and
- standalone and classical source evaluation components.

### Notebook 2: Multilingual Enrichment

Contains the multilingual completion of the five retained Shona additions, including:

- English and multilingual equivalents;
- direct Shona-to-target and English-pivot translation checks;
- provisional Ciluba completion;
- protected-field checks; and
- creation of the final 6,620-row releases.

### Notebook 3: Strict Shona Evaluation

Contains the final contextual and hybrid evaluation using:

- AfroLM;
- AfroXLMR;
- AfriBERTa;
- probability ensembles;
- coverage-aware FrenchyShona hybrids;
- paired bootstrap analysis;
- match-conditioned analysis;
- LIME diagnostics;
- attention diagnostics; and
- runtime and environment records.

### Notebook 4: Grounding Audit

Contains the post hoc audit of the frozen model-assisted construction records, including:

- grounding-based hallucination rate (GHR);
- model-reviewer disagreement rate (MRDR);
- Wilson confidence intervals; and
- generation of the grounding and disagreement figure reported in the paper.

Supporting files are stored under `Results/Grounding_Audit`.

## Grounding Audit

The final paper reports a post hoc grounding audit of model-assisted lexical stages.

The audit found:

- Shona contextual recovery: **0 ungrounded outputs out of 32 audited**
- Ciluba completion: **0 ungrounded outputs out of 5 audited**
- Combined: **0 ungrounded outputs out of 37 audited**

All 25 source-row references associated with the five provisional Ciluba completions were resolved against the preserved source resources.

The observed combined GHR of 0% should not be interpreted as proof that the underlying hallucination probability is zero. The paper therefore reports Wilson confidence intervals.

The native-speaker review and the separate model-assisted contextual assessment are compared using the model-reviewer disagreement rate (MRDR). MRDR is reported separately from GHR and is not treated as a hallucination rate.

## External Data

ShonaSenti is an external dataset and is **not redistributed** in this repository.

The five Ciluba translations added during multilingual enrichment are **provisional and were not independently validated by native speakers**.

## Model Files

The full trained model weight archives are not included in this GitHub repository because of their size.

The repository includes the model configurations, tokenizer files, training settings, manifests, checksums, training histories and experimental records required to document the completed runs.

## Reproducibility

The repository preserves the main artefacts supporting the reported journal results, including:

- resource construction records;
- final FrenchyShona releases;
- candidate-screening outputs;
- review records;
- multilingual enrichment records;
- strict Shona evaluation outputs;
- paired bootstrap results;
- XAI outputs;
- grounding-audit records;
- figures;
- runtime information; and
- reproducibility manifests and checksums.

## Zenodo Archive

The FrenchyShona data and supporting research files are also archived on Zenodo:

https://doi.org/10.5281/zenodo.22674533

## Licence

The FrenchyShona resource and supporting research data are released under the **Creative Commons Attribution 4.0 International licence (CC BY 4.0)**.

The notebooks and original code in this repository are released under the **MIT License**.

Third-party datasets, pretrained models and externally sourced resources remain subject to their original licences.
