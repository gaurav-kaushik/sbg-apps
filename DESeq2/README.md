##Differential Expression
 
`diff.R` is a script for performing a differential expression analysis using the DESeq2 library in R.

This repository demonstrates:

1. How to build a container where you install custom R packages/libraries
2. How to make an R script that is command-line runnable
3. A CWL description for how to run the script inside the container (the description refers to an already-built container on the cloud)

**To run in the command line:** 

	Rscript diff.R data/brca_gene.csv data/brca_meta.csv csv_filename pdf_filename <rld | vsd>

- `brca_gene.csv` is a matrix of genes vs samples
- `brca_meta.csv` is a matrix of samples vs metadata (e.g. sample_type, gender)
- `*_filename` are the desired prefixes for your output files
- `<rld | vsd>` is your choice of normalization method (use "rld" or "vsd" without quotes)

**Note:** `brca_gene.csv` and `brca_meta.csv` were produced with Open Access TCGA Gene Quantification Data as the input (see `brca_index_file.txt` the for list of input files).

###Build your own container
To package this tool into a Docker container for testing and/or deployment, you can use the following command:
`docker build -t <repository/container:tag> .` 

Or you can pull the container using:
`docker pull gauravkaushik/rnaseq:workshop`

###Import into the Seven Bridges platform
You can import **`diff.cwl.json`** into the Seven Bridges platform to use for your own research or try wrapping this application yourself using the Tool Editor!

###Run using the Rabix Executor

Seven Bridges has developed a local executor for CWL. You can find it [here](http://www.github.com/rabix/bunny).

To run this tool with Rabix:

	./rabix diff.cwl.json input.json

Note: You may have the Rabix Executor installed in another directory. Make sure the path to the executor and JSONs are correct.
