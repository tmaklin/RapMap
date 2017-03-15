<<<<<<< HEAD
#Building RapMap_mod
Make sure your C++ compiler supports C++11. Enter the RapMap directory, and run the commands:

```
mkdir build && cd build
cmake ..
make
make install
```

#Description
Fork of [RapMap](https://github.com/COMBINE-lab/RapMap) with the purpose of outputting pseudoalignment profiles instead of .sam files for further analysis.
=======
Fork of [RapMap](https://github.com/COMBINE-lab/RapMap) for the purpose of adding support to output pseudoalignment profiles instead of the usual .sam files output by the original RapMap. Pseudoalignment profiles contain the observed counts for each profile and a string representation of the corresponding mappings.

#Usage
After obtaining the pseudoindex of a transcriptome, specifying the new program flag '-b' in combination with '-n' (no .sam output) and an output file, and performing the mapping with the command

> rapmap pseudomap -i ref_index -1 <(gunzip -c r1.fq.gz) -2 <(gunzip -c r2.fq.gz) -t 8 -b -n -o mapped_reads.bitfields

results in a 'mapped_reads.bitfields' file which contains the .sam format header and the pseudoalignments.

#.bitfields format
The .bitfields file format consists of a header part, containing the same information as a .sam file header would, followed by lines containing the number of times a pseudoalignment profile occurred and a string representation of the observed profile. For example if a two reads both aligned to references 1 and 5 with a total of 6 references in the index, the string representation of the profile would be "100010" and whole line as follows

> 2 100010
>>>>>>> 51d5c1d88c3820e55a0ed0d81c17bf91e3fb7707
