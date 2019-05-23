

[![DOI](https://zenodo.org/badge/185804041.svg)](https://zenodo.org/badge/latestdoi/185804041)


# primerpython
A wrapper for Primer3 to automatically create PCR primers for locus alignments. 

This software is considered BETA and comes without any warranty. Please open an issue if you have any questions or encounter problems. 

The repository includes a binary of Primer3 (https://github.com/primer3-org). I do not claim any ownership on Primer3. Please refer to the Primer3 website for licensing and documentation. 

## Usage

Primerpython expects a directory containing multiple sequence alignments (MSA) with the filename suffix *.aln.fa (`-i`).
Primerpython creates a consensu sequence from the MSA, and tries to identify conserved regions around the midpoint of the MSA to create PCR primers. 
The primers are designed by Primer3. 

You need to define a primer start number (`-n`), that defines a start of the incremental numbering of the primers. That way you can use primer python to design primers 1-10 for a first batch of ten sequences and 11-20 for a second batch. 

A new alignment that include the primer sequences as well as a tabular list of the primers are generated as output.

To change PCR parameters change the `primer3_config.orig` file according to the Primer3 documentation. A copy of the parameters are written to `primer3_config.orig.pry3`

```
$ ./primerpython.py 
usage: primerpython.py [-h] -i INPUT_PATH -n PRIMER_START_NO
```

## Citation

If you use primerpython for your published research, please consider citing this repository by using the DOI: https://doi.org/10.5281/zenodo.3210632. 


## Ideas 

Future development could focus on 
- [ ] select amplicon regions
- [ ] easy changing of PCR parameters
