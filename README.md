# ebola-ai-denovo-binder
In silico de novo design of synthetic peptidic entry inhibitors targeting the Ebola Virus Glycoprotein RBS using NVIDIA MoLMiM.
# 🧬 In Silico De Novo Design of Synthetic Peptidic Binders against Ebola Virus Glycoprotein (PDB: 5DQO)

An end-to-end computational pipeline integrating **NVIDIA MoLMiM (BioNeMo API)** for generative molecular design, **BioPython / Py3Dmol** for structural interface analysis, and **SwissADME** for biophysical and pharmacokinetic profiling.

---

## 🎯 Project Overview
This project targets the Receptor-Binding Site (RBS) of the **Ebola Virus Glycoprotein (EBOV GP)** to design *de novo* peptidic entry inhibitors. By occupying the critical interface required for host receptor engagement (NPC1), these synthetic peptide binders act as competitive inhibitors designed to block viral entry into host cells.

---

## ⚙️ Technical Architecture & Pipeline Flow
1. **Target Acquisition:** Fetches and parses the EBOV GP crystal structure (`PDB: 5DQO`) using BioPython, isolating key Receptor-Binding Site (RBS) residues (`[51, 88, 111, 113, 114, 141, 142, 143]`).
2. **Generative Design:** Queries the **NVIDIA MoLMiM NIM API** seeded with complex structural fragments to generate optimized *de novo* molecular variants, filtering out trivial atomic fragments.
3. **Interfacial Scoring:** Evaluates candidates via an empirical scoring function estimating binding free energy ($\Delta G$) based on aromatic stacking and heteroatom interactions.
4. **Biophysical Profiling & Rendering:** Validates solubility and drug-likeness profiles via SwissADME parameters and renders interactive 3D complexes using Py3Dmol.

---

## 🏆 Top De Novo Binder Candidates
The screening yielded structurally robust peptide sequences tailored for the viral interface:

| Rank | Sequence / Lead Candidate | Est. Binding Free Energy ($\Delta G$) | Description |
| :---: | :--- | :---: | :--- |
| **1** | `KVDYLRSTRYNRKY` | **-4.78 kcal/mol** | Cationic-aromatic balanced 14-mer lead scaffold |
| **2** | `RFKTVRYFMKDQGK` | **-4.49 kcal/mol** | Secondary high-affinity binder variant |
| **3** | `KRLKKTSVELSRTG` | **-4.32 kcal/mol** | Electrostatic-optimized scaffold |
| **4** | `WLAVRGKWRDLKGV` | **-4.28 kcal/mol** | Hydrophobic/aromatic enriched motif |
| **5** | `SGYNQMTEAWKAFV` | **-4.26 kcal/mol** | Interfacial pocket binder variant |

---

## 📊 Biophysical & ADME Validation (SwissADME)
* **Aqueous Solubility:** $65.8\text{ mg/mL}$ (`Log S ESOL = -1.22` / **Very Soluble**), confirming ideal properties for parenteral/intravenous formulation.
* **Medicinal Chemistry:** **0 PAINS alerts**, verifying absence of pan-assay interference compounds and ensuring specific interfacial binding potential.
* **Therapeutic Class:** Classified as a biological peptide therapeutic (parenteral administration profile, complying with standard biopolymer biophysics rather than small-molecule oral Lipinski rules).

---


## ⚠️ Disclaimer & Regulatory Notice
> **Research Use Only:** This project, including its source code, computational models, sequence predictions, and biophysical scores ($\Delta G$, SwissADME metrics), is developed strictly for **educational, scientific research, and portfolio demonstration purposes**. 
> 
> The generated peptide candidates are purely *in silico* predictions and have **not been validated *in vitro*, *in vivo*, or in clinical trials**. This repository does not constitute medical, pharmacological, or clinical advice, nor does it represent a clinically approved therapeutic drug or pharmaceutical product.
