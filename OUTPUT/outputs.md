**Model Visualizations**
We generated three sets of visualizations—histograms, violin plots, and density plots—to explore how different spectral bands and indices separate glacier and non-glacier classes.

**Histograms with KDE (Kernel Density Estimation):**
Most reflectance bands (especially SR_B3–SR_B5) show clear separation between glacier and non-glacier pixels. Glacier pixels tend to have much higher reflectance values, while non-glacier pixels cluster at lower values. NDSI and NDVI in particular show strong bimodality, with glaciers displaying high NDSI and low NDVI values.

**Violin Plots by Glacier Class:**
Violin plots reinforce the separation observed in histograms. Glacier pixels show tight distributions centered around high reflectance in visible and near-infrared bands, while non-glacier pixels have broader distributions. The separation is especially visible in SR_B5 (NIR), SR_B6 (SWIR1), and NDSI.

**Density Plots:**
KDE plots emphasize that many features—especially NDSI—are nearly linearly separable between classes. While most bands show overlap, combining multiple features in a model allows for more robust classification, particularly in ambiguous cases such as debris-covered ice.

These visualizations suggest that a supervised model like a Random Forest can achieve high accuracy by leveraging the combined predictive power of all bands and indices. However, they also underscore the need for careful generalization, since some features (e.g., SR_B6) exhibit more class overlap than others.


**Model Visualizations**
To better understand how the spectral bands and indices contribute to glacier classification, we visualized the distributions of key features across glacier and non-glacier classes using histograms, violin plots, density plots, and correlation analysis.

**Band Distributions**
We plotted the distributions of SR_B2–SR_B6, NDVI, and NDSI across both classes:

1. Histograms and density plots show clear separations between glacier and non-glacier pixels across most bands.

2. Glacier pixels tend to have higher reflectance in bands SR_B2–B5 and higher NDSI values.

3. Non-glacier pixels are more dispersed but tend to cluster around lower reflectance and NDSI values.

**Violin Plots by Class**
Violin plots further illustrate this separation:

Bands like SR_B5 and NDSI show tight, distinct clusters by class.

NDVI exhibits a more subtle but still meaningful shift between glacier and non-glacier regions, with glaciers generally showing lower vegetation index values.

**NDSI vs. NDVI Scatterplot**
A scatterplot of NDSI vs. NDVI colored by glacier class highlights their joint effectiveness:

Glacier pixels cluster in a region with high NDSI and low NDVI.

Non-glacier pixels spread more broadly, with higher NDVI and lower NDSI, confirming their potential as a decision boundary in classification tasks.

**Correlation Matrix**
The correlation heatmap shows strong positive correlations between the glacier class and:

SR_B2–SR_B5 (~0.96–0.98)

NDSI (0.92)

There’s also a negative correlation with NDVI (−0.67), reinforcing that glacier-covered areas are spectrally and vegetatively distinct from surrounding land cover.

