# CμMD Simulations of NaCl(aq) at Graphite Using GROMACS and PLUMED (v2)

__Please consider citing Perego et al. J Chem Phys 142, 144113 (2015)__
__Please consider citing Finney et al.__

The repository hosts the input and output files to run simulations of the kind described by Finney et al. using [GROMACS](https://www.gromacs.org) and [PLUMED 2](https://www.plumed.org).

All input files and example output files from a short MD run are included. The force field parameter files are contained in `./graph-NaCl-pol.ff` and the files to perform structural analyses using the Plumed driver are in `./plumed-drivier-analysis`

1. To run the simulation with Gromacs and Plumed:
`gmx grompp -f job.mdp -c initial.gro -p topol.top -o cmumd`
`gmx mdrun -deffnm cmumd -cpi md.cpt -plumed plumed.dat`

2. To perform the analysis in `./plumed-drivier-analysis`:
`plumed driver --mf_xtc ../cmumd.xtc --plumed clusters.plmd --timestep 0.002 --trajectory-stride 200 > log.clusters.plmd`