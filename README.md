<p align="center">
  <a href="https://example.com/">
    <img src="https://via.placeholder.com/72" alt="Logo" width=72 height=72>
  </a>

  <h3 align="center">Logo</h3>

  <p align="center">
    Short description
    <br>
    <a href="https://reponame/issues/new?template=bug.md">Report bug</a>
    ·
    <a href="https://reponame/issues/new?template=feature.md&labels=feature">Request feature</a>
  </p>
</p>

## Seurat object usage

At the top level, the Seurat object serves as a collection of Assay and DimReduc objects, representing expression data and dimensionality reductions of the expression data, respectively. The Assay objects are designed to hold expression data of a single type, such as RNA-seq gene expression, CITE-seq ADTs, cell hashtags, or imputed gene values. DimReduc objects represent transformations of the data contained within the Assay object(s) via various dimensional reduction techniques such as PCA. For class-specific details, including more in depth description of the slots, please see the wiki sections for each class.

## Slot data
pbmc[["RNA"]]@counts
pbmc[["RNA"]]@data # Normalized values are stored in here
pbmc[["RNA"]]@scale.data # ScaleData

- When running dimension reduction method, data must in ]@scale.data

## meta data (Cell-level meta data

## Seurat object structure
```
# Load the PBMC dataset
pbmc.data <- Read10X(data.dir = "../data/pbmc3k/filtered_gene_bc_matrices/hg19/")
# Initialize the Seurat object with the raw (non-normalized data).
pbmc <- CreateSeuratObject(counts = pbmc.data, project = "pbmc3k", min.cells = 3, min.features = 200)
pbmc

## An object of class Seurat 
## 13714 features across 2700 samples within 1 assay 
## Active assay: RNA (13714 features, 0 variable features
```

Features = gene
Samples = cell

