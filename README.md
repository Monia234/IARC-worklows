# IARC bioinformatics nextflow pipelines (updated on 08/08/2018)

## IARC pipelines list (mostly nextflow pipelines -nf)

### Raw NGS data processing
| Name      | Description     |	Tools used	|
|-----------|-----------------|-----------------|
| [alignment-nf](https://github.com/IARCbioinfo/alignment-nf)    | Performs BAM realignment or fastq alignment, with/without local indel realignment and base quality score recalibration |[bwa](https://github.com/lh3/bwa), [samblaster](https://github.com/GregoryFaust/samblaster), [sambamba](https://github.com/lomereiter/sambamba) & in option: [samtools](http://samtools.sourceforge.net/), [AdapterRemoval](https://github.com/MikkelSchubert/adapterremoval), [GATK](www.broadinstitute.org/gatk/download), [k8 javascript execution shell](https://sourceforge.net/projects/bio-bwa/files/bwakit/), [bwa-postalt.js](https://github.com/lh3/bwa/tree/master/bwakit) |
| [gatk4-DataPreProcessing-nf](https://github.com/IARCbioinfo/gatk4-DataPreProcessing-nf)   | Performs bwa alignment and pre-processing (mark duplicates and recalibration) following GATK4 best practices - compatible with hg38 |[bwa](https://github.com/lh3/bwa), [picard](https://broadinstitute.github.io/picard/), [GATK4](https://software.broadinstitute.org/gatk/download/), sambamba, [qualimap](http://qualimap.bioinfo.cipf.es/)|
| [GATK-Alignment-nf](https://github.com/IARCbioinfo/GATK-Alignment-nf)   | Performs bwa alignment and pre-processing (realignment and recalibration) following first version of GATK best practices (less performant than [alignment-nf](https://github.com/IARCbioinfo/alignment-nf) ) |[bwa](https://github.com/lh3/bwa), picard, [GATK](www.broadinstitute.org/gatk/download)|
| [BQSR-nf](https://github.com/IARCbioinfo/BQSR-nf)   | Performs base quality score recalibration of bam files using GATK |[samtools](http://samtools.sourceforge.net/), [samblaster](https://github.com/GregoryFaust/samblaster), [sambamba](https://github.com/lomereiter/sambamba), [GATK](www.broadinstitute.org/gatk/download)|
| [abra-nf](https://github.com/IARCbioinfo/abra-nf)   | Runs ABRA (Assembly Based ReAligner) |[ABRA](https://github.com/mozack/abra), [bedtools](http://bedtools.readthedocs.io/en/latest/), [bwa](http://bio-bwa.sourceforge.net), [sambamba](http://lomereiter.github.io/sambamba/), [samtools](http://www.htslib.org/) |
||||
| [marathon-wgs](https://github.com/IARCbioinfo/marathon-wgs)   | Studies intratumor heterogeneity with Canopy|[bwa](https://github.com/lh3/bwa), [platypus](https://github.com/andyrimmer/Platypus), [strelka2](https://github.com/Illumina/strelka), [vt](https://github.com/atks/vt), [annovar](http://annovar.openbioinformatics.org/en/latest/), R scripts, [Falcon](https://cran.r-project.org/web/packages/falcon/index.html), [Canopy](https://github.com/yuchaojiang/Canopy)|

### RNA Seq
| Name      | Description     |	Tools used	|
|-----------|-----------------|-----------------|
| [RNAseq-nf](https://github.com/IARCbioinfo/RNAseq-nf)   | Performs RNAseq mapping, quality control, and reads counting - See also [RNAseq_analysis_scripts](https://github.com/IARCbioinfo/RNAseq_analysis_scripts) for post-processing  |[fastqc](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/INSTALL.txt), [cutadapt](http://cutadapt.readthedocs.io/en/stable/installation.html), Python version > 2.7, [trim_galore](https://github.com/FelixKrueger/TrimGalore), [RESeQC](http://rseqc.sourceforge.net/), [multiQC](http://multiqc.info/docs/), [STAR](https://github.com/alexdobin/STAR/blob/master/doc/STARmanual.pdf), [htseq](http://www-huber.embl.de/HTSeq/doc/install.html#install) & in option: [hisat2](https://ccb.jhu.edu/software/hisat2/index.shtml), [GATK](www.broadinstitute.org/gatk/download), [samtools](http://samtools.sourceforge.net/)|
| [RNAseq-transcript-nf](https://github.com/IARCbioinfo/RNAseq-transcript-nf)   | Performs transcript identification and quantification from a series of BAM files |[StringTie](https://github.com/gpertea/stringtie)|

### QC
| Name      | Description     |	Tools used	|
|-----------|-----------------|-----------------|
| [conpair-nf](https://github.com/IARCbioinfo/conpair-nf)   | Runs conpair (concordance and contamination estimator) |[conpair](https://github.com/nygenome/Conpair), [Python 2.7](www.python.org), [numpy 1.7.0 or higher](www.numpy.org), [scipy 0.14.0 or higher](www.scipy.org), [GATK 2.3 or higher](www.broadinstitute.org/gatk/download)|
| [damage-estimator-nf](https://github.com/IARCbioinfo/damage-estimator-nf)   | Runs "Damage Estimator" |[Damage Estimator](https://github.com/Ettwiller/Damage-estimator), [samtools](http://samtools.sourceforge.net/), [R](https://www.r-project.org) with GGPLOT2 package|
| [QC3](https://github.com/IARCbioinfo/QC3)   | Runs QC on DNA seq data (raw data, aligned data and variant calls - forked from [slzhao](https://github.com/slzhao/QC3) |[samtools](http://samtools.sourceforge.net/)|
| [mpileup-nf](https://github.com/IARCbioinfo/mpileup-nf)   | Computes bam coverage with samtools mpileup (bed parallelization) |[samtools](http://samtools.sourceforge.net/),[annovar](http://annovar.openbioinformatics.org/en/latest/)|
| [bamsurgeon-nf](https://github.com/IARCbioinfo/bamsurgeon-nf)   | Runs bamsurgeon (tool to add mutations to bam files) with step of variant simulation |[Python 2.7](www.python.org), [bamsurgeon](http://github.com/adamewing/bamsurgeon/), [R software](https://www.r-project.org/) (tested with R version 3.2.3)|


### Variant calling
| Name      | Description     |	Tools used	|
|-----------|-----------------|-----------------|
| [needlestack](https://github.com/IARCbioinfo/needlestack)   | Performs multi-sample somatic variant calling |[perl](https://www.perl.org),  [bedtools](http://bedtools.readthedocs.org/en/latest/), [samtools](http://samtools.sourceforge.net/) and Rscript |
| [target-seq](https://github.com/IARCbioinfo/target-seq)   | Whole pipeline to perform multi-sample somatic variant calling using Needlestack on targeted sequencing data|[abra2](https://github.com/IARCbioinfo/abra-nf),[QC3](https://github.com/slzhao/QC3) ,[needlestack](https://github.com/IARCbioinfo/needlestack), [annovar](http://annovar.openbioinformatics.org/en/latest/) and R script |
| [strelka2-nf](https://github.com/IARCbioinfo/strelka2-nf)   | Runs Strelka 2 (germline and somatic variant caller)|[Strelka2](https://github.com/Illumina/strelka)|
| [strelka-nf](https://github.com/IARCbioinfo/strelka-nf)   | Runs Strelka (germline and somatic variant caller)|[Strelka](https://sites.google.com/site/strelkasomaticvariantcaller/home/strelka-workflow-installation)|
| [mutect-nf](https://github.com/IARCbioinfo/mutect-nf)   | Runs Mutect on tumor-matched normal bam pairs |[Mutect](https://github.com/broadinstitute/mutect) and its dependencies (Java 1.7 and Maven 3.0+), [bedtools](http://bedtools.readthedocs.io/en/latest/content/installation.html)|
| [gatk4-HaplotypeCaller-nf](https://github.com/IARCbioinfo/gatk4-HaplotypeCaller-nf)   | Runs variant calling in GVCF mode on bam files following GATK best practices|[GATK](https://software.broadinstitute.org/gatk/download/)|
| [gatk4-GenotypeGVCFs-nf](https://github.com/IARCbioinfo/gatk4-GenotypeGVCFs-nf)   | Runs joint genotyping on gvcf files following GATK best practices|[GATK](https://software.broadinstitute.org/gatk/download/)|
| [GVCF_pipeline-nf](https://github.com/IARCbioinfo/GVCF_pipeline-nf)   | Performs bam realignment and recalibration + variant calling in GVCF mode following GATK best practices|[bwa](https://github.com/lh3/bwa), [samblaster](https://github.com/GregoryFaust/samblaster), [sambamba](https://github.com/lomereiter/sambamba), [GATK](https://software.broadinstitute.org/gatk/download/)|
| [GATK-Calling-GVCF-nf](https://github.com/IARCbioinfo/GATK-Calling-GVCF-nf) | Runs variant calling in GVCF mode on bam files, joint genotyping and variant recalibration (SNPs and indels) following GATK best practices - still in development!!|[GATK](www.broadinstitute.org/gatk/download)|
| [platypus-nf](https://github.com/IARCbioinfo/platypus-nf)   | Runs Platypus (germline variant caller) |[Platypus](https://github.com/andyrimmer/Platypus)|
| [TCGA_platypus-nf](https://github.com/IARCbioinfo/TCGA_platypus-nf)   | Converts TCGA Platypus vcf in format for annotation with annovar |[vt](https://github.com/atks/vt),[VCFTools](https://github.com/vcftools/vcftools)|
| [vt-nf](https://github.com/IARCbioinfo/vt-nf)   | Decomposes and normalizes variant calls (vcf files) |[vt](https://github.com/atks/vt), samtools/htslib|
| [TCGA_germline-nf](https://github.com/IARCbioinfo/TCGA_germline-nf) | Extract germline variants from TCGA data for annotation with annovar (vcf files) |R script|
| [table_annovar-nf](https://github.com/IARCbioinfo/table_annovar-nf) | Annotate variants with annovar (vcf files) |[annovar](http://annovar.openbioinformatics.org/en/latest/)|
||||
| [MutSpec](https://github.com/IARCbioinfo/mutspec)   | Suite of tools for analyzing and interpreting mutational signatures |[annovar](http://annovar.openbioinformatics.org/en/latest/)|
||||
| [CODEX-nf](https://github.com/IARCbioinfo/CODEX-nf)   | Performs copy number variant calling from whole exome sequencing data using CODEX |[R](https://www.r-project.org) with package Codex, Rscript |


### Other tools/pipelines
| Name      | Description     |	Tools used	|
|-----------|-----------------|-----------------|
| [nextflow-course-2018](https://github.com/IARCbioinfo/nextflow-course-2018)   | Nextflow course |NA|
| [SBG-CGC_course2018](https://github.com/IARCbioinfo/SBG-CGC_course2018)   | Analyzing TCGA data in SBG-CGC |NA|
| [template-nf](https://github.com/IARCbioinfo/template-nf)   | Empty template for nextflow pipelines |NA|
| [LSF-Tricks](https://github.com/IARCbioinfo/LSF-tricks)   | Tips and tricks for LSF HPC scheduler |NA|
||||
| [scanMyWorkDir](https://github.com/IARCbioinfo/scanMyWorkDir)   | Non-destructive and informative scan of a nextflow work folder |NA|
| [BAM-tricks](https://github.com/IARCbioinfo/bametrics-nf)   | Tips and tricks for BAM files |[samtools](http://samtools.sourceforge.net/), freebayes, [bedtools](http://bedtools.readthedocs.io/en/latest/), biobambam2, [Picard](http://broadinstitute.github.io/picard/), [rbamtools](https://cran.r-project.org/web/packages/rbamtools/index.html)|
| [addreplacerg-nf](https://github.com/IARCbioinfo/addreplacerg-nf)   | Adds and replaces read group tags in BAM files |[samtools](http://samtools.sourceforge.net/)|
| [bametrics-nf](https://github.com/IARCbioinfo/BAM-tricks)   | Computes average metrics from reads that overlap a given set of positions |NA|
| [Gviz_multiAlignments](https://github.com/IARCbioinfo/Gviz_multiAlignments)   | Generates multiple BAM alignments views using Gviz bioconductor package|[Gviz](https://bioconductor.org/packages/release/bioc/html/Gviz.html)||
| [nf_coverage_demo](https://github.com/IARCbioinfo/nf_coverage_demo)   | Plots mean coverage over a series of BAM files |[bedtools](http://bedtools.readthedocs.io/en/latest/), R script|
| [VCF-tricks](https://github.com/IARCbioinfo/VCF-tricks) | Tips and tricks for VCF files |[samtools](http://samtools.sourceforge.net/),[bcftools](https://github.com/samtools/bcftools), [vcflib](https://github.com/vcflib/vcflib), [vcftools](https://github.com/vcftools/vcftools), R scripts|
| [LiftOver-nf](https://github.com/IARCbioinfo/LiftOver-nf) | Converts BED/VCF between hg19 and hg38 |[picard](https://broadinstitute.github.io/picard/)|
| [integration_analysis_scripts](https://github.com/IARCbioinfo/integration_analysis_scripts)   | Performs unsupervised analyses (clustering) from transformed expression data (e.g., log fpkm) and methylation beta values |[R software](https://www.r-project.org/) + iClusterPlus, gplots and lattice R packages|
| [mpileup2readcounts](https://github.com/IARCbioinfo/mpileup2readcounts)| Get the readcounts at a locus by piping samtools mpileup output - forked from [gatoravi](https://github.com/gatoravi/mpileup2readcounts) |[samtools](http://samtools.sourceforge.net/)|
| [R-tricks](https://github.com/IARCbioinfo/R-tricks)| Tips and tricks for R |NA|
| [awesomeTCGA](https://github.com/IARCbioinfo/awesome-TCGA) | Curated list of resources to access TCGA data |NA|
| [EGA-tricks](https://github.com/IARCbioinfo/EGA-tricks)| Tips and tricks to use the European Genome-Phenome Archive from the European Bioinformatics Institute |[EGA client](https://www.ebi.ac.uk/ega/sites/ebi.ac.uk.ega/files/documents/EGA_download_client_2.2.2.zip)|
| [GDC-tricks](https://github.com/IARCbioinfo/GDC-tricks)| Tips and tricks to use the [GDC data portal](https://gdc-portal.nci.nih.gov/) |NA|

### Coming soon...
| Name      | Description     |	Tools used	|
|-----------|-----------------|-----------------|
| [methylkey](https://github.com/IARCbioinfo/methylkey)   |  ||
| [variantflag](https://github.com/IARCbioinfo/variantflag)   | Merge and annotate variants from different callers ||

## Installation 

### Nextflow

1. Install [java](https://java.com/download/) JRE if you don't already have it (7 or higher).

2. Install [nextflow](http://www.nextflow.io/).

	```bash
	curl -fsSL get.nextflow.io | bash
	```
	And move it to a location in your `$PATH` (`/usr/local/bin` for example here):
	```bash
	sudo mv nextflow /usr/local/bin
	```

### Docker

To avoid having to installing all dependencies each time you use a pipeline, you can instead install [docker](https://www.docker.com) and let nextflow dealing with it. Installing docker is system specific (but quite easy in most cases), follow  [docker documentation](https://docs.docker.com/installation/) (docker CE is sufficient). Also follow the post-installation step to manage Docker as a non-root user ([here](https://docs.docker.com/engine/installation/linux/linux-postinstall/) for Linux), otherwise you will need to change the `sudo` option in nextflow `docker` config scope as described in the nextflow documentation [here](https://www.nextflow.io/docs/latest/config.html#scope-docker).

To run nextflow pipeline with Docker, simply add the `-with-docker` option in the `nextflow run` command.

### Configuration file

## Usage

### Pipelines updates

You can update the nextflow sofware and the pipeline itself simply using:
```bash
nextflow -self-update
nextflow pull iarcbioinfo/pipeline_name
```

You can also automatically update the pipeline when you run it by adding the option `-latest` in the `nextflow run` command. Doing so you will always run the latest version from Github.

### Display help

```bash
nextflow run iarcbioinfo/pipeline_name --help
```

