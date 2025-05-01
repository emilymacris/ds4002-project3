# Glacier Coverage Classification Project

By _Data Destroyers (Emily Macris - leader, Karan Rawat)_



## Contents of Repository
This repository contains all the work for Project 3 of Prototyping which has the goal of working with image data. Specifcally, the goal of the repository is to answer the question: 
_Can a supervised machine learning classifier detect glacier coverage more accurately than index-threshold methods like NDSI, and how well does it generalize across time and other glacier regions?_<br>

**Hypothesis:**  
A Random Forest classifier trained on labeled satellite imagery will outperform static index thresholds like NDSI in pixel-level classification of glacier vs. non-glacier terrain.

---



## Section 1 -- Software and Platform
- **Platform:** Google Colab (preferred), GitHub
- **Languages & Tools:** Python, Google Earth Engine (GEE) and JavaScript, GeoJSON
- **Python Packages Used:**
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `geopandas`
  - `scikit-learn`
  - `earthengine-api`
- Compatible with both **MacOS** and **Windows**

To reproduce this work in Colab, open `scripts/project_3.ipynb`.
All of these packages would have to be downloaded in order to run the notebooks. Both Windows and Mac were used to complete this project. 

## Section 2 -- Directory Map
ds4002_project1/<br>
&nbsp;&nbsp;&nbsp;&nbsp;├── data/<br>
&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;└── speech_data.parquet<br>
&nbsp;&nbsp;&nbsp;&nbsp;├── output/<br>
&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;└── analysis_output.md<br>
&nbsp;&nbsp;&nbsp;&nbsp;├── scripts/<br>
&nbsp;&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;├── project_3.ipynb<br>
&nbsp;&nbsp;&nbsp;&nbsp;├── LICENSE.md<br>
&nbsp;&nbsp;&nbsp;&nbsp;├── README.md<br>
&nbsp;&nbsp;&nbsp;&nbsp;└── DATA_APPENDIX.pdf<br>



## Section 3 -- Reproducing the Results

1. [Clone the repository](https://github.com/emilymacris/ds4002-project3)
2. Step 2: Download Full Dataset
Due to file size limits, the full dataset is hosted externally.

📥 Download glacier_combined.parquet and nonglacier_combined.parquet from this Google Drive folder: https://drive.google.com/file/d/1m6hsUy_mObymYFy_U55HXeccAEcYxKgA/view?usp=drive_link
3. Update file paths in code
In the Colab notebook, update the file paths to match your own Drive structure.
For example, if you copied the files into:
MyDrive/DS4002_Project/Data/

Then modify the relevant cells to:

import pandas as pd

base_path = '/content/drive/MyDrive/DS4002_Project/Data/'

glacier_df = pd.read_parquet(base_path + 'glacier_combined.parquet')
nonglacier_df = pd.read_parquet(base_path + 'nonglacier_combined.parquet')
MyDrive/DS4002_Project/Data/

Then modify the relevant cells to:

➡ Place them in the /data/ folder of the repository.
4. Access the dataset: 
Access the parquet file by running 
df = pd.read_parquet('/content/drive/MyDrive/DS4002_Project/P3_Emily_Karan/data/glacier_combined.parquet')
This will give you the equivalent data set that we had. 

5. First go to the python notebook EDA.ipynb and run each code box in order. This will produce the data set and EDAs
6. Next, run the python Analysis.ipynb notebook to run the model and produce outputs (Train/test split, Random Forest model training, Evaluation via confusion matrix and classification report)
