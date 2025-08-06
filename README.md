## Clustering of Borehole Logging Data – I-EDDA TC1

This repository contains the Python workflow used in the context of a Master's thesis to apply unsupervised clustering methods to borehole geophysical logging data from the I-EDDA Test Center 1 (TC1) borehole. The main goal is to investigate to what extent physical logging parameters correlate with lithological variations, and to explore the internal structure of the dataset through unsupervised learning.
<br />

## Context

Geophysical logging data were acquired along the 962.9 m deep TC1 borehole drilled into various crystalline basement lithologies. The available parameters are:

- MSUS (Magnetic susceptibility)<br /> 
- Th (Thorium concentration)<br /> 
- U (Uranium concentration)<br /> 
- K (Potassium concentration)<br /> 
- Vp (P-wave velocity)<br /> 
- Rdeep (Deep resistivity)

These parameters serve as input features for clustering. The resulting clusters are then compared to true lithological labels to evaluate the degree of correspondence.
<br />

## Workflow Summary

1. Data Import and Preprocessing
    Two CSV files are imported: one containing physical logging parameters and one containing lithological labels.
    Logarithmic transformations are applied to handle skewed distributions.
    StandardScaler is applied to normalize the data for clustering.<br />
2. Clustering
    k-means clustering is performed with 4 clusters (n_clusters=4), based on scaled versions of the logarithmized input features.
    Cluster labels are added to the original dataset for comparison.<br />
3. Evaluation
    Internal clustering metrics are computed:
        Silhouette Score
        Davies-Bouldin index
        Calinski-Harabasz index
    The relationship between clusters and lithology is evaluated using heat maps based on confusion matrices. These visualizations provide insight into how well the clustering reflects geological reality and may inform further geostatistical or petrophysical interpretation. The heat maps display:<br />
        1. Absolute values<br />
        2. the percentual distribution of lithologies across the clusters)<br />
        3. the percentual composition of the clusters<br />

## Notes

- The code assumes that both the data and lithology CSV files are pre-processed and cleaned, including removal of invalid values such as nulls and missing values.<br />
- This script is not a general-purpose clustering pipeline, but part of a broader geological interpretation project.<br />
- All file paths are local and need to be adjusted for external use.<br />

## Citation

This repository is part of the Master’s thesis of Wilhelmine Klamt, submitted at University of Greifswald, Faculty of Mathematics and Natural Sciences, Institute of Geography and Geology, under the supervision of Dr. Simona Pierdominici (Helmholtz-Centre Potsdam, German Research Centre for Geosciences – GFZ, Telegrafenberg, 14473 Potsdam, Germany) and Dr. Grit Büttner (University of Greifswald, 17489 Greifswald, Germany), 2025.
