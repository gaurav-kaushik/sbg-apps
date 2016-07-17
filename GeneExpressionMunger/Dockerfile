# Use the reference python container
FROM rfranklin/pythondev:latest

# Add the files from the GitHub repo [glob all (/*) files from each folder and put into homedir (/)]
RUN mkdir data
ADD scripts/munger.py /
ADD data/* data/

CMD ["/bin/bash"]