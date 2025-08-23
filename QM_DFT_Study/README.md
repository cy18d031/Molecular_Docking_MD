# Binding Free Energy Estimation (DFT + Solvation)

This folder demonstrates **binding free energy estimation** of protein–ligand complexes using **quantum chemistry with solvation models (COSMO/PCM)**.

---

## Key Idea
- **Docking** provides binding poses (geometric fit).  
- **Molecular Dynamics (MD)** refines these poses in a realistic environment.  
- **DFT with solvation (COSMO/PCM)** adds **quantum accuracy + solvent effects** to estimate binding free energies.  

---

##  Example Input Files

### Gaussian (CPCM = COSMO-like solvation)

```text
%chk=ligand.chk
# B3LYP/6-31G(d) SCRF=(CPCM,Solvent=Water) Opt Freq

Ligand optimization in water (CPCM solvation)

0 1
O   0.0000   0.0000   0.1173
H   0.0000   0.7572  -0.4692
H   0.0000  -0.7572  -0.4692
````

* `SCRF=(CPCM,Solvent=Water)` → activates continuum solvation (water).
* Replace coordinates with your ligand or complex.
* Run in **Gaussian (WebMO, university HPC, or licensed cluster)**.

---

### NWChem (COSMO block, free via ChemCompute)

```text
start ligand_cosmo

geometry units angstroms
  O   0.0000   0.0000   0.1173
  H   0.0000   0.7572  -0.4692
  H   0.0000  -0.7572  -0.4692
end

basis
  * library 6-31g*
end

dft
  xc b3lyp
end

cosmo
  dielectric 80.4   # water
end

task dft optimize
```

* `cosmo` block specifies **solvent dielectric** (80.4 = water).
* Can be run online at **[ChemCompute](https://chemcompute.org)** (free for academics).

---

## Output

* **Optimized ligand geometry in solvent**
* **Solvation free energy correction (ΔG\_solv)**
* Combine ligand, receptor, and complex results to estimate **ΔG\_binding**


---

## Where to Run

* **Gaussian CPCM** → WebMO / university HPC
* **NWChem COSMO** → [ChemCompute (free academic cloud)](https://chemcompute.org)
* **ADF COSMO-RS** → SCM trial license
---

## Note on Alternatives

Other approaches exist for free energy estimation, such as **MM-GBSA** (widely used in pharma).
This subfolder does **not** implement MM-GBSA, but the input files here demonstrate that I can set up **DFT + solvation models**, which are more rigorous and highlight my ability to use **quantum chemistry for binding studies**.
