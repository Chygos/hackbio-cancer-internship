
## **Methodology**

### **Dataset Description and Preprocessing Steps**

Expression data for lower grade gliomas (LGG) cancer data for this study was sourced from [The Cancer Genome Atlas (TCGA)](https://www.cancer.gov/ccg/research/genome-sequencing/tcga). The dataset comprised 534 samples: 516 primary tumor cases and 18 recurrent cases. Only primary cases were selected.

### **Data Preparation and Preprocessing**

Data preprocessing and normalization were conducted using the TCGAbiolinks library in R. The steps included

- **Filtering genes:** Genes with a correlation less than 0.6 across samples were removed.
- **Normalization:** Expression levels were normalized based on gene length and GC content.
- **Exclusion of low-expression genes:** Genes with expression levels below the 25th percentile were excluded.

### **Biomarker Discovery and Machine Learning**

#### **Differential Gene Expression (DGE) Analysis**

We performed DGE analysis using the likelihood ratio method, identifying differentially expressed genes based on the criteria: False discovery rate (FDR) < 0.05 and Absolute log fold change > 2. Genes with FDR < 0.05 and LogFC < -2 were classified as downregulated, while genes with FDR < 0.05 and LogFC > 2 were classified as upregulated. The preprocessed data, consisting of about 26,000 genes, was used for subsequent machine learning predictions (Fig 1). DGE analysis was based on the tumor grade (Grade 2 vs Grade 3) and IDH status (Wild type vs Mutant).

#### **Pathway Enrichment Analysis**
We conducted pathway enrichment analysis to determine the biological roles of the upregulated and downregulated genes. This included analyzing the molecular functions, cellular localization, and biochemical pathways in which these genes are involved.

#### **Machine Learning**

__Data Splitting__

The preprocessed dataset was split into train and test sets, with 75% for model development and the other 25% for model evaluation.

__Feature Selection__

- __Filtering:__ Statistically insignificant genes from DGE analysis (FDR > 0.05) were removed reducing the features to about 24,000 genes.
- __Lasso Logistic Regression:__ A Lasso regression model was used to select features by applying a penalty which shrank unimportant features to exactly zero. A total of 91 genes were selected for modeling based on non-zero coefficient values (Fig 6).

__Modeling__

The k-nearest neighbors (k-NN) (k=5) and random forest models were used to train a model for predicting IDH status. The model's performance was evaluated using accuracy, recall, F1 score, precision, and specificity.


