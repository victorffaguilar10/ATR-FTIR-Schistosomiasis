# ATR-FTIR Spectroscopy and Machine Learning for Schistosomiasis Detection

## Description

This repository contains the raw ATR-FTIR serum spectral data and a graphical representation of the analytical workflow used for spectral preprocessing and machine learning analysis in the study:

*ATR-FTIR Spectroscopy Combined with Machine Learning Enables Detection of Schistosomiasis-Associated Biochemical Signatures in Human Serum*

The materials are provided to facilitate transparency, independent inspection, and reproducibility of the spectral and machine learning analyses reported in the manuscript.

## Repository contents

### 1. Raw spectral data

The raw ATR-FTIR spectral data used in the study are provided as numerical spectral values for the analyzed serum samples.

The dataset includes spectra from:

- Control individuals
- Schistosoma mansoni-infected (SCH+) individuals

The spectra were acquired in the spectral regions used for the machine learning analyses.

### 2. Orange Data Mining workflow

A graphical representation of the Orange Data Mining workflow used in the analysis is provided.

The workflow illustrates the main analytical steps, including:

- Spectral preprocessing
- Spectral transformation
- Selection of spectral regions
- Machine learning classification
- Model evaluation

The workflow was implemented using Orange Data Mining (version 3.3.5).

## Data processing and machine learning

The study evaluated multiple spectral preprocessing strategies and supervised machine learning algorithms for the classification of serum spectra according to S. mansoni infection status.

The Random Forest classifier combined with first-derivative preprocessing showed the best performance in the initial cross-validation analysis and was subsequently subjected to nested cross-validation for a more stringent assessment of classifier robustness.

## Citation

If these data are used, reanalyzed, or incorporated into other studies, users are requested to cite the original publication:

*ATR-FTIR Spectroscopy Combined with Machine Learning Enables Detection of Schistosomiasis-Associated Biochemical Signatures in Human Serum.*

Please also acknowledge this repository when appropriate.

## License

The materials in this repository are made available under the *Creative Commons Zero v1.0 Universal (CC0 1.0)* license.

The authors waive, to the extent permitted by law, copyright and related rights to the materials deposited in this repository.

Although attribution is not a legal requirement under CC0, users are strongly encouraged to cite the original publication when using or reanalyzing these data.

## Contact

For questions regarding the dataset or the analytical workflow, please contact the corresponding author of the associated publication.
