##Differential Expression
 
`diff.R` is a script for performing a differential expression analysis using the DESeq2 library in R.

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
