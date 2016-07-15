#SamTools Sort

This repository contains:

1. A Dockerfile you can use to create a container with SamTools 1.2
2. A CWL description of how to use SamTools Sort to sort an unsorted BAM file

####To run in the command line:
	samtools sort <unsorted.bam> <sorted.bam>

####Build your own container
To package this tool into a Docker container for testing and/or deployment, you can use the following command:
`docker build -t <repository/container:tag> .` 

Or you can pull the container using:
`docker pull gauravkaushik/samtools:1.2`

####Import into Seven Bridges
You can import **`samtools.sort.cwl.json`** into Seven Bridges to use for your own research or try wrapping this application yourself using the Tool Editor.

####Exercises
You can customize this tool to your specifications.

Import the tool into Seven Bridges, then try the following exercises:

1. Add the ability to add a user-specified prefix to the sorted bam filename at runtime. [Hint: this requires an additional input port and a dynamic expression]

		output prefix: "new"
		sorted bam file: new_sorted.bam

2. Add the ability to pass the basename of the input file as a prefix for the sorted bam file if no custom prefix is given by the user. [Hint: this only requires a modification to the dynamic expression used in (1)]

	With an empty prefix:

		output prefix = ""
		input bam file = sample01.bam
		output bam file = sample01_sorted.bam

	With a specified prefix:

		output prefix = "new"
		input bam file = sample01.bam
		output bam file = new_sorted.bam
		
3. Create a workflow with SamTools Sort, with which you can create "Batch Tasks."
		
