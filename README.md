# SCEA
An optimized graph-based structure for single-cell RNA-seq cell-type classification based on non-linear dimension reduction

## Requirements
Python --- 3.6.4

Tensorflow --- 1.12.0

Keras --- 2.1.0

Numpy --- 1.19.5

Scipy --- 1.5.4

Pandas --- 1.1.5

Sklearn --- 0.24.2

## Usage
### Inputs
All the original datasets are available here and can be downloded ([Biase](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE57249), [Klein](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE65525), [Romanov](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE74672), [Zeisel](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE60361), [Chung](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75688), [PBMC](https://support.10xgenomics.com/single-cell-gene-expression/datasets/2.1.0/pbmc4k), [Neuron_5k](https://cf.10xgenomics.com/samples/cell-exp/6.0.0/SC3_v3_NextGem_DI_Neurons_5K_SC3_v3_NextGem_DI_Neurons_5K/SC3_v3_NextGem_DI_Neurons_5K_SC3_v3_NextGem_DI_Neurons_5K_web_summary.html), [Mouse](https://figshare.com/s/865e694ad06d5857db4b), [Petropoulos](https://www.ebi.ac.uk/arrayexpress/exp), [Mouse_Brain](https://www.10xgenomics.com/resources/datasets/mouse-tissue-microarray-in-3x3-layout-with-2-mm-edge-to-edge-spacing-ffpe-2-standard)).

### Preprocessing
First, the original expression matrix brain.csv of dataset mouse_brain is downloaded and put into /data/mouse_brain. Using the following command, low-quality cells and genes can be filtered before clustering:
```Bash
python preprocess.py mouse_brain
```
The preprocessed matrix is then saved as data.tsv in /data/mouse_brain.

### Run SCEA
For SCEA to work, you must specify the address of the dataset and the number of clusters. for example, 
```Bash
python SCEA.py [dataset address] [number of clusters]
```
The following command can be used for mouse_brain data.
```Bash
python SCEA.py mouse_brain 5
```
### Outputs
Under the folder /result, you will find a text file named pred_Dataset.txt that contains the predicted clustering results.
As an example, for mouse_brain, we have:
pred_mouse_brain.txt
