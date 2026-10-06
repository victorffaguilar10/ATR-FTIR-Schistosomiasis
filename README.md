# ATR-FTIR Schistosomiasis: Orange Workflow

This repository contains the Orange Data Mining workflow and the data files used for the exploratory analysis and machine-learning classification of schistosomiasis-associated ATR-FTIR serum spectra.

## 1. Requirements

Install [Orange Data Mining](https://orangedatamining.com).

The workflow uses widgets that are not included in the base Orange installation. After installing the software, go to **Options > Add-ons**, select the two add-ons below, click **OK**, and restart Orange:

* **Spectroscopy, version 0.9.2.** Provides the `Preprocess Spectra` and `Spectra` widgets and other spectral preprocessing widgets, including MNF and PCA denoising.
* **Explain, version 0.6.11.** Provides the `Explain Model` widget.

Without these add-ons, the workflow may open with broken or unavailable widgets.

## 2. Files in this repository

* `Workflow.ows`: Orange workflow for exploratory analysis, spectral preprocessing, machine learning, model evaluation, model interpretation, and locality-effect analysis.
* `General_and_truncated_spectra.xlsx`: spectra covering the complete spectral range (`General spectra` worksheet) and the selected spectral regions (`Truncated spectra` worksheet).
* `Localidade_truncado.xlsx`: spectra organized according to the geographical origin of the samples, used for the locality-effect analysis and independent validation across study sites.

## 3. Data format

The `.xlsx` files contain the mean spectrum of each sample, obtained by averaging the two technical replicates acquired for each sample. No normalization or additional spectral preprocessing was applied to these exported spectra; all subsequent spectral preprocessing is performed within the Orange workflow.

Each row of the spreadsheet corresponds to one sample. The `class` column is the target variable and contains the values `control` and `positive`; in Orange, this column must be correctly recognized as the target variable. The remaining columns contain the spectral values at each wavenumber (cm⁻¹).

## 4. Opening the workflow

Install Orange and the required add-ons described in Section 1. Download `Workflow.ows` and the `.xlsx` files from this repository, and open `Workflow.ows` in Orange.

The `File` widgets may appear with a red X. This is expected because the workflow stores the file paths from the original computer on which it was created. Double-click each `File` widget and select the corresponding file from your computer.

## 5. Main analyses

### 5.1 Exploratory analysis

In the first `File` widget, load `General_and_truncated_spectra.xlsx` and select the `General spectra` worksheet.

For exploratory analysis, principal component analysis (PCA) is performed after rubberband baseline correction and Min-Max normalization. The workflow allows visualization of the resulting PCA scores using `Scatter Plot` and `Data Table`. The spectra can also be visualized using the `Spectra` widget after the appropriate spectral preprocessing and color assignment.

### 5.2 Machine-learning classification

In the `File (1)` widget, load `General_and_truncated_spectra.xlsx` and select the `Truncated spectra` worksheet.

The spectral analysis focuses on the regions 3050–2800 cm⁻¹ and 1800–900 cm⁻¹, corresponding to the lipid and fingerprint regions, respectively.

To reproduce an analysis, connect the desired preprocessing method to the desired machine-learning algorithm. The output of the algorithm is then connected to `Test and Score` for model evaluation and to `Explain Model` for model interpretation.

Model performance was evaluated using stratified 10-fold cross-validation, preserving the proportion of positive and control samples in each fold.

The results for each combination of preprocessing method and algorithm are described in the associated publication. To verify the analysis, compare the output of `Test and Score` with the published results.

## 6. Locality-effect analysis

This additional analysis was performed at the reviewers' request to investigate whether classifier performance could be influenced by differences associated with the geographical origin of the samples.

The analysis is identified in the workflow by the sections **`Localidade`** and **`File 3`**. Load `Localidade_truncado.xlsx` in both sections.

### External validation

In the first flow, starting from `Localidade`, the Random Forest classifier is trained exclusively using samples from **Januária, Minas Gerais**, which is the only study site containing both classes (positive and control).

The samples from Januária are selected using the `Site is Januária` step, processed using the first derivative, and then classified using Random Forest.

The independent test set consists of samples from **Jaboatão dos Guararapes, Pernambuco**, and **Belo Horizonte, Minas Gerais**. These samples are selected using the `Site is not Januária` step and are entered into `Test and Score (1)` as test data, with the evaluation mode set to **Test on test data**.

Thus, samples from Jaboatão dos Guararapes and Belo Horizonte are not used during model training and constitute an independent test set.

### Internal evaluation within Januária

In the second flow, starting from `File 3`, only samples from Januária are selected using the `Site is Januária (1)` step. These samples undergo the same first-derivative preprocessing and Random Forest classification and are evaluated using `Test and Score (2)`.

In both locality-based analyses, the preprocessing and classification method are **first derivative + Random Forest**, consistent with the original analysis.

## 7. Step-by-step reproduction

1. Install Orange Data Mining.
2. Install the **Spectroscopy (0.9.2)** and **Explain (0.6.11)** add-ons.
3. Download `Workflow.ows` and the `.xlsx` files from this repository.
4. Open `Workflow.ows` in Orange.
5. In each `File` section, select the corresponding file and worksheet as described in Sections 5 and 6.
6. For the main machine-learning analysis, connect the desired preprocessing method to the desired algorithm.
7. Connect the model to `Test and Score` for evaluation and, when applicable, to `Explain Model` for model interpretation.
8. For the locality-effect analysis, load `Localidade_truncado.xlsx` in the **`Localidade`** and **`File 3`** sections and follow the corresponding workflow.
9. Compare the resulting performance metrics with those reported in the associated publication.

## Citation

If these data are used, reanalyzed, or incorporated into other studies, please cite the original publication:

**ATR-FTIR Spectroscopy Combined with Machine Learning Enables Detection of Schistosomiasis-Associated Biochemical Signatures in Human Serum.**

Please also acknowledge this repository when appropriate.

## License

The materials in this repository are made available under the **Creative Commons Zero v1.0 Universal (CC0 1.0)** license. The authors waive, to the extent permitted by law, copyright and related rights to the materials deposited in this repository. Although attribution is not a legal requirement under CC0, users are strongly encouraged to cite the original publication.

## Contact

For questions regarding the data or the analytical workflow, please contact the corresponding author of the associated publication.

