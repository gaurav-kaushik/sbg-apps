# dna2protein

This example consists of two CWL tools (Transcribe, Translate) and one workflow (dna2protein), as well as the Dockerfile you can use to build a container with the tools inside.

Transcribe takes a TXT file containing a DNA Sequence as an input and produces a TXT file with an mRNA Sequence. Translate takes an mRNA Sequence, identifies the first ORF, and produces a TXT file with a peptide sequence as an output. dna2protein consists of *input -> Transcribe > Translate --> output*.

To run locally with Python:

1. `python scripts/transcribe.py -d data/input.txt > data/rna.txt`
2. `python scripts/translate.py -r data/rna.txt > data/protein.txt`

OR

`python scripts/transcribe.py -d data/input.txt | python scripts/translate.py > data/protein.txt`


###Run using the Rabix Executor

Seven Bridges has developed a local executor for CWL. You can find it [here](http://github.com/rabix/bunny).

To run this workflow with Rabix:

	./rabix dna2protein.cwl.json input.json

Note: You may have the Rabix Executor installed in another directory. Make sure the path to the executor and JSONs are correct.

