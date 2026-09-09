# ATR-FTIR Spectroscopy and Machine Learning for Schistosomiasis Detection

## Description

This repository contains the raw ATR-FTIR serum spectral data and the analytical workflow associated with the study:

**ATR-FTIR Spectroscopy Combined with Machine Learning Enables Detection of Schistosomiasis-Associated Biochemical Signatures in Human Serum**

The materials are provided to promote transparency, independent inspection, and reproducibility of the spectral and machine learning analyses reported in the manuscript.

---

## Repository contents

### 1. Raw.Spectra.ods

`Raw.Spectra.ods` contains the raw ATR-FTIR spectral data used in the main analysis.

The spreadsheet contains separate worksheets with:

- **Duplicate spectra:** individual replicate spectra acquired from the serum samples.
- **Mean spectra:** averaged spectra obtained from the corresponding duplicate measurements.

The sample groups are identified as follows:

- 🟨 **Yellow:** Control individuals from a non-endemic area
- 🟦 **Blue:** Control individuals from an endemic area
- 🟩 **Green:** *Schistosoma mansoni*-infected individuals (SCH+)

The inclusion of both endemic-area and non-endemic-area controls allows inspection of the spectral data across the different study populations.

---

### 2. Raw_Spectra_Sup.ods

`Raw_Spectra_Sup.ods` contains the spectral data associated with the supplementary analyses assessing the robustness and site-related performance of the classification approach.

This file includes the data used for:

- **Leave-one-site-out analysis**, in which samples from one study site were excluded from model training and used for evaluation.
- **Within-site analysis**, in which classification performance was evaluated within the respective study sites.

These analyses were performed as supplementary assessments of the generalizability and robustness of the spectral classification approach across study locations.

---

### 3. Orange_Workflow.png

`Orange_Workflow.png` provides a graphical representation of the Orange Data Mining workflow used for spectral preprocessing and machine learning analysis.

The workflow illustrates the principal analytical steps, including:

- Spectral preprocessing
- Spectral transformation
- Selection of spectral regions
- Machine learning classification
- Model evaluation

The analyses were performed using **Orange Data Mining version 3.3.5**.

---

## Main machine learning analysis

Multiple spectral preprocessing strategies and supervised machine learning algorithms were evaluated for classification of serum spectra according to *S. mansoni* infection status.

First-derivative preprocessing combined with a Random Forest classifier showed the best performance in the initial cross-validation analysis.

To further assess the robustness of the selected classifier, a nested cross-validation analysis was subsequently performed using an outer 10-fold stratified cross-validation and an inner 4-fold stratified cross-validation for hyperparameter selection.

---

## Data organization

The spectral datasets provided in this repository are intended to allow independent inspection of the raw spectral measurements and the analytical workflow described in the manuscript.

The main dataset (`Raw.Spectra.ods`) corresponds to the primary analysis, whereas `Raw_Spectra_Sup.xslx` corresponds specifically to the supplementary site-related analyses.

---

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
