# FrenchyShona

This folder contains the notebooks, datasets, model information and results used for the journal paper:

**FrenchyShona: Building and Evaluating a Multilingual Sentiment Lexicon with a Shona Focus**

The final FrenchyShona resource contains 6,620 rows. It was developed from an inherited 6,632-row multilingual resource. After the final audit, 17 rows were quarantined, leaving a clean base of 6,615 rows. Five Shona expressions were then retained and added to the resource.

The Shona experiments use 7,880 build instances, 876 validation instances and 1,224 strict unseen test instances.

Files are organised as follows:

- `Notebooks` — code used for resource construction, multilingual enrichment and Shona evaluation.
- `Datasets` — inherited, intermediate and final FrenchyShona resource files.
- `Models` — configuration, tokenizer and training information for AfroLM, AfroXLMR and AfriBERTa.
- `Results` — evaluation results, statistical tests, runtime information, XAI outputs and figures used in the paper.

The notebooks should be followed in this order:

1. `01_FrenchyShona_V7_4_Construction.ipynb`
2. `02_FrenchyShona_Multilingual_Enrichment.ipynb`
3. `03_FrenchyShona_Shona_Evaluation.ipynb`

ShonaSenti is an external dataset and is not redistributed here. The five Ciluba translations added during multilingual enrichment are provisional

The full trained model archives are not included in this GitHub repository because of their size. Model configurations, training settings, manifests and checksums are included.

The FrenchyShona data and supporting research files are also archived on Zenodo:

https://doi.org/10.5281/zenodo.22674533

The FrenchyShona resource and supporting research data are released under the Creative Commons Attribution 4.0 International licence. The notebooks and code are released under the MIT License. Third-party datasets and pretrained models remain subject to their original licences.
