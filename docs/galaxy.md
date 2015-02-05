# Galaxy

## References
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

# Custom Genomes, Building indices

One of the hurdles for the common user is the need for (custom) genomes and indices for their preferred mapping tools.
There is the option of using custom genomes from the history and building indices from there, however this is not always
straight-forward and wasted effort and (computing) time, even more for genomes used frequently and from multiple users.

Therefore, Galaxy now offers the possibility for admins to upload genomes and build indices using data managers.
Further, new DBKeys can easily be generated (mm10, hg38).

### Pitfalls
UCSC annotation is prefered over Ensembl, as there are slight differences in strucure (e.g. chr1 vs 1). 
The data manager for building bwa indices fails with Ensembl genomes. Keep that in mind.

## From the toolshed

* data_manager_fetch_genome_dbkeys_all_fasta
* data_manager_bwa_index_builder
* data_manager_rnastar


