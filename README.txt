Si-C bond parameterization for CHARMM

The bond between the silicon of the head group and the first carbon of the alkyl chain of an alkylsilane (Si-C1) has
no CHARMM parameters. This folder gives its length and force constant. The model molecule is octylsilanetriol,
Si(OH)3-C8H17, neutral and in the gas phase, at the HF/6-31G* level with ORCA. The length comes from the relaxation of
the molecule. The force constant is calculated in two ways: reduced-mass scaling of the CHARMM C-C bond, and relaxed
scans of the Si-C1 and C4-C5 bonds, calibrated on the CHARMM C-C bond.

Files
Si-C_bond_parameterization_for_CHARMM.ipynb   the calculation, from the ORCA files to the length and force constant
figures/                                       the figures of the notebook, as PNG and PDF files
ORCA_results/relaxation/                       relaxation and vibrational frequencies of the molecule (its own README.txt)
ORCA_results/bond_scans/Si-C/                  relaxed scan of the Si-C1 bond, 50 points from 1.80 to 1.94 Angstrom
ORCA_results/bond_scans/C4-C5/                 relaxed scan of the C4-C5 bond, 50 points from 1.45 to 1.59 Angstrom

Each scan folder has the ORCA input (.inp) with its start structure (octylsilanetriol.xyz, the relaxed molecule), the
output (.out), the energy of every scan point (.relaxscanact.dat and .relaxscanscf.dat), the structures of all points
(.allxyz) and the last structure (.xyz).

Run
Open the notebook in Jupyter and run all cells. Its first cell installs the Python packages it needs (numpy, pandas,
matplotlib, ase, nglview and ipywidgets).

The ORCA runs, each in its own folder:
orca octylsilanetriol.inp > octylsilanetriol.out      (ORCA_results/relaxation)
orca si_c_scan.inp > si_c_scan.out                    (ORCA_results/bond_scans/Si-C)
orca c4_c5_scan.inp > c4_c5_scan.out                  (ORCA_results/bond_scans/C4-C5)
