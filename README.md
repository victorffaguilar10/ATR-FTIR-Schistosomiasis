# ATR-FTIR Schistosomiasis — Orange Workflow

This repository contains the Orange workflow and data files used for the exploratory analysis and machine-learning classification of schistosomiasis-associated ATR-FTIR serum spectra.

## 1. Software

First, download and install **Orange Data Mining**.

After installation, download the workflow from this repository:

Workflow.ows

Open the `Workflow.ows` file in Orange to visualize the complete workflow used in the analysis.

---

## 2. Exploratory spectral analysis

The first step of the workflow consists of the exploratory analysis of the ATR-FTIR spectra.

In the first **File** widget, upload:

`General_and_truncated_spectra.xlsx`

This file contains two datasets:

* **General spectra:** the complete spectral range used for exploratory analysis.
* **Truncated spectra:** spectra restricted to the spectral regions of interest used in subsequent analyses.

For the initial exploratory analysis, select the **General spectra** dataset.

---

## 3. Machine-learning analysis

For the machine-learning analysis, the `General_and_truncated_spectra.xlsx` file is also used, with the **truncated spectra** corresponding to the selected spectral regions of interest.

Because the workflow includes neural-network-based analyses, the different preprocessing methods are connected to the different machine-learning algorithms. The resulting models are then connected to:

* **Test & Score**, for model evaluation;
* **Explain Model**, for model interpretation.

The workflow therefore allows the user to reproduce the preprocessing, classification, model evaluation, and model interpretation steps used in the analysis. For this step, add the truncated data to the "File 1" section.

---

## 4. Locality-effect analysis

As suggested by the reviewers, additional analyses were performed to investigate the potential effect of sample locality on model performance.

The locality-based analysis is identified in the workflow by the **“Loacalidade”** section and the **“File 3”** widget. **This is where the dataset containing the information related to sample locality should be uploaded.**

The corresponding spectral data are provided in:

"Localidade_truncado.xlsx"

This file contains the spectra organized  according to the geographical origin of the samples, allowing the potential effect of locality to be evaluated.

## 5. Files in this repository

| File                            | Description                                                                                                                                           |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Workflow.ows`                  | Orange workflow used for exploratory analysis, preprocessing, machine learning, model evaluation, model interpretation, and locality-effect analysis. |
| `General_and_truncated_spectra.xlsx` | Dataset containing the general spectral range and the truncated spectral regions used in the analyses.                                                |
| `Localidade_truncado.xlsx`             | Spectral data used for the locality-effect analysis and independent validation across study sites.                                                    |

## 6. Reproducibility

To reproduce the Orange-based analyses:

1. Install **Orange Data Mining**.
2. Download `Workflow.ows`.
3. Download the required dataset files from this repository.
4. Open `Workflow.ows` in Orange.
5. In each **File** widget, select the corresponding dataset.
6. For the main analyses, use `General_and_truncated_spectra.xlsx` as indicated in the workflow.
7. To analyze the location effect, download the `Localidade_truncado.xlsx` file and add it to the **“Localidade”** and **“File 3”** collections in the workflow to perform the analyses..
8. Follow the connections between preprocessing, machine-learning, evaluation, and model-interpretation 

## Citation

If these data are used, reanalyzed, or incorporated into other studies, users are requested to cite the original publication:

**ATR-FTIR Spectroscopy Combined with Machine Learning Enables Detection of Schistosomiasis-Associated Biochemical Signatures in Human Serum.**

Please also acknowledge this repository when appropriate.

---

## License

The materials in this repository are made available under the **Creative Commons Zero v1.0 Universal (CC0 1.0)** license.

The authors waive, to the extent permitted by law, copyright and related rights to the materials deposited in this repository.

Although attribution is not a legal requirement under CC0, users are strongly encouraged to cite the original publication when using or reanalyzing these data.

---

## Contact

For questions regarding the dataset or the analytical workflow, please contact the corresponding author of the associated publication.
