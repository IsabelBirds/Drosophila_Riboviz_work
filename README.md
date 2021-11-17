# Drosophila Riboviz work

## Raw data

(Not uploaded)

From Flybase:
- [Dmel all GFF 6.35](http://ftp.flybase.net/releases/FB2020_04/dmel_r6.35/gff/)
- [Dmel all GTF 6.35](http://ftp.flybase.net/releases/FB2020_04/dmel_r6.35/gtf/)
- [Dmel genome fasta 6.35](http://ftp.flybase.net/releases/FB2020_04/dmel_r6.35/fasta/)
- [tRNA fasta 6.35](http://ftp.flybase.net/releases/FB2020_04/dmel_r6.35/fasta/)

From Ribogalaxy:
- [rRNA fasta](https://ribogalaxy.ucc.ie/library/index)

Sequencing data: 
- [Small polysome footprints RPF sample](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSM1477470)

## Processed data
- subsampled fastq (```head -400000 SRR1548656.fastq > SRR1548656_subsample.fastq```)
- Fasta and gff - formatted for Riboviz
- Filtered fasta and gff - one CDS per gene
## src

- Converting fly genome - script to make ORFeome GFF and fasta from flybase reference GFF and fasta.
- Filtering fly genome - script to filter ORFeome GFF and fasta to one (longest) CDS per gene.
- Outputs in Processed data
- *Needs update*. Test mouse genome - successful test on mouse gencode reference genome.
- *Needs update*. Test yeast genome - as yet unsuccessful test on yeast reference genome - needs fasta header editing step, and genome padding. Likely to be needed for any non-standard annotations.

## Riboviz test

Test running converted filtered fasta and gff on Riboviz.
Includes params file, output from checks, etc.

Check gff: ```python -m riboviz.tools.check_fasta_gff -f /Users/isabelbirds/Documents/GitHub/Drosophila_Riboviz_work/2_Processed_data/Dmel/Dmel_filtered.fasta -g /Users/isabelbirds/Documents/GitHub/Drosophila_Riboviz_work/2_Processed_data/Dmel/Dmel_filtered.gff3 -o /Users/isabelbirds/Documents/GitHub/Drosophila_Riboviz_work/4_Riboviz_test/Dmel_filtered.issues.tsv --use-feature-name -v```

Validate config: ```nextflow run /Users/isabelbirds/Documents/Programs/Riboviz/riboviz/prep_riboviz.nf -params-file Aspden_2014_RPF_config.yaml --validate_only```

Run riboviz: ```nextflow run /Users/isabelbirds/Documents/Programs/Riboviz/riboviz/prep_riboviz.nf -ansi-log false -params-file Aspden_2014_RPF_config.yaml```