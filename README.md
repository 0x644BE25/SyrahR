# SyrahR
SyrahR is an R package that provides read 1 error correction for [Slide-seqV2](https://www.nature.com/articles/s41587-020-0739-1) and [Curio Seeker](https://curiobioscience.com/seeker/) spatial transcriptomic data. 

**NOTE:** This is the R package version of Syrah that only corrects the read 1 FASTQ and is intended for use in conjunction with a standard [Slide-seqV2](https://broadinstitute.github.io/warp/docs/Pipelines/SlideSeq_Pipeline/README) or Curio Seeker analysis pipeline. If you are looking for the standalone analysis pipeline, it is [here](https://github.com/0x644BE25/Syrah).

## Installation
You will need to have [R](https://www.r-project.org/) and [devtools](https://www.rdocumentation.org/packages/devtools/versions/2.4.5) installed, then run
```
library(devtools)
install_github("0x644BE25/SyrahR")
```


## Inputs
SyrahR takes as input the tab-delimited bead coordinates file and the read 1 FASTQ file.

## Basic Usage
```
library(SyrahR)
syrah(coords_file="coodinates_file.txt", r1_fastq="read1_file.fastq")
```

## Output
SyrahR will output a bead deduplication map text file, a barcode whitelist file, and a corrected read 1 FASTQ with a filename ending in `.r1syrah`
This corrected read 1 FASTQ can now be input into your spatial transcriptomic pipeline of choice along with the original read 2 FASTQ and coordinates file.

## Advanced Usage
<img width="878" height="578" alt="image" src="https://github.com/user-attachments/assets/9743559f-1fe3-4cdb-80ee-4047e6ee0b96" />

## Parameters

| Parameter name      | Description                                                                                                                                                                                                                                                                    | Example                                    |
|------------------|----------------------------|--------------------------|
| `coords_file`         | Path to a tab-delimited file containing the barcodes and coordinates for the puck | `"/path/to/myWorkingDir/coordinates.txt"` |
| `r1_fastq`          | Path to the read 1 FASTQ file, or a comma-delimited list of read 1 FASTQ files | `"path/to/myWorkingDir/read_1.fastq"` |
| `write_dir`        | (optional) Directory to write to. Defaults to current working directory. | `"/path/to/myWorkingDir/"`  |
| `n_cores`        | (optional) Number of CPU cores to use. Defaults to 1.  | `1`         |
| `max_slide_dist`          | (optional) Maxium allowable slide distance between beads to consider them duplicated. You are very unlikely to need to change this. Defaults to 10. | `10`  |
| `max_linker_dels`          | (optional) Maximum allowable number of deletions for an acceptable linker match. You are unlikely to need to change this. Defaults to 5. | `5`  |
| `batch_size`          | (optional) Number of reads to process at once.  You are very unlikely to need to change this. Defaults to 10^5. | `10^5`  | 
