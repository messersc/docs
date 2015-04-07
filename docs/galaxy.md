# Galaxy

## Example
An extensive Galaxy tutorial for RNA-Seq can be found here

http://wiki.bits.vib.be/index.php/RNA-Seq_analysis_for_differential_expression#Galaxy

## Galaxy challenges

* building indices for mappers
* upload of large files (use FTP!)
	* symlinking is probably enough, but right now only admins can do this

# Simple Workflow - NY Genome Center

* STAR
* featurecount
* DESeq2

## Extended

* options for adapter removal and quality trimming
* edgeR, limma + voom

## Legacy

* provide Tophat2 and BWA as fall-back mappers

## Custom Genomes, Building indices

One of the hurdles for the common user is the need for (custom) genomes and indices for their preferred mapping tools.
There is the option of using custom genomes from the history and building indices from there, however this is not always
straight-forward and wasted effort and (computing) time, even more for genomes used frequently and from multiple users.

Therefore, Galaxy now offers the possibility for admins to upload genomes and build indices using data managers.
Further, new DBKeys can easily be generated (mm10, hg38).

Another possibility is to clone the public Galaxy instance, which pulls all the data sources and tools so you don't have to start from scratch.

### Pitfalls
UCSC annotation is prefered over Ensembl, as there are slight differences in strucure (e.g. chr1 vs 1). 
The data manager for building bwa indices fails with Ensembl genomes. Keep that in mind.

## From the toolshed

* data_manager_fetch_genome_dbkeys_all_fasta
* data_manager_bwa_index_builder
* data_manager_rnastar

## Workflows: Dataset collections

To facilitate the construction of more complex workflows, dataset collections were introducted.
Those include dataset pairs, list and paired lists. Obviously, this can be especially useful for a workflow
processing paired-end reads with an a-priori unknown number of replicates.

However, it is crucial that all the tools in the workflow can handle dataset collections!

## Schedulung

Before stalling your development machine with 4 concurrent BWA jobs, check out the manual at https://wiki.galaxyproject.org/Admin/Config/Jobs to limit the number of threads and RAM your Galaxy instance gets to use.
