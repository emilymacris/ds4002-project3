**Model Evaluation**



We evaluated the performance of our supervised classification model using a combination of confusion matrix analysis, classification reports, and visual exploration of key features (bands and indices). Our primary goal was to classify glacier vs. non-glacier pixels using a Random Forest classifier trained on spectral bands and index data from Landsat 8.

**1. Accuracy and Performance Metrics**


<img width="494" alt="image" src="https://github.com/user-attachments/assets/8ffc7ea5-865f-4723-9279-dcb2786df7e5" />



The final model achieved an overall accuracy of 99.22%, with precision, recall, and F1-scores exceeding 0.99 for both glacier and non-glacier classes:

Precision: 0.9921 (non-glacier), 0.9924 (glacier)

Recall: 0.9929 (non-glacier), 0.9915 (glacier)

F1-Score: 0.9925 (non-glacier), 0.9919 (glacier)

These results indicate the model performs very well, but the extremely high accuracy raises concerns about overfitting, particularly because the model was trained and tested on random splits of the full dataset rather than distinct polygons. While we added Gaussian noise to reduce memorization, additional steps like spatial cross-validation may be needed for more robust generalization.

**2. Feature Separation and Correlation**

The visual EDA confirms strong separation between glacier and non-glacier classes:

The NDSI index showed particularly strong separation, with glacier pixels concentrated around 0.4–0.6 and non-glacier pixels near 0.

Bands SR_B2 to SR_B5 also demonstrated distinct class distributions.

NDVI showed some overlap but still contributed useful information.

The correlation matrix further validates the importance of these features. The glacier class is positively correlated with NDSI (0.92) and SR_B bands (>0.95), and negatively correlated with NDVI (−0.67), suggesting these variables are highly informative for classification.
<img width="419" alt="image" src="https://github.com/user-attachments/assets/5e4f34b8-5136-4bd2-84f7-7c38a35c3212" />




**3. Joint Feature Space**







<img width="717" alt="image" src="https://github.com/user-attachments/assets/2b40d5fa-1321-4ca0-abcd-e6f9e48178ac" />






A 2D scatterplot of NDSI vs. NDVI by glacier class shows clear clustering:

Glacier pixels (orange) form a tight cluster with high NDSI and low NDVI.

Non-glacier pixels (blue) are widely dispersed and tend toward higher NDVI and lower NDSI.

This demonstrates that combining spectral indices provides effective class separation even without geographic information.

