# ExaCA temperature example files
This repository contains supplementary temperature data files (the .txt files in the "Temperatures" subdirectory) for use with the ExaCA code (see https://github.com/LLNL/ExaCA). Within the ExaCA repository, there are 2 example files that use the external temperature data within this ExaCA-Data repository: examples/Inp_SimpleRaster.txt, which uses the file Temperatures/Master-Raster-150um.txt (a single layer of a raster pattern), and examples/Inp_AMBenchMultilayer.txt, which uses the files Temperatures/1CA-FOAM-fluidflow.txt and Temperatures/2CA-FOAM-fluidflow.txt (a four layer Additive Manufacturing-like problem that alternates an odd and an even layer scan pattern).
To run those example problems, first ensure that a copy of the main ExaCA repository is checked out, then change directory to the ExaCA/examples folder and clone this repository:

git clone https://github.com/LLNL/ExaCA-Data

When running the Inp_SimpleRaster.txt and Inp_AMBenchMultilayer.txt, the external temperature data is assumed to be located in examples/Temperatures, though by modifying the input files themselves, the path to the temperature data can be changed.

# Release

LLNL-CODE-821827
