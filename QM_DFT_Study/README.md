

# Binding Free Energy Estimation (DFT + Solvation)

This subfolder focuses on applying **Density Functional Theory (DFT)** calculations with solvation models to evaluate **ligand binding free energies**.

---

## Purpose

Docking and molecular dynamics (MD) provide binding poses and dynamic stability, but their scoring functions are approximate.
DFT adds a **quantum-level refinement**, incorporating **electronic structure** and **solvent effects** (COSMO/PCM), to yield more reliable estimates of binding energetics.

---

## Where to Run

* **NWChem (COSMO)** – free, can be run online via [ChemCompute](https://chemcompute.org).
* **Gaussian (CPCM)** – standard in industry, requires licensed HPC/WebMO.
* **Other solvation models** – COSMO-RS (ADF) or PCM variants.

---
## Files

* **complex_cpcm.gjf** - Gaussian input (B3LYP/6-31G*, CPCM solvation in water).
* **complex_cosmo.nw** - NWChem input (B3LYP/6-31G*, COSMO solvation in water).

The placeholder line:[Insert coordinates of protein–ligand complex here] needs to be replaced with the actual coordinates of the receptor–ligand system (from docking/MD).
---
## Output

* Optimized ligand geometry in solvent.
* Solvation free energy correction (ΔG\_solv).
* Binding free energy refinement for ligand–protein complexes.

---

## Note on Alternatives

Other approaches exist for free energy estimation, such as **MM-GBSA** (widely used in pharma).



