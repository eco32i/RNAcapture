# RNAcapture
Analysis scripts for lnrCXCR4 lncRNA paper

# Dependencies

The analysis was performed on a ubuntu 16.04 workstation with 32 cores. Adjust the value of `NUMPROC` variable to match the number of cores in your machine.

## Non-python dependencies

These can be installed either system-wide or in user space. Make sure the appropriate executables are on `PATH`.

* [samtools v1.5.2](http://samtools.sourceforge.net/)
* [bedtools v2.26](http://bedtools.readthedocs.io/en/latest/index.html)
* [bowtie2 v2.3.0](http://bowtie-bio.sourceforge.net/bowtie2/index.shtml)
* [Trimmomatic](http://www.usadellab.org/cms/?page=trimmomatic)

## Python dependencies

Create the virtual environment and install python dependencies like so:

```
$ pyvenv ~/.venv/RNAcapture
$ source ~/.venv/RNAcapture/bin/activate
(RNAcapture)$ pip install -r requirements.txt
```
## Running notebooks

The analysis is organized into three `jupyter` notebooks:

### `00 - Build reference.ipynb`

Download the reference, extract appropriate sequences and build the index for `bowtie2`

### `01 - Quality trimming and alignment.ipynb`

Perform quality trimming and reads alignment to the reference. Prepare locus coverage files for the next step.

### `02 - Locus coverage plots.ipynb`

Plot the coverage of the reference locus along with provided `.gtf` annotations

To run the analysis download the data files and place them in the top level `RNAcapture` directory:

```
|-RNAcapture
|---data
|   |---yoon01
|   |---yoon02
|   |---yoon03
...
```
Then activate `RNAcapture` environment and launch `jupyter`:

```
$ source ~/.venv/RNAcapture/bin/activate
(RNAcapture)$ jupyter notebook
```

