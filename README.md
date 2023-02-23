# Lei_Lab_TK_43

#### A bed file containing the annotation of mm39 was generated from a gff3 file downloaded from ENCODE using the following shell command line:
```
gunzip -c gencode.vM32.annotation.gff3.gz | \
	grep '\tgene\t' | \
	cut -f 1,4,5,7,9 | \
	perl -ne 'chomp; @x=split /\t/; $type=$1 if m/gene_type=(\S*?);/; print "$x[0]\t$x[1]\t$x[2]\t$x[3]\t$type\n"' \
	> gencode.vM32.annotation.gff3.bed
```
