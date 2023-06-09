# ExaCA temperature example files
This repository contains supplementary temperature data files (the .txt files in the "Temperatures" subdirectory) for use with the ExaCA code (see https://github.com/LLNL/ExaCA). Within the ExaCA repository, there are 2 example files that use the external temperature data within this ExaCA-Data repository: examples/Inp_SingleLine.json, which uses the file Temperatures/Line.txt (a single line from a laser scan over a substrate), and examples/Inp_TwoLineTwoLayer.json, which uses the file Temperatures/TwoLine.txt (segments from two overlapping line scan melt pools, repeated for two layers of a build).
To run those example problems, first ensure that a copy of the main ExaCA repository is checked out, then change directory to the ExaCA/examples folder and clone this repository:

git clone https://github.com/LLNL/ExaCA-Data

When running the Inp_SingleLine.json and Inp_TwoLineTwoLayer.json example problems, the external temperature data is assumed to be located in examples/Temperatures, though by modifying the input files themselves, the path to the temperature data can be changed. 

The additional temperature example files 1CA-FOAM-fluidflow.txt, 2CA-FOAM-fluidflow.txt, and Master-Raster-150um.txt can be used with the example problems Inp_SimpleRaster.json and Inp_AMBenchMultilayer.json from ExaCA version 1.2 and older. These are simplfied data sets that only include the final time that each cell in the simulation undergoes solidification, and no physically meaningful melting data is given (0s are in the "tm" column of these files). These example problems and data sets are no longer current beyond ExaCA version 1.2.

# ExaCA substrate example files
The substrate data files provided within the https://github.com/LLNL/ExaCA repository consist of various representations of 10,000 random cubic grain orientations (see the README file provided in the examples subdirecory of the ExaCA repository for more details) and are sufficient for running the example problems provided. However, simulations containing more than 10,000 grains using said substrate files will reuse orientations; to mitigate the effect of having multiple grains share a single orientation, the supplementary substrate files in this repository contain 1,000,000 random cubic orientations. Running ExaCA with this larger set of grain orientations yields a negligible increase in runtime (and for simulations tested to date, a negligible change in predicted texture), but may improve ExaConstit property prediction for microstructures containing large numbers of grains with the reduced probability of multiple grains being assigned the same orientation.

# MTEX example input files
Running the directional solidification example problem and analysis executable using https://github.com/LLNL/ExaCA creates three MTEX input files that should resemble those in the `MTEX_Input` directory. These files can be analyzed using Matlab and the MTEX toolbox (https://mtex-toolbox.github.io/) along with the appropriate scripts in the ExaCA repository's `utilities/MTEX` directory to analyze the texture of the example regions (see `analysis/README.md` in the ExaCA repository for more details).

* `TestProblemDirS_XY198_PoleFigureData.txt` consists of the Euler angles and frequencies for the grains in the XY cross-section at Z = 198 (just below the top surface of the directional solidification problem). This can be used to plot pole figures and inverse pole figures using `utilities/MTEX/PlotPoleFigure.m` in the ExaCA repository
* `TestProblemDirS_XY198_IPFCrossSectionData.txt` consists of the Euler angles associated with each point in the XY cross-section at Z = 198 (just below the top surface of the directional solidification problem)
* `TestProblemDirS_XZ100_IPFCrossSectionData.txt` consists of the Euler angles associated with each point in the XZ cross-section at Y = 100 (the center plane of the directional solidification problem, slicing parallel to the thermal gradient direction)

# Release

LLNL-CODE-821827
