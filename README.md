# Computational Drug Discovery Portfolio

This repository demonstrates an **end-to-end virtual screening and binding free energy pipeline**, integrating **molecular docking, molecular dynamics (MD), and quantum chemistry (DFT + solvation)**.

---

## Projects

### Docking_VS

* **Tools:** AutoDock Vina, Open Babel, Py3Dmol
* **Highlights:**

  * Protein & ligand preparation (PDB → PDBQT, MOL/SDF → PDBQT)
  * Automated docking loop for multiple ligands
  * Extraction of binding energies from log files
  * Ligand ranking and **in-browser 3D visualization**

---

### MD\_Simulation

* **Tools:** GROMACS (scripts, templates)
* **Highlights:**

  * Protein–ligand system setup with solvation & ions
  * Energy minimization, equilibration, and production MD
  * Trajectory analysis (RMSD, RMSF, hydrogen bonds, etc.)
  * Demonstrates ability to run **atomistic simulations**

---

### FreeEnergy

* **Tools:** Gaussian (CPCM), NWChem (COSMO)
* **Highlights:**

  * Template input files for **protein–ligand DFT calculations** with solvation
  * Refinement of docking/MD poses at **quantum chemistry level**
  * More accurate estimation of **binding free energies**

---

## Workflow Summary

1. **Docking** → Generate poses & initial binding scores
2. **Molecular Dynamics** → Refine poses in explicit solvent and dynamic conditions
3. **DFT + Solvation** → Apply quantum-level correction with solvent effects

This pipeline reflects how **industry and academic groups** reduce false positives, refine hits, and evaluate binding energetics in **drug discovery**.

---

## How to Run

* **Docking:** Google Colab notebooks provided (runs online).
* **MD:** Requires GROMACS (local HPC, Linux, or cloud).
* **Free Energy (DFT):**

  * Gaussian (licensed, HPC/WebMO)
  * NWChem (open-source, runs on [ChemCompute](https://chemcompute.org))

---

