# Biohackathon-Team-12-Breast-Cancer

## Breast Cancer Overview
### What is Breast Cancer?
Breast cancer is a malignant tumor that develops in breast cells. It is one of the most common forms of cancer affecting women. In fact, approximately 1 in 8 women (or 13%) will be diagnosed with breast cancer at one point in their lives. 

### Symptoms
From a clinical perspective, the symptoms associated with breast cancer include a lump or thickening in the breast/underarm, change in breast size or shape, skin changes on the breast, nipple changes or discharge, and pain in the breast. 

### Diagnostic Criteria
Typically, a diagnosis of breast cancer is made after a breast biopsy. However, imaging through a mammogram, ultrasound, or MRI can be used to identify suspicious areas to check with a breast biopsy.

### Prognostic Criteria
A patient's prognosis for breast cancer is made using a combination of criteria, which include cancer stage, tumor grade, biomarker status, age (younger than 60 is associated with poorer prognosis), histologic type, Ki-67 index (a marker for cell proliferation, and lymph node involvement. None of these factors are considered in isolation; rather, a combination of these factors is taken into consideration when providing a prognosis for a breast cancer patient.

### Frontline Treatment Options
Currently, the frontline treatments for breast cancer include surgery (lumpectomy or mastectomy), radiation therapy, hormone therapy (tamoxifen, aromatase Inhibitors, ovarian suppression), targeted therapy (trastuzumab or pertuzumab), immunotherapy, and chemotherapy. Current chemotherapy regiments are AC-T (Adriamycin, Cyclophosphamide, followed by Taxol), TC (Taxotere and Cyclophosphamide 5), and CMF (Cyclophosphamide, Methotrexate, and 5-Fluorouracil 5). The choice of treatment depends on several factors, such as the cancer stage, tumor size/location, HER2 status (amount of breast cancer cells), and overall patient health.

### Successful Treatment Signs
A successful treatment for breast cancer would show any of the following: a reduction in tumor size, complete disappearance of the tumor, prolonged time without cancer growth, and biomarker improvements (such as a decrease in tumor markers).

### Options if Frontline Treatment Fails:
If the frontline treatment fails, there are other treatment options that can be taken. Alternative chemotherapy regimens may be recommended, advanced targeted therapies (T-DM1, tucatinib, CDK4/6 and mTOR inhibitors), and alternative immunotherapy options may be prescribed. Additionally, patients can try PARP inhibitors to see if they qualify for any clinical trials. Lastly, patients can focus on treatments targeted at symptom management and improving quality of life.

### Organs Involved in Expression of Breast Cancer
The primary site of breast cancer is breast tissue. This includes mammary glands, ducts, and lobules. However, breast cancer can metastasize to other sites, and common sites of metastasis include bone, lungs, liver, brain, and lymph nodes. The pattern of metastasis can vary depending on the severity and molecular subtype of breast cancer. 

## Methods
### Finding seed genes:  
Genes that are associated with breast cancer were identified in an OMIM (www.omim.org) search, which returned a total of 20 genes that harbor known gene-phenotype relationships in breast cancer.  The 20 gene list was then queried using generative AI (Prometheus) on the PraxisAI platform (https://learning.praxislxp.com/) to help identify the top 5 most significant genes based on the scientific literature and reliable public databases.  These 5 genes served as the known candidate 'seed' genes associated with breast cancer for this analysis: *BRCA2* (600185), *ESR1* (133430), *CDH1* (92090), *BARD1* (601593), and *KRAS* (190070).  

### Building the PPI Network: 
The 'seed' gene node list was used for building a protein:protein interaction (PPI) network, which can provide insight into cellular processes, disease mechanisms, and protein functions in breast cancer. The human protein interactors in the PPI network were determined via searching of the ‘seed’ genes in the European Bioinformatics Institute (EBI) Intact database (https://www.ebi.ac.uk/intact).  The PPI mitab files were obtained for each seed gene from Intact and processed via Python to generate a PPI list, that lists the seed genes and target gene edges (protein interactors), see *biohackathon-BC_PIP_pythonscript.txt.*

### Visualization and Characterization of the PPI Network:  
The PPI list (see *Biohackathon_BCdisease_Edges.csv*) was uploaded into the Cytoscape software platform (https://cytoscape.org/index.html) for visualization and further characterization of the PPI network. Cytoscape's gene enrichment tool was utilized to identify significantly enriched biological functions and pathways (p-value < 1e-20) in the network to explore how they relate to each other and the network as a whole, see *Biohackathon_BCdisease_gene_enrichments.csv.* 

## Results

### Genes Underlying Breast Cancer
BARD1, BRCA2, ESR1, KRAS, and CDH1 genes are associated with breast cancer and each of these genes plays a unique role in the development and progression of breast cancer.

 * *BARD1* is involved in DNA double-strand break repair and plays a crucial role in tumor suppression. *BARD1* is closely associated with *BRCA1*, another tumor suppressor gene involved in DNA repair and cell cycle regulation.
 * *BRCA2* is crucial for maintaining genomic stability through its role in homologous recombination DNA repair and is a well-known tumor suppressor gene. Mutations in the *BRCA2* gene significantly increases risk of breast and ovarian cancers.
 * *ESR1* encodes the estrogen receptor alpha (ERα) which is a transcription factor that, when activated by estrogen, regulates the expression of genes involved in cell proliferation and survival. Mutations in *ESR1* can lead to hormone therapy resistance in breast cancer patients
 * *KRAS* is a GTPase that regulates cell proliferation and survival. *KRAS* mutations are commonly associated with other cancers, and can play a role in breast cancer development.
 * *CDH1* encodes E-cadherin, a protein crucial for cell-cell adhesion in epithelial tissues.  Loss of E-cadherin function can lead to increased cell motility and invasiveness, promoting cancer metastasis.

Three potential hypotheses consider the complex molecular mechanisms underlying disease development to explain how the misexpression of these genes can lead to breast cancer:  
* Hypothesis 1: Disruption of DNA Repair Mechanisms and Genomic Instability- *BRCA2* and *BARD1* are both involved in DNA Repair Pathways, and defects in these pathways can lead to genomic instability and increased cancer risk. 
* Hypothesis 2: Dysregulation of Cell Signaling and Proliferation Pathways- *KRAS* mutations can induce downstream signaling pathways that may interfere or override the protective effects of tumor suppressor genes or the regulatory effects of hormone receptors, such as *BRCA2* or *ESR1*, respectively. 
* Hypothesis 3: Compromised Cell Adhesion and Enhanced Metastatic Potential- *CDH1* mutations can lead to loss of cell-cell adhesion and potentially interact with other pathways to promote cancer cell invasion and metastasis.



### Protein-Protein Interaction (PPI) Network
* #### The 'seed' gene node list:
  * *BRCA2* (600185)
  * *ESR1* (133430)
  * *BARD1* (601593)
  * *CDH1* (92090)
  * *KRAS* (190070)
 
The separate Intact PPI mitab files for each seed gene were processed via a Python script into a single CSV file, where each row in the CSV contains a seed gene and its interacting partner, see *Biohackathon_BCdisease_Edges.csv.*

#### EBI Intact Database PPI Analysis Results:
> Processing complete. Results:
BRCA2: 95 interacting genes
BARD1: 64 interacting genes
KRAS: 458 interacting genes
CDH1: 553 interacting genes
ESR1: 184 interacting genes


#### Cytoscape PPI Network:

 ![Alt text](https://github.com/zackverdin/Biohackathon-Team-12-Breast-Cancer/blob/main/Biohackathon_BCdisease_Edges.png.png)
 
Cytoscape's gene enrichment tool identified 306 significantly enriched terms and pathways (p-value < 1e-20) in the biological network to further explore, see *Biohackathon_BCdisease_gene_enrichments.csv.* 

 [Link text](URL)
     
### Tissue-specific eQTLs DNA polymorphisms

## Hypotheses



