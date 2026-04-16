# hybrid-igl1

Leakage-aware hybrid feature selection pipeline for intrusion detection on the UNSW-NB15 dataset using Information Gain and L1-regularized LinearSVC.

## Repository Metadata

- **Repository name:** hybrid-igl1
- **Project lead / maintainer:** Andri Saputra
- **Authors:** Andri Saputra, Kalamullah Ramli, Anto Satriyo Nugroho, I Gde Dharma Nugraha, Bernardi Pranggono
- **Repository metadata update:** 2026-04-15
- **Status:** Research code accompanying a manuscript under journal review

## Related Manuscript

**Title:**  
*A Hybrid IGL1 Feature Selection Method for Intrusion Detection on UNSW-NB15 Using Multiple Machine Learning Models*

This repository accompanies the manuscript above and provides the main notebook, selected-feature outputs, supporting result files, and figure assets used in the reported study.

## Project Description

This repository implements a **leakage-aware intrusion detection pipeline** on the **UNSW-NB15** dataset using a two-stage hybrid feature selection framework:

1. **Information Gain (IG)** for initial relevance filtering  
2. **L1-regularized LinearSVC** for sparse ranking and top-k feature retention

The final experimental workflow evaluates the selected feature subset using:
- Random Forest
- Multi-Layer Perceptron (MLP)
- Gradient Boosting

with:
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)

as supporting baselines.

## Main Contribution of the Code

This repository provides:

- a **reproducible leakage-aware pipeline**
- implementation of the **IGL1** two-stage feature selection framework
- the **final reported working configuration** used in the manuscript
- selected features, feature-importance outputs, and result summaries
- figure assets and editable workflow diagrams

## Repository Contents

Important files in this repository include:

- `UNSW_NB15_ML_S3_FS_IGL1_FINAL.ipynb`  
  Main experimental notebook

- `final_selected_features.csv`  
  Final retained feature subset

- `final_feature_importance_ig_l1.csv`  
  Feature-importance outputs from the IG and L1 stages

- `validation_results.csv`  
  Validation-stage model results

- `test_results.csv`  
  Final test-stage results

- `run_summary.json`  
  Run summary and experiment outputs

- `selector_ig_unsw_nb15.pkl`  
  Saved IG selector object

- `selector_l1_unsw_nb15.pkl`  
  Saved L1 selector object

- `scaler_unsw_nb15.pkl`  
  Saved MinMax scaler

- `label_encoder_unsw_nb15.pkl`  
  Saved label encoder

- `Figure.zip`  
  Final figures used in the manuscript

- `Draw.io.zip`  
  Editable workflow figures

## Experimental Notes

The final reported workflow follows these principles:

- data partitioning is performed **before** learned preprocessing
- all learned transformations are fitted **only on the training split**
- categorical attributes are encoded using a **training-driven binary dominant-category scheme**
- previously unseen categorical values in validation/test data are mapped to **0**
- the final reported run uses a **reduced six-class configuration**
- **no controlled oversampling** is used in the final reported run

## Dataset

This study uses the UNSW-NB15 dataset.

The dataset should be obtained from the official UNSW Research dataset page for UNSW-NB15.

Users are responsible for complying with the original dataset access conditions, redistribution terms, and citation requirements specified by the dataset authors.

## Environment

The experiments were prepared for a Python / Jupyter / Google Colab workflow using standard scientific Python libraries, including scikit-learn, pandas, numpy, and matplotlib.

## How to Run

1. Prepare the UNSW-NB15 dataset in the expected working directory.
2. Open `UNSW_NB15_ML_S3_FS_IGL1_FINAL.ipynb` in Jupyter Notebook or Google Colab.
3. Run the notebook sequentially from preprocessing through evaluation.
4. Export result tables and figures if needed.
5. Use the provided CSV and PKL files to verify the reported feature-selection and evaluation outputs.

## Reproducibility and Scope

This repository is intended to support **reproducibility of the reported final experiment**.

Please note:

- the final 31-feature and 21-feature retention levels correspond to the **final reported working configuration**
- they should not be interpreted as the output of an exhaustive optimization study
- the repository supports the final manuscript workflow and reported outputs, not a broader hyperparameter-search framework

## License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

See the `LICENSE` file for the full license text.

## Citation

If you use this repository, please cite the software repository and the related manuscript.

A machine-readable citation file is provided as `CITATION.cff`.

## Contact

**Andri Saputra**  
Email: `andri.saputra31@ui.ac.id`

For academic correspondence regarding the associated manuscript, please use the contact information provided in the paper.
