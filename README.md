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
