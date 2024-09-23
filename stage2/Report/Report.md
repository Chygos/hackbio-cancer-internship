**Gene Expression Patterns in Glioblastoma: Heatmap Visualization and Pathway Enrichment Analysis**

@Hackbio @slack 

 _Authors:_

- Chaimaa BenMohamed
- Charlotte Chinwendu Iwuji
- Chigozie Nkwocha
- Igwebuike Vivian
- Opeyemi De Campos
- Reem  Atawia

**Overview**

This task focuses on visualizing and interpreting a gene expression dataset related to glioblastoma, the most common primary malignant brain tumor. The aim is to generate heatmaps, identify differentially expressed genes (DEGs), and perform functional enrichment analysis to interpret biological processes that contribute to the disease.

**Protein with unfavorable prognosis in glioblastoma**

Numerous genes are implicated in the pathogenesis of glioblastoma (Figure 1), including the EGF (Epidermal Growth Factor) gene, which encodes the Epidermal Growth Factor Receptor (EGFR) protein that plays a critical role in cell signaling pathways regulating cell division and survival (Brosseau et al., 2015). Mutations in this gene can lead to EGFR overexpression, resulting in abnormal cell proliferation, with most mutations occurring in the EGFRvII and EGFRvIII variants, while the EGFRx variant, which lacks a binding domain due to the deletion of exons 2–14, is essential for tumor growth in glioblastoma xenografts (Huang et al., 2023; Chen et al., 2016; Singh et al., 2023).

![Figure 1](https://github.com/cha1ima/hackbio-cancer-internship/blob/main/Stage%202/Images/Figure%201.png?raw=true)

**_Figure 1: _**_EGFR signaling and related pathways in cancer involve gene products that transmit signals from the cell surface to the nucleus, mediated by EGFR._


**Data Preprocessing and Visualization**

Using the glioblastoma dataset, containing over 500 differentially expressed genes from 10 patients, the first step involved preprocessing, which included data normalization and exploration. Heatmaps were generated using a diverging and sequential color palette to improve interpretation. The diverging palette effectively visualized the difference between upregulated and downregulated genes, while the sequential palette allowed a smoother transition in gene expression intensities. Both palettes were essential for making high, low, and medium values easily distinguishable.

Clustering of genes and samples was performed in three ways:

1. Clustering of genes alone (Figure 2).
2. Clustering of both genes and samples (Figure 3.
3. Clustering of samples alone (Figure 4).

**Genes only**

![Figure 2](https://github.com/cha1ima/hackbio-cancer-internship/blob/main/Stage%202/Images/Figure%202.png?raw=true)

**_Figure 2: _**_Heatmap showing clusters on genes alone_



**Both genes and samples**


![Figure 3](https://github.com/cha1ima/hackbio-cancer-internship/blob/main/Stage%202/Images/Figure%203.png?raw=true)

**_Figure 3: _**_Heatmap showing clusters on genes and samples_****



**Samples only**


![Figure 4](https://github.com/cha1ima/hackbio-cancer-internship/blob/main/Stage%202/Images/Figure%204.png?raw=true)

**_Figure 4: _**_Heatmap showing clusters on samples alone_

These visualizations identified distinct gene expression patterns, helping to group related genes and patients based on their molecular signatures.


**Differentially Expressed Genes (DEGs)**

DEGs were identified using a t-statistical test, setting a significance level of 5%. The log2 fold change (FC) was calculated using this formula:

![LogFC](https://github.com/cha1ima/hackbio-cancer-internship/blob/main/Stage%202/Images/LogFC%20equation.png?raw=true)

with cut-offs of >1.5 for upregulation and <-1.5 for downregulation. From the analysis, 10 genes were upregulated and 2 were downregulated (Figure 5). A volcano plot was created to visualize these results, showing how significantly genes were either up- or downregulated based on their p-values and fold changes.

![Figure 5](https://github.com/cha1ima/hackbio-cancer-internship/blob/main/Stage%202/Images/Figure%205.png?raw=true)

**_Figure 5: _**_Volcano Plot of Glioblastoma dataset (Horizontal axis represents log2-fold change, and the vertical axis represents adjusted p-value)._

**Functional Enrichment Analysis**

Using ShinyGO (Ge et al., 2019b), functional enrichment analysis was performed to identify key biological pathways affected by the upregulated and downregulated genes (Figures 6 and 7). Lollipop plots were created to show the top five pathways, scaling the points according to the negative log10 of the p-value to reflect their significance.

![Figure 6](https://github.com/cha1ima/hackbio-cancer-internship/blob/main/Stage%202/Images/Figure%206.png?raw=true)

**_Figure 6: _**_Top five biological processes for downregulated genes._

![Figure 7](https://github.com/cha1ima/hackbio-cancer-internship/blob/main/Stage%202/Images/Figure%207.png?raw=true)

**_Figure 7_**_: Top three biological processes pathways for upregulated genes._

Figures 6 and 7 are **lollipop charts** showing the top biological processes for downregulated and upregulated genes, respectively. The dots show the number of genes in each biological process and the colors of the line show their fold enrichment scores.

**The top 3 upregulated pathways include:**

1. **Glutathione derivative metabolic process**: Critical in neutralizing reactive oxygen species (ROS) and promoting cancer cell survival through redox balance (Kennedy et al., 2020).
2. **Glutathione derivative biosynthetic process**: Involves increased glutathione production, allowing glioblastoma cells to survive oxidative stress (Backos et al., 2012).
3. **Proteolysis**: Supports extracellular matrix degradation and enhances tumor growth by remodeling the tumor microenvironment (Bischof et al., 2017).

**Top 3 Downregulated Pathways:**

1. **Ribosomal small subunit assembly**: Ribosomal proteins support tumor progression by maintaining stem-cell-like properties in glioblastoma (Hide et al., 2022).
2. **Maturation of SSU-rRNA from tricistronic rRNA transcript**: Disruptions in ribosomal function promote carcinogenesis (Shirakawa et al., 2021).
3. **Maturation of SSU-rRNA**: Linked to ribosomal disorders, contributing to tumor development (McElreavey et al., 2022).

These analyses provided insights into the pathways driving glioblastoma pathogenesis, offering potential targets for therapeutic intervention.

 


# **REFERENCES**

Backos, D.S., Franklin, C.C. and Reigan, P., 2012. The role of glutathione in brain tumor drug resistance. _Biochemical Pharmacology_, 83(8), pp.1005-1012. doi: 10.1016/j.bcp.2011.11.016.

Bischof, J., Westhoff, M.-A., Wagner, J.E., et al., 2017. Cancer stem cells: The potential role of autophagy, proteolysis, and cathepsins in glioblastoma stem cells. _Tumor Biology_, 39(3). doi:10.1177/1010428317692227.

Brosseau, S., Viala, M., Varga, A., Planchard, D., Besse, B. and Soria, J.C., 2015. 3rd generation's TKI in lung cancer non-small cell EGFR-mutated having acquired a secondary T790M resistance. _Bulletin du Cancer_, 102, pp.749–757. doi: 10.1016/j.bulcan.2015.05.001.

Brown, N.F., Ottaviani, D., Tazare, J., Gregson, J., Kitchen, N., Brandner, S., Fersht, N. and Mulholland, P., 2022. Survival outcomes and prognostic factors in glioblastoma. _Cancers_, 14(13). doi: 10.3390/cancers14133161.

Chen, J., Zeng, F., Forrester, S.J., Eguchi, S., Zhang, Z. and Harris, R.C., 2016. Expression and function of the epidermal growth factor receptor in physiology and disease. _Physiological Reviews_. doi: 10.1152/PRV-00030-2015.

Gilard, V., Tebani, A., Dabaj, I., Laquerrière, A., Fontanilles, M., Derrey, S., Marret, S. and Bekri, S., 2021. Diagnosis and management of glioblastoma: A comprehensive perspective. _Journal of Personalized Medicine_, 11(4). doi: 10.3390/jpm11040258.

Hide, T., Shibahara, I., Inukai, M., Shigeeda, R. and Kumabe, T., 2022. Ribosomes and ribosomal proteins promote plasticity and stemness induction in glioma cells via reprogramming. _Cells_, 11(14), p.2142.

Huang, W., Li, J., Zhu, H., Qin, X., Chen, C., Wang, B., Wei, J., Song, Y., Lu, X., Li, Z., et al., 2023. A novel EGFR variant EGFRx maintains glioblastoma stem cells through STAT5. _Neuro-Oncology_, 26, pp.85–99.

Kennedy, L., Sandhu, J.K., Harper, M.E. and Cuperlovic-Culf, M., 2020. Role of glutathione in cancer: From mechanisms to therapies. _Biomolecules_, 10(10), p.1429. doi: 10.3390/biom10101429.

McElreavey, K., Pailhoux, E. and Bashamboo, A., 2022. DHX37 and 46,XY DSD: A new ribosomopathy? _Sexual Development_, 16, pp.194–206.

Singh, S., Barik, D., Lawrie, K., Mohapatra, I., Prasad, S., Naqvi, A.R., Singh, A. and Singh, G., 2023. Unveiling novel avenues in mTOR-targeted therapeutics: Advancements in glioblastoma treatment. _International Journal of Molecular Sciences_, 24, p.14960.

Shirakawa, Y., Ohta, K., Miyake, S., Kanemaru, A., Kuwano, A., Yonemaru, K., Uchino, S., Yamaoka, M., Ito, Y., Ito, N., Hide, T., Shinojima, N., Mukasa, A., Saito, H. and Jono, H., 2021. Glioma cells acquire stem-like characters by extrinsic ribosome stimuli. _Cells_, 10(11), p.2970. doi: 10.3390/cells10112970.

<a id="_6agy3xqjct9u"></a>

Ge, S. X., Jung, D., & Yao, R. (2020). ShinyGO: a graphical gene-set enrichment tool for animals and plants. _Bioinformatics (Oxford, England)_, _36_(8), 2628–2629. doi:10.1093/bioinformatics/btz931.
