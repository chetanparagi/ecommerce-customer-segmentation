# E-Commerce Customer Segmentation and Prediction

A BIA capstone notebook that transforms transaction history into customer-level RFM features, compares clustering approaches, assigns business-facing segment names, and trains classifiers to predict a segment from RFM data.

## Workflow

1. Load transaction records and clean cancellations, missing customer IDs, duplicates, and invalid quantities or prices.
2. Aggregate Recency, Frequency, and Monetary features for each customer.
3. Compare K-Means, agglomerative clustering, DBSCAN, and Gaussian mixture clustering.
4. Profile and label the resulting groups (for example, Champions, Promising, At-Risk, and Hibernating).
5. Compare classifiers and serialize the selected clustering/classification artifacts.
6. Explore segment-level business recommendations.

## Repository contents

- `ECommerce_Segmentation_and_Prediction.ipynb` — analysis, model comparison, and prediction workflow
- `best_clustering_model.pkl`, `best_classifier.pkl` — fitted artifacts from the submitted analysis
- `ECommerce_Segmentation_Capstone_Presentation.pptx` — capstone presentation

## Setup

Python 3.10 or newer is recommended. Create an environment and install the dependencies:

```bash
python -m venv .venv
# Windows PowerShell: .venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter lab
```

Open the notebook and run cells in order. The notebook looks for `data.csv` in its working directory. The original transaction dataset is not included; obtain it from its source, check its terms, and place it beside the notebook as `data.csv`. If absent, the notebook generates synthetic sample transactions for a demonstration. Results from synthetic data are illustrative and are not comparable with the submitted model results.

## Metrics

The submitted project summary reports a silhouette score of **0.498** for clustering and **98.6% accuracy** for the selected classifier. Treat these as results reported for the submitted data/model run; reproduce them only with the matching dataset, preprocessing, and library versions. The classifier predicts labels derived from clustering, so high accuracy measures agreement with those generated labels rather than independent ground-truth customer value.

## Reproducibility notes

The included pickle files are Python-version and dependency sensitive. Load pickle files only from a trusted source. The notebook contains the main workflow; the pickles are saved outputs and are not required to rerun the analysis.

## License

No license is specified. Add a license only after deciding how you want others to use this work. Dataset rights remain with the data provider.