# DL4H_Team_30 : Reproducing Improving Clinical Outcome Predictions Using Convolution over Medical Entities with Multimodal Learning

This repository contains source code for demoing our attempt at reproducing the paper [Improving Clinical Outcome Predictions Using Convolution over Medical Entities with Multimodal Learning](https://doi.org/10.1016/j.artmed.2021.102112)[1]. The notebook provided takes 3+ days to run on the full dataset. The following was done for demo purposes:

Outside the project notebook:
1. Process all the data
2. Train the models (experiments and ablations) on the full dataset
3. Save all experiement results and pretrained models

Inside the project notebook:
1. Use a subset of the data to demonstrate that the processing steps run with no errors.
2. Run the main models on this subset with a few epochs to demonstrate that model code runs.
3. Load the pretrained main models and processed testing data to use for validation in the results section. (the models are saved in the results folder, but the code to load and test them is commented out as it needs the processed testing data which takes about 1 day to process, the purpose was to show the results from the full model.)
4. All other experiment and ablation results are loaded, summarized and discussed

The notebook provides had been set up to run both locally and in Google Colab through mounting notebook to Google Drive.

## Requirements

### Software

Python version: 3.10.12

To install packages: 
```setup
pip install -r requirements.txt
```
Note: this is already done in the provided notebook.

CPU RAM: 13GB

### Datasets

The code uses both MIMIC-III and MIMIC-Extract data.

####  MIMIC-III
To obtain access to the dataset:

1. Navigate to the MIMIC-III [2] PhysioNet page: https://physionet.org/content/mimiciii/1.4/
2. Navigate to the "Files" section at the bottom of the page.
3. Follow the instructions provided
4. After getting access, repeat steps 1 and 2. All files should now be accessible for download.
5. Download `ADMISSIONS.csv.gz`, `ICUSTAYS.csv.gz` and `NOTEEVENTS.csv.gz`.
6. Unzip each file

####  MIMIC-Extract
To obtain access to the dataset:

Access and download the pre-processed output from Google Cloud Platform.
1. Get access to MIMIC-III as outlined above
2. Link your UIUC email account to your PhysioNet profile https://mimic.mit.edu/docs/gettingstarted/cloud/link/.
2. Request access to the cloud resource for MIMIC-III as outlined in this link: https://mimic.mit.edu/docs/gettingstarted/cloud/request/.
3. Click the access link to the Google Cloud Platform storage bucket sent via email.
4. Navigated to the GitHub page MIMIC-Extract [3] https://github.com/MLforHealth/MIMIC_Extract.
5. Navigated to the “Pre-processed Output” section and clicked the link provided for Google Cloud Platform (referred to as gcp).
6. Downloaded the data `all_hourly_data.zip`.
7. Unzip each file

NOTE: Data access instructions are also contained in the notebook under the Data sub-section under Methodology.

## Usage

1. Clone the code to local.   
```
https://github.com/598team30/DL4H_Team_30.git
cd Team30ConvolutionMedicalNer
```
2. a. If using google colab: Upload folder to your Colab Notebooks folder (/My Drive/Colab Notebooks), be sure to keep the folder name "DL4H Team 30 Project".

   b. If running locally, make sure you have at least 13GB RAM otherwise this will not run. This notebook also installs required packages and their versions under environments > install packages. You may want to run this in a virtual environment.
   
3. Upload/copy the `ADMISSIONS.csv`, `NOTEEVENTS.csv`, `ICUSTAYS.csv` files into the data folder.
   
4. Upload/copy `all_hourly_data.h5` to the `data` folder.

5. Copy everything in the `embeddings` folder from https://drive.google.com/drive/folders/1IfqKghs9ztuYZfVYV_mHXAvdZ6q-J2JU to your projects `embeddings` folder.
 
6. Open the `DL4H_Team_30.ipynb` notebook from your `DL4H Team 30 Project` folder and run all (if using google colab, a popup will appear which needs your attention to give permission to mount the notebook to your drive).

## References

[1] Bardak, B., & Tan, M. (2021). Improving clinical outcome predictions using convolution over medical entities with multimodal learning. Artificial intelligence in medicine, 117, 102112. https://doi.org/10.1016/j.artmed.2021.102112 
GitHub link: https://github.com/tanlab/ConvolutionMedicalNer

[2] Johnson, A., Pollard, T., Shen, L. et al. MIMIC-III, a freely accessible critical care database. Sci Data 3, 160035 (2016). https://doi.org/10.1038/sdata.2016.35

[3] Shirly Wang, Matthew B. A. McDermott, Geeticka Chauhan, Michael C. Hughes, Tristan Naumann, and Marzyeh Ghassemi. MIMIC-Extract: A Data Extraction, Preprocessing, and Representation Pipeline for MIMIC-III. arXiv:1907.08322. https://arxiv.org/pdf/1907.08322.pdf

