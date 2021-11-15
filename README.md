# Drosophila - Riboviz work:

## 1 Raw data - not uploaded as large.

From Flybase:
* Dmel GFF 6.35
* Dmel genome fasta 6.35
* tRNA fasta 6.35

From Ribogalaxy:
* rRNA fasta

- Converting fly genome - script to make ORFeome GFF and fasta from flybase reference GFF and fasta. Outputs in [Dmel_genomes](Riboviz_work/2_Processed_data/Dmel_genomes/).
- Filtering fly genome - script to filter ORFeome GFF and fasta to one CDS per gene for testing. Outputs in [Dmel_genomes](Riboviz_work/2_Processed_data/Dmel_genomes/).
- Test mouse genome - successful test on mouse gencode reference genome.
- Test yeast genome - as yet unsuccessful test on yeast reference gemone - needs fasta header editing step, and genome padding. Likely to be needed for any non-standard annotations.
- tmp extended 3UTR and 5UTR - R objects saved from Dmel testing to save time.
