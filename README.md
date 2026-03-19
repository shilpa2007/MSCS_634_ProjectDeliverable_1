# Advanced Data Mining for Data-Driven Insights and Predictive Modeling  
### Deliverable 1: Data Collection, Cleaning, and Exploration  
**Dataset:** Brain Tumor Feature Dataset  
**Author:** Vinay Varma Sagi 
**Course:** MSCS 634 – Advanced Data Mining  



##  Project Overview  
This project focuses on the application of data mining techniques to extract meaningful patterns, relationships, and insights from medical imaging data. The primary goal of this deliverable is to collect, clean, and explore a dataset containing extracted first-order and second-order features from MRI brain scans. These features are instrumental in distinguishing between tumor and non-tumor images. The deliverable establishes a strong foundation for subsequent stages of feature engineering, regression modeling, classification, and clustering that will follow in later phases of the project.

The dataset used is the **Brain Tumor Feature Dataset**, which includes 3,762 records and 15 columns. Each record corresponds to an image sample with computed numerical features such as Mean, Variance, Standard Deviation, Skewness, Kurtosis, Contrast, Energy, Entropy, ASM, Homogeneity, Dissimilarity, Correlation, and Coarseness. The column **Class** serves as the target variable, where `1` indicates the presence of a tumor and `0` represents a non-tumor image.


## Dataset Summary and Key Insights  
The dataset combines both **first-order statistical features** (e.g., Mean, Variance, Skewness, Kurtosis) and **texture-based second-order features** (e.g., Contrast, Energy, Homogeneity, ASM, and Correlation). These descriptors provide an in-depth numerical representation of the images’ intensity distribution and textural complexity.  

The exploratory data analysis (EDA) revealed several important insights:  
1. Tumor images typically exhibit **higher Variance and Dissimilarity values**, suggesting more irregular intensity distributions compared to non-tumor images.  
2. There are strong **positive correlations** among features such as Energy, ASM, and Homogeneity, indicating overlapping textural properties.  
3. The **Entropy** and **Contrast** features showed significant variation across samples, providing potential discriminatory power for classification tasks.  
4. The data was free of missing values and duplicates, and outlier detection using the Interquartile Range (IQR) method revealed a notable number of extreme observations, particularly in the Contrast and Kurtosis features.  
5. Visualization techniques, including histograms, boxplots, and heatmaps, highlighted the data’s overall structure, feature relationships, and outlier presence.



##  Data Cleaning and Exploration Steps  
The cleaning and preprocessing phase involved multiple systematic steps to ensure data quality and consistency:  
- **Loading and inspection**: The dataset was loaded into a Pandas DataFrame, and its structure, data types, and non-null counts were verified using `.info()` and `.describe()`.  
- **Missing value treatment**: The dataset was found to have no missing values; hence, no imputation was necessary.  
- **Duplicate removal**: A check for duplicate entries was performed and confirmed that none existed.  
- **Outlier detection and removal**: Outliers were identified using the IQR technique and removed to improve model reliability.  
- **Exploratory data analysis (EDA)**: Visualization techniques such as histograms, boxplots, and correlation heatmaps were employed to uncover data patterns, relationships, and variability across features.  
- **Data export**: The cleaned dataset was saved as `Brain_Tumor_Cleaned.csv` for subsequent feature engineering and modeling tasks.


## Challenges and Solutions  
One of the primary challenges encountered was dealing with the **high variability in feature scales**, as values ranged from near-zero decimals (e.g., Coarseness) to extremely high magnitudes (e.g., Contrast and Kurtosis). This discrepancy could lead to model bias during later stages of machine learning. The issue was addressed by planning to apply **feature scaling techniques** such as **Min-Max Normalization** and **Z-Score Standardization** in future deliverables to standardize data ranges.  

Another challenge was the **presence of numerous outliers** that could distort statistical summaries and skew distributions. This was effectively managed through the **Interquartile Range (IQR) method**, which allowed for systematic detection and removal of anomalous values without compromising dataset integrity. Additionally, ensuring that correlations were properly interpreted required careful visual analysis, supported by the use of a heatmap for improved clarity.



##  Conclusion  
The Brain Tumor Feature Dataset has been successfully cleaned, explored, and prepared for advanced analytical tasks. The insights gained from this phase provide a strong foundation for subsequent predictive modeling, including classification, clustering, and association analysis. The cleaned and structured dataset will serve as a reliable input for deriving meaningful, data-driven insights that can contribute to early tumor detection and medical image interpretation.


