# 20-DNPs-Tm
Here are the VASP-based training datasets, relevant scripts for generating atomistic potentials, and the resulting [DeepMD-kit v2.2.1]( https://github.com/deepmodeling/deepmd-kit/releases/tag/v2.2.1 ) trained potentials (DNPs).

We trained DNPs using the DeepMD-kit for 20 elements across the Periodic Table; these potentials have been extended/modified from the previous [datasets]( https://github.com/saidigroup/23-Single-Element-DNPs/tree/main ) to improve the modeling of melting behavior and the element's liquid phase.

Three randomly seeded DNPs were generated for each atomistic potential. Up to 14 iterations of adaptive learning refinement were applied to improve DNP simulation accuracy. The final iterations of these DNPs can be located in the "[DNPs]( https://github.com/saidigroup/20-DNPs-Tm/tree/main/DNPs )" directory.  Additionally, loss function output "lcurve.out", plot "lcurve.png", and the DeepMD-kit training file output "out.json" for the "ELEMENT-0.pb" DNP are included for each element.

The "[Training_Data]( https://github.com/saidigroup/20-DNPs-Tm/tree/main/Training%20Datasets )" directory contains all the training data used to fit the DNPs for each element. The VASP trajectories and the *.npy files are in these compressed files.

An example of the LAMMPS input script "[melt.in]( xxx )" and structure can be found in the two-phase coexistence directory "[TPC]( https://github.com/saidigroup/20-DNPs-Tm/tree/main/TPC )".  The VASP "[INCAR]( https://github.com/saidigroup/20-DNPs-Tm/blob/main/TPC/INCAR )" file, used to calculate each element's ground-state lattice's cohesive energy, can also be found here.   

The [VASP](https://github.com/saidigroup/23DNPs_and_me/blob/main/LAMMPS_VASP_Scripts%20for%20Calculations/Elastic_constants/INCAR_elastic) and [LAMMPS]( https://github.com/saidigroup/23-Single-Element-DNPs/tree/main/LAMMPS_VASP_Scripts%20for%20Calculations/Elastic_constants )  files used for validation of basic material property benchmarks are identical to what we previously used and can be found [here]( https://github.com/saidigroup/23-Single-Element-DNPs/tree/main/LAMMPS_VASP_Scripts%20for%20Calculations ).
