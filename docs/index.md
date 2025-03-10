<div align="center">

  <h1 style="font-size: 250%">methyl-seek 🔬</h1>

  <b><i>long pipeline name</i></b><br> 
  <a href="https://github.com/OpenOmics/methyl-seek/actions/workflows/main.yaml">
    <img alt="tests" src="https://github.com/OpenOmics/methyl-seek/workflows/tests/badge.svg">
  </a>
  <a href="https://github.com/OpenOmics/methyl-seek/actions/workflows/docs.yml">
    <img alt="docs" src="https://github.com/OpenOmics/methyl-seek/workflows/docs/badge.svg">
  </a>
  <a href="https://github.com/OpenOmics/methyl-seek/issues">
    <img alt="GitHub issues" src="https://img.shields.io/github/issues/OpenOmics/methyl-seek?color=brightgreen">
  </a>
  <a href="https://github.com/OpenOmics/methyl-seek/blob/main/LICENSE">
    <img alt="GitHub license" src="https://img.shields.io/github/license/OpenOmics/methyl-seek">
  </a>

  <p>
    This is the home of the pipeline, methyl-seek. Its long-term goals: to accurately call CpG sites within whole-genome and cell-free DNA fragments, to perform deconvolution for CpG calls within cell-free DNA fragments, and to boldly identify differentially methylated regions like no pipeline before!
  </p>

</div>  


## Overview

Welcome to methyl-seek's documentation! This guide is the main source of documentation for users that are getting started with the [methylation pipeline](https://github.com/OpenOmics/methyl-seek/). 

The **`./methyl-seek`** pipeline is composed several inter-related sub commands to setup and run the pipeline across different systems. Each of the available sub commands perform different functions: 

<section align="center" markdown="1" style="display: flex; flex-wrap: row wrap; justify-content: space-around;">

!!! inline custom-grid-button ""

    [<code style="font-size: 1em;">methyl-seek <b>run</b></code>](usage/run.md)   
    Run the methyl-seek pipeline with your input files.

!!! inline custom-grid-button ""

    [<code style="font-size: 1em;">methyl-seek <b>unlock</b></code>](usage/unlock.md)  
    Unlocks a previous runs output directory.

</section>

<section align="center" markdown="1" style="display: flex; flex-wrap: row wrap; justify-content: space-around;">


!!! inline custom-grid-button ""

    [<code style="font-size: 1em;">methyl-seek <b>install</b></code>](usage/install.md)  
    Download remote reference files locally.


!!! inline custom-grid-button ""

    [<code style="font-size: 1em;">methyl-seek <b>cache</b></code>](usage/cache.md)  
    Cache remote software containers locally.  

</section>

**methyl-seek** is a comprehensive bisulphite-sequencing-based DNA methylation pipeline. It relies on technologies like [Singularity<sup>1</sup>](https://singularity.lbl.gov/) to maintain the highest level of reproducibility. The pipeline consists of a series of data processing and quality-control steps orchestrated by [Snakemake<sup>2</sup>](https://snakemake.readthedocs.io/en/stable/), a flexible and scalable workflow management system, to submit jobs to a cluster.

The pipeline is compatible with data generated from Illumina short-read sequencing technologies. As [inputs](usage/run.md), it accepts a set of FastQ files and can be run locally on a compute instance or on-premise using a cluster. A user can define the method or mode of execution. The pipeline can submit jobs to a cluster using a job scheduler like SLURM (more coming soon!). A hybrid approach ensures the pipeline is accessible to all users.

Before getting started, we highly recommend reading through the [usage](usage/run.md) section of each available sub-command.

For more information about issues or troubleshooting a problem, please check out our [FAQ](faq/questions.md) prior to [opening an issue on Github](https://github.com/OpenOmics/methyl-seek/issues).

## Dependencies

**Requires:** `singularity>=3.5`  `snakemake<8.0`

At the current moment, the pipeline uses a mixture of environment modules and docker images; however, this will be changing soon! In the very near future, the pipeline will only use docker images. With that being said, [snakemake](https://snakemake.readthedocs.io/en/stable/getting_started/installation.html) and [singularity](https://singularity.lbl.gov/all-releases) must be installed on the target system. Snakemake orchestrates the execution of each step in the pipeline. To guarantee the highest level of reproducibility, each step of the pipeline will rely on versioned images from [DockerHub](https://hub.docker.com/u/skchronicles). Snakemake uses singularity to pull these images onto the local filesystem prior to job execution, and as so, snakemake and singularity will be the only two dependencies in the future.

## Installation

Please clone this repository to your local filesystem using the following command:
```bash
# Clone Repository from Github
git clone https://github.com/OpenOmics/methyl-seek.git
# Change your working directory
cd methyl-seek/
# Add dependencies to $PATH
# Biowulf users should run
module load snakemake singularity
# Get usage information
./methyl-seek -h
```

## Contribute

This site is a living document, created for and by members like you. **methyl-seek** is maintained by the members of OpenOmics and is improved by continuous feedback! We encourage you to contribute new content and make improvements to existing content via pull request to our [GitHub repository :octicons-heart-fill-24:{ .heart }](https://github.com/OpenOmics/methyl-seek).

## Citation

If you use this software, please cite it as below:  

=== "BibTex"
 
    ```text
    @software{neelam_redekar_2023_8387344,
      author       = {Neelam Redekar and Tom Hill and Skyler Kuhn},
      title        = {OpenOmics/methyl-seek: v1.0.0},
      month        = sep,
      year         = 2023,
      publisher    = {Zenodo},
      version      = {v1.0.0},
      doi          = {10.5281/zenodo.8387343},
      url          = {https://doi.org/10.5281/zenodo.8387343}
    }
    ```
  
=== "APA"

    ```text
    Neelam Redekar, Tom Hill, & Skyler Kuhn. (2023). OpenOmics/methyl-seek: v1.0.0 (v1.0.0). Zenodo. https://doi.org/10.5281/zenodo.8387343
    ```


For more citation style options, please visit the pipeline's [Zenodo page](https://doi.org/10.5281/zenodo.8387343).


## References

<sup>**1.**  Kurtzer GM, Sochat V, Bauer MW (2017). Singularity: Scientific containers for mobility of compute. PLoS ONE 12(5): e0177459.</sup>  
<sup>**2.**  Koster, J. and S. Rahmann (2018). "Snakemake-a scalable bioinformatics workflow engine." Bioinformatics 34(20): 3600.</sup>  
