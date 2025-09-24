# SyrahR
SyrahR is an R package that provides read 1 error correction for [Slide-seqV2](https://www.nature.com/articles/s41587-020-0739-1) and [Curio Seeker](https://curiobioscience.com/seeker/) spatial transcriptomic data. **NOTE:** is the R package version of Syrah that only corrects the read 1 FASTQ and is intended for use in conjunction with a standard [Slide-seqV2](https://broadinstitute.github.io/warp/docs/Pipelines/SlideSeq_Pipeline/README) or Curio Seeker analysis pipeline. If you are looking for the standalone analysis pipeline, it is [here](https://github.com/0x644BE25/Syrah).

## Installation
You will need to have [R](https://www.r-project.org/) and [devtools](https://www.rdocumentation.org/packages/devtools/versions/2.4.5) installed, then run
```
library(devtools)
install_github("0x644BE25/SyrahR")
```

