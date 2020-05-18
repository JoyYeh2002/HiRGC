# HiRGC

A high performance referential genome compression algorithm (termed HiRGC)

## Correction of Example 1
There is typos in Example 1. We correct it in the following.
<img src="https://sites.google.com/site/yyuanshengliu/home/correction/example1-hirgc.png">

#### Performance
We present a high-performance referential genome compression algorithm named HiRGC. It is based on a 2-bit encoding scheme and an advanced greedy-matching search on a hash table. We compare the performance of HiRGC with four state-of-the-art compression methods on a benchmark data set of eight human genomes. HiRGC takes less than 30 minutes to compress about 21 gigabytes of each set of the seven target genomes into 96 to 260 megabytes, achieving compression ratios of 217 to 82 times. This performance is at least 1.9 times better than the best competing algorithm on its best case. Our compression speed is also at least 2.9 times faster. HiRGC is stable and robust to deal with different reference genomes. In contrast, the competing methods’ performance varies widely on different reference genomes. More experiments on 100 human genomes from the 1000 Genome Project and on genomes of several other species again demonstrate that HiRGC’s performance is consistently excellent.

## Compile
	make hirgc
	make de_hirgc

## Compress
The following three different commands:

    （1） ./hirgc -m file -r YH_chr1.fa -t HG18_chr1.fa
    （2） ./hirgc -m genome -r YH -t HG18 -n chr_name.txt/default
    （3） ./hirgc -m set -r YH -t genome_set.txt -n chr_name.txt/default


* -m is the mode that the user want to used;
* -r is the reference (a FASTA file or a genome folder);
* -t is the target (a FASTA file or a genome folder or a file contains a list of genome folder);
* -n is a file containing name of chromosomes or a string "default".

---
**Some other explaination**<br />

- the mode *file* is to comrpess chromosomes; *genome* is to comoress a genome; *set* is to compress genome set.
- The first command compress a chromosome *HG18_chr1.fa* and the reference chromosome is *YH_chr1.fa*. The compressed is *HG18_chr1.fa_ref_YH_chr1.fa.7z*.
- The second compress a genome *HG18* contain some chromosomes and the reference genome is *YH*. The name of chromosomes can be given in the file *chr_name.txt* or set as default. The compressed file is *HG18_ref_YH.7z*.
- The third compress a genome set and the reference genome is *YH*. The list of genomes is given in file *genome_set.txt*. The name of chromosomes can be given in the file *chr_name.txt* or can be set as default.
- The default name of chromosomes is [*chr1.fa, chr2.fa, chr3.fa, chr4.fa, chr5.fa, chr6.fa, chr7.fa, chr8.fa, chr9.fa, chr10.fa, chr11.fa, chr12.fa, chr13.fa, chr14.fa, chr15.fa, chr16.fa, chr17.fa, chr18.fa, chr19.fa, chr20.fa, chr21.fa, chr22.fa, chrX.fa, chrY.fa*]

## Decompress

    ./de_hirgc -m file -r YH_chr1.fa -t HG18_chr1.fa_ref_YH_chr1.fa.7z
    ./de_hirgc -m genome -r YH -t HG18_ref_YH.7z -n chr_name.txt/default
    ./de_hirgc -m set -r YH -t de_genome_set.txt -n chr_name.txt/default

- the first command decompress a compressed chromosome file *xxx.7z* to *dec_xxx*.
- the second command decomperss a  compressed genome folder *yyy.7z* to *dec_yyy*.
- the parameter *-n* is identical to the compression procedure.

## Status
Published in *Bioinformatics* DOI: https://doi.org/10.1093/bioinformatics/btx412.

## Citation
Yuansheng Liu, Hui Peng, Limsoon Wong, Jinyan Li; High-speed and high-ratio referential genome compression, Bioinformatics, btx412, 2017, https://doi.org/10.1093/bioinformatics/btx412

### Contacts
If any bugs during you run our code, please email to <yyuanshengliu@gmail.com>

