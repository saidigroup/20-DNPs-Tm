# 20-DNPs-Tm
Here are the VASP-base training datasets, relevant scripts for generating atomistic potentials, and the resulting [DeepMD-kit]( https://github.com/deepmodeling/deepmd-kit/releases/tag/v2.2.1 ) trained potentials (DNPs).

We trained DNPs using the DeepMD-kit for 20 elements across the Periodic Table; these potentials have been extended/modified from the previous [datasets]( https://github.com/saidigroup/23-Single-Element-DNPs/tree/main ) to improve the modeling of melting behavior and the element's liquid phase.

Three randomly seeded DNPs were generated for each potential. Up to three iterations of adaptive learning refinement were applied to reduce standard deviations among these randomly seeded DNPs. The final iterations of these DNPs can be located in the "DNPs" directory.

The "Training_Data" directory contained all the training data used to fit the DNPs for each element. The VASP trajectories and the *.npy files are in these compressed files.

The structures used to validate these DNPs can be found in each element's "Validation" directories. The "melt. in" is the LAMMPS script for generating relaxed structures, calculating the energies of these structures, and reporting the cell dimensions. The heat.in LAMMPS script was used to heat 14x14x28 supercells from 0 to the melting temperature for each element to demonstrate the DNP's stability for the solid phase. The INCAR file is the VASP input script we used to generate the corresponding VASP reference data and compare it with the LAMMPs-DNP results. Lastly, the LAMMPS and VASP scripts for elastic calculations are supplied.

We utilized the LAVA code for calculating the DNP surface energy for these elements using the DNPs and LAMMPs due to the code's ease of use for this application (there are many other interesting tools in this package as well for LAMMPS and VASP validations of atomistic potentials).

The data used to produce figures are located in the "Figures" directories along with the Python scripts to generate these plots.
