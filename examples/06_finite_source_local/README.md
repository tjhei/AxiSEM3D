# Example 06 - Finite_source_local
# =================================
# Models of the San Francisco Bay Area need to be downloaded from Zenodo & copied to the input folder
# Zenodo link: TBA 
# cd input
# sh genmesh.sh

# to generate source & surface observation locations (already done in the input folders)
ipython notebook input_setup.ipynb

# to run axisem on Archer2 (need to set necessary uppercase variables in submit.slurm)
cp axisem3d .
sbatch submit.slurm

# to plot results animation on the surface
ipython notebook post_processing.ipynb

# Example 00 — Global 1D (PREM)
# ==============================
# A global simulation using a 1D PREM (anisotropic) Earth model.
# Source: 2011 Virginia earthquake (Mw 5.8)
# Stations: GSN global network + USArray transportable array
# Period: 50 s

# The mesh has already been generated and is provided in input/.
# To regenerate it:
#   python -m salvus_mesh_lite.interface AxiSEM --basic.model prem_ani --basic.period 50 --output_file input/global_mesh__prem_ani__50s.e

# To run the simulation (~4 minutes on 4 cores):
#   cp path/to/axisem3d .
#   mpirun -np 4 ./axisem3d input/

# Output will be written to output/ inside this folder.

# Use post_processing.ipynb to visualize seismograms and USArray animations.
# This notebook is set up for the 1D simulation only.