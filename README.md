Note, this version seems to break normal RapMap function.

# Building RapMap_mod
Make sure your C++ compiler supports C++11. Enter the RapMap directory, and run the commands:

```
mkdir build && cd build
cmake ..
make
make install
```

This creates the rapmap executable in bin/ directory.

# Description
Fork of [RapMap](https://github.com/COMBINE-lab/RapMap) for the purpose of adding support to output pseudoalignment profiles instead of the usual .sam files output by the original RapMap. Pseudoalignment profiles contain the observed counts for each profile and a string representation of the corresponding mappings.

# Usage

Index a transcriptome called "references.fasta":
> rapmap pseudoindex -i ref_index -t references.fasta

Map some paired end reads:
> rapmap pseudomap -i ref_index -1 reads_1.fq.gz -2 reads_2.fq.gz -t 8 -b -n -o mapped_reads.bitfields

Map some gzipped paired end reads:
> rapmap pseudomap -i ref_index -1 <(gunzip -c r1.fq.gz) -2 <(gunzip -c r2.fq.gz) -t 8 -b -n -o mapped_reads.bitfields

results in a 'mapped_reads.bitfields' file which contains the .sam format header and the pseudoalignments.
