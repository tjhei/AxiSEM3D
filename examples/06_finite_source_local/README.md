# Example 06 - Finite_source_local
# =================================
# Models of the San Francisco Bay Area need to be downloaded from Zenodo & copied to the input folder
# Zenodo link: TBA 
# cd input
# sh genmesh.sh
# Before you run the script genmesh.sh, Salvus_Mesh_Lite module is needed
# pip install https://gitlab.com/Salvus/SalvusMeshLite/-/archive/master/SalvusMeshLite-master.zip
# pip install "scipy<1.14" "numpy<2.0"
#
# AxiSEMCartesian_sfba_m500_2s.e file is made

# To generate source & surface observation locations (already done in the input folders)
# ipython notebook input_setup.ipynb

# To run axisem on Archer2 (need to set necessary uppercase variables in submit.slurm)
# cp axisem3d .
# sbatch submit.slurm
# In the local environment, you need to run AxiSEM3D with mpirun instead of sbatch
# mpirun -np 4 ./axisem3d --input input

# To plot results animation on the surface
# ipython notebook post_processing.ipynb