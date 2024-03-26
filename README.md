# scLEGA
scLEGA method for clustering scRNA-seq data

Current methods used for cell type inference based on single-cell RNA sequencing (scRNA-seq) data focus on highly expressed genes and ignore the role of low-expressed genes. These low-expressed genes may be critical for determining cell type or state, or may be key elements in regulatory networks. Relying on highly expressed genes may result in neglecting the specificity of certain cell types, compromising the accuracy and completeness of classification. To address this issue, we developed a new cell type inference method based on scRNA-seq data called scLEGA. scLEGA modifies the traditional zero-inflated negative binomial (ZINB) loss function, which in turn fully takes into account the importance of low-expressed genes in cell type inference, and thus learns a better clustering representation.

The code for this project references the https://github.com/LiShenghao813/AttentionAE-sc code with some modifications, which allows the scLEGA model to converge on lower gene expression, and thus learn more reasonable cell type inference characteristics.
## run environment

python --- 3.8

pytorch --- 1.11.0

torchvision --- 1.12.0

torchaudio --- 0.11.0

scanpy --- 1.8.2

scipy --- 1.6.2

numpy --- 1.19.5

leidenalg --- 0.8.10





## Usage
For applying AttentionAE-sc, the convenient way is  run "run_scLEGA.py"

Please place the scRNA-seq dataset you want to analyze in the directory "./Data/AnnData", where is the default for model input.
If you want to calculate the similarity between the predicted clustering resluts and the true cell labels (based on NMI or ARI score), please transmit your true labels into the "adata.obs['celltype']" and setting the argument "-celltype" to **True**.

