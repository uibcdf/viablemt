# ViableMT
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/python-3.9%20%7C%203.10%20%7C%203.11-blue)](https://www.python.org/)
[![Rust](https://img.shields.io/badge/rust-powered-orange)](https://www.rust-lang.org/)
[![UIBCDF](https://img.shields.io/badge/UIBCDF-Lab-00a896)](http://www.uibcdf.org)

**The Universal Developability and Liability Profiling Engine for Molecular Systems.**

## What is ViableMT?
**ViableMT** is a high-performance computational engine designed to evaluate the real-world survivability of molecular designs. Acting as the developability and liability profiling module of **MolSysSuite**, it transcends the classical ADMET (Absorption, Distribution, Metabolism, Excretion, and Toxicity) paradigm to offer a holistic "fitness" evaluation of small molecules, peptides, and biological probes.

While other tools focus purely on topological binding affinities, ViableMT answers the critical downstream questions: *Is it safe? Is it stable? Can it be synthesized? Will it aggregate?* By evaluating these parameters dynamically, ViableMT prevents late-stage failures and accelerates the transition from theoretical *in-silico* hits to viable real-world candidates.

## Core Capabilities

* **Holistic ADMET & Toxicity Profiling:** Deep screening for metabolic lability, hepatotoxicity, hERG inhibition, and classical pharmacokinetic parameters to ensure biological safety.
* **Synthetic Accessibility (SA) & Formulatability:** Algorithms to predict the synthetic complexity of AI-generated compounds, alongside physicochemical stability metrics (e.g., colloidal aggregation, hygroscopicity, and PAINS recognition).
* **Biopolymer Viability:** Specialized profiling for peptides and macrocycles, evaluating proteolytic stability, membrane permeability, and physiological solubility.
* **Phase-Agnostic Architecture:** Designed to be used at any stage of the engineering pipeline—from filtering libraries of millions of hits to fine-tuning the liability profile of an advanced lead compound.
* **Seamless Interoperability:** Powered by a high-efficiency Rust computational core and fully integrated with `MolSysMT`. It accepts any molecular representation natively without requiring manual file conversions.

## Why "Viable"?
In modern molecular engineering, evaluating a molecule is no longer tied to the strict "Hit-to-Lead" pharmaceutical pipeline. Whether you are designing a therapeutic small molecule, an industrial peptide, or a fluorescent diagnostic probe, the ultimate goal is **viability**. ViableMT is universally applicable across disciplines, providing a unified metric of a molecule's practical fitness.

## Quick Start

ViableMT is designed to feel completely native to the MolSysSuite ecosystem.

```python
import molsysmt as msm
import viablemt as vmt

# 1. Load a molecular system (e.g., an identified hit or AI-generated peptide)
molecular_system = msm.convert('hit_candidate.sdf')

# 2. Run a full viability and developability profile
profile = vmt.get_viability_profile(molecular_system)

# 3. Analyze critical liabilities
print(f"Synthetic Accessibility Score: {profile.synthetic_accessibility}")
print(f"Toxicity Alerts: {profile.toxicity_alerts}")
print(f"Predicted Proteolytic Stability: {profile.proteolytic_stability}")

# 4. Filter libraries based on specific viability thresholds
viable_candidates = vmt.filter(molecular_library, min_solubility='moderate', exclude_pains=True)
```

## The MolSysSuite Ecosystem
ViableMT is an independent library that reaches its maximum potential when orchestrated within the broader **MolSysSuite** architecture developed at the [Research Unit on Computational Biology and Drug Design (UIBCDF)](http://www.uibcdf.org):

* **`molsysmt`**: The universal molecular systems interoperability layer.
* **`topomt`**: Topology and geometric analysis.
* **`bindingmt`**: Thermodynamic and binding affinity calculations.
* **`pharmacophoremt`**: Pharmacophore modeling and spatial tolerance.
* **`allomt`**: Allosteric communication and cryptic pocket mapping.
* **`peptidemt`**: Specialized biopolymer and peptide manipulation.
* **`molsysviewer` / `molsyssketcher`**: Advanced 3D and 2D interactive visualization.
* **`viablemt`**: Developability, ADMET, and liability profiling.

## License
ViableMT is distributed under the [MIT License](LICENSE).
