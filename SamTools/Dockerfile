FROM ubuntu:latest

MAINTAINER "Gaurav Kaushik" <gaurav@sevenbridges.com>

WORKDIR /

# Update the package index inside the container
RUN apt-get update --yes 

# Install the tools we need to compile SamTools
RUN apt-get install wget build-essential zlib1g-dev libncurses5-dev vim --yes 

# Grab the SamTools 1.2 repo on GitHub
RUN wget https://github.com/samtools/samtools/releases/download/1.2/samtools-1.2.tar.bz2 && tar jxf samtools-1.2.tar.bz2

# cd into the folder and install SamTools
RUN cd samtools-1.2 && make && make install

CMD ["/bin/bash"]