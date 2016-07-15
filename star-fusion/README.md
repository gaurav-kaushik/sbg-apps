# STAR-Fusion

You can find the STAR-Fusion wiki [here](https://github.com/STAR-Fusion/STAR-Fusion/wiki/Home/2d0814500e882bf4eafa039f47030855d418c0f2).

This repository contains two tools:

1. STAR-untar
2. STAR-Fusion

STAR-Fusion identifies fusion transcripts from RNA-Seq data. It takes an untar'd index file and a junction file (from STAR):

	STAR-Fusion --genome_lib_dir </path/to/genome/dir> -J <chimeric.junction> --output_dir <dir> --CPU <5>
