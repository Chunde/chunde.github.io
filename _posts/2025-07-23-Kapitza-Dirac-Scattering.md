---
layout: post  
title: Kapitza-Dirac Scattering  
date: 2025-07-22 23:08:44  
description: Quantum diffraction of particles by a standing light wave, demonstrating wave-particle duality.  
tags: quantum-mechanics atom-optics laser-cooling diffraction matter-waves  
tabs: true  
---  

### **Definition**  
*Kapitza-Dirac scattering* refers to the diffraction of matter waves (electrons, atoms, or molecules) by a standing wave of light, analogous to X-ray diffraction in crystals. Predicted by Pyotr Kapitza and Paul Dirac in 1933, it experimentally confirms the wave nature of particles.  

### **Key Mechanism**  
1. **Light-Matter Interaction**:  
   A standing laser wave creates a periodic potential (optical lattice) via the AC Stark shift. The potential $$V(x)$$ for a two-level atom is:  
   $$V(x) = \frac{\hbar \Omega^2}{4 \Delta} \cos^2(kx)$$  
   where $$\Omega$$ is the Rabi frequency, $$\Delta$$ the detuning, and $$k$$ the wavevector.  

2. **Diffraction Condition**:  
   Particles with de Broglie wavelength $$\lambda_{dB}$$ satisfying $$2d\sinθ = n\lambda_{dB}$$ (Bragg condition, $$d = \lambda_L/2$$) undergo constructive interference, splitting into discrete momentum states $$\pm n\hbar k_L$$.  

### **Experimental Setup**  
1. **Requirements**:  
   - **Ultracold Atoms/Electrons**: Typically Bose-Einstein condensates (BECs) or laser-cooled atoms (µK temperatures).  
   - **Standing Wave**: Counter-propagating laser beams forming a 1D optical lattice (wavelength $$\lambda_L$$).  
   - **Pulse Duration**: Short interaction time (µs to ms) to avoid spontaneous emission.  

2. **Steps**:  
   - **Cooling & Trapping**: Prepare atoms in a magneto-optical trap (MOT) and evaporatively cool to BEC.  
   - **Pulse Application**: Shine the standing wave for a time $$t$$ (adjusted to reach $$n$$th-order diffraction).  
   - **Detection**: Time-of-flight imaging reveals diffracted peaks separated by $$2\hbar k_L$$.  

### **Diffraction Regimes**  
- **Raman-Nath (Weak Pulses)**: Multiple diffraction orders (thin grating approximation).  
- **Bragg (Strong Pulses)**: Selective $$n$$-th order transitions (thick grating).  

### **Applications**  
- **Atom Interferometry**: Precision measurements of $$g$$, $$\hbar/m$$.  
- **Quantum Simulation**: Emulating solid-state physics in optical lattices.  
- **Matter-Wave Optics**: Building atomic beam splitters for quantum computing.  

### **Example Experiment**  
A **$$^{87}Rb$$ BEC** exposed to a 780 nm standing wave ($$I \sim 10^9\, \text{W/m}^2$$, $$\Delta \sim 1\, \text{GHz}$$) for $$t = 10\, \mu\text{s}$$ produces $$\pm 2\hbar k_L$$ momentum states with 30% efficiency.  

### **Math Insight**  
The diffraction probability $$P_n$$ for $$n$$-th order follows Bessel functions (Raman-Nath) or sinusoidal dependence (Bragg):  
$$P_n = J_n^2(\Omega t/2) \quad \text{(Raman-Nath)}$$  
$$P_{\pm1} = \sin^2(\Omega t/2) \quad \text{(Bragg)}$$  

---  
**Note**: Modern experiments use optical tweezers or delta-kick cooling to enhance resolution.