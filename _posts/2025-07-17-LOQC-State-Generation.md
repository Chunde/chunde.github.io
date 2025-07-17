---
layout: post
title: LOQC State Generation
date: 2025-07-17 00:42:13
description: Step-by-step demonstration of generating quantum states using linear optical quantum computing methods
tags: Quantum-Computing LOQC Photonics Quantum-Optics
tabs: true
---

### Step-by-Step LOQC State Generation

1. **Photon Source Preparation**  
   Begin with spontaneous parametric down-conversion (SPDC) to generate entangled photon pairs:  
   $$|\psi\rangle = \frac{1}{\sqrt{2}}(|H\rangle_1|H\rangle_2 + |V\rangle_1|V\rangle_2)$$

2. **Polarization Encoding**  
   Use wave plates to encode qubits in photon polarization states:  
   $$|0\rangle \equiv |H\rangle, \quad |1\rangle \equiv |V\rangle$$

3. **Beam Splitter Operation**  
   Apply a 50:50 beam splitter transformation:  
   $$\hat{a}^\dagger \rightarrow \frac{1}{\sqrt{2}}(\hat{b}^\dagger + \hat{c}^\dagger)$$  
   $$\hat{d}^\dagger \rightarrow \frac{1}{\sqrt{2}}(\hat{b}^\dagger - \hat{c}^\dagger)$$

4. **Post-Selection**  
   Detect photons in specific output modes to herald successful state creation (e.g., Bell state generation requires coincidence detection)

5. **Feed-Forward Correction**  
   Apply conditional phase shifts based on measurement outcomes:  
   $$U_{ff} = e^{i\pi|1\rangle\langle 1|}$$

6. **Verification**  
   Perform quantum state tomography to confirm the generated state's fidelity

Key optical components required:
- Nonlinear crystals (BBO/PPKTP)
- Polarizing beam splitters
- Half-wave and quarter-wave plates
- Single-photon detectors

The entire process can be represented as a quantum circuit:  
$$\text{SPDC} \rightarrow \text{BS} \rightarrow \text{PS} \rightarrow \text{PBS} \rightarrow \text{Det.}$$

Where BS = Beam Splitter, PS = Phase Shifter, PBS = Polarizing Beam Splitter, Det. = Detection. The exact sequence depends on the target state (e.g., GHZ, cluster, or graph states).