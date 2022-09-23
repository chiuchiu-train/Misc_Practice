# Unix Challenge #1

## Code:

**Command #1**: Extract the markers via rsID and sort by chromosome number (string) and position (numerical), \
prioritizing chromosome number.
```
zgrep -f markers.txt /share/carvajal-archive/REFERENCE_DATA/gnomAD/3.0.0/gnomad.genomes.r3.0.sites.vcf.bgz |
sort -k 1 -k2n > gnomad_subset_noheader.vcf
```
* Start time 11:47 am

**Command #2*: Extract the header, concatenate it with `gnomad_subset_noheader.vcf`, and compress.
```
zgrep "##" /share/carvajal-archive/REFERENCE_DATA/gnomAD/3.0.0/gnomad.genomes.r3.0.sites.vcf.bgz |
cat - gnomad_subset_noheader.vcf |
gzip > gnomad_subset_challenge.vcf.gz
```

## Attempt 2
```
cut -f 1,2,3 /share/carvajal-archive/REFERENCE_DATA/gnomAD/3.0.0/gnomad.genomes.r3.0.sites.vcf.bgz |
grep -f markers.txt > 1.identifiers.txt
```
* Runtime ~1 hour
* cut started at 1:03 pm
