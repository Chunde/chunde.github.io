---  
layout: post  
title: Gapped 1D Systems and Area Law  
date: 2025-07-07 23:45:49  
description: Explanation of low entanglement in gapped 1D systems and the area law with discrete examples.  
tags: Quantum Physics, Entanglement, Area Law, Condensed Matter  
tabs: true  
---  

### **1. Why Gapped 1D Systems Have Low Entanglement**  
Gapped 1D quantum systems (e.g., spin chains) typically exhibit **low entanglement** because their ground states avoid long-range quantum correlations. A discrete example is the **Majumdar-Ghosh spin chain**:  

- Consider a 1D spin-1/2 chain with Hamiltonian:  
  $$H = \sum_i \left( \vec{S}_i \cdot \vec{S}_{i+1} + \frac{1}{2} \vec{S}_i \cdot \vec{S}_{i+2} \right)$$  
- The ground state is a **dimerized product state** (e.g., spins form singlets on alternating bonds):  
  $$|\psi\rangle = (|01\rangle - |10\rangle) \otimes (|01\rangle - |10\rangle) \otimes \dots$$  
- The entanglement entropy of any bipartition is **zero** (no entanglement across cuts) because the state is a product of local singlets.  

Gapped systems generally satisfy the **area law**, meaning entanglement entropy scales with the boundary size (here, a constant in 1D).  

---  

### **2. Area Law Explained with a Simple Example**  
The **area law** states that the entanglement entropy $$S_A$$ of a subsystem $$A$$ scales with its boundary size (not volume).  

#### **Example: 1D Spin Chain with Nearest-Neighbor Coupling**  
 Hamiltonian: $$H = -J \sum_i \sigma_i^z \sigma_{i+1}^z$$ (Ising model in its gapped phase).  
 Ground state (for $$J > 0$$): $$|\psi\rangle = |\uparrow \uparrow \dots \uparrow\rangle$$ or $$|\downarrow \downarrow \dots \downarrow\rangle$$.  
 Bipartition the chain into $$A$$ (first $$L$$ spins) and $$B$$ (rest).  
 Reduced density matrix $$\rho_A$$ is pure (e.g., $$\rho_A = |\uparrow \dots \uparrow\rangle \langle \uparrow \dots \uparrow|$$), so $$S_A = 0$$.  

For slightly entangled states (e.g., perturbed ground states), $$S_A$$ remains **constant** (independent of $$L$$), obeying the area law. In higher dimensions, $$S_A \sim \text{boundary area of } A$$.  

#### **Violations of Area Law**  
- Critical (gapless) systems in 1D: $$S_A \sim \log L$$ (logarithmic divergence).  
- Highly excited states: Volume-law scaling ($$S_A \sim L$$).  

The area law is a hallmark of **low-complexity quantum states**, relevant for efficient numerical simulations (e.g., DMRG, tensor networks).