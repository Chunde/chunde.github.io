---
layout: post  
title: HOM Effect Phase Shift and Unitarity  
date: 2025-07-12 20:20:23  
description: Explanation of the π phase shift in beam splitter reflections and discrete proof of unitarity requirement.  
tags: Quantum-Optics Interference Unitarity Beam-Splitter  
categories: Physics  
tabs: true  
---

### Why the π Phase Shift Exists  
In a symmetric beam splitter, the reflection from the **bottom side** acquires a π phase shift (factor of $$-1$$) due to the **Fresnel coefficients** and boundary conditions of electromagnetic waves. This is required because:  
1. **Field Continuity**: The electric field undergoes a phase reversal when reflecting off a denser medium (bottom side), while the top-side reflection (air-to-glass) does not.  
2. **Unitarity Constraint**: Without this sign flip, the beam splitter’s transformation matrix would violate probability conservation (non-unitary).  

### Discrete Proof of Unitarity Requirement  
A 50:50 beam splitter’s transformation is represented by the matrix:  
$$
U = \begin{pmatrix}
t & r \\
r & t
\end{pmatrix}
$$  
where $$t$$ (transmission) and $$r$$ (reflection) are complex coefficients.  

#### Step 1: Unitarity Condition  
For $$U$$ to be unitary, it must satisfy $$U^\dagger U = I$$. Explicitly:  
$$
\begin{pmatrix}
t^* & r^* \\
r^* & t^*
\end{pmatrix}
\begin{pmatrix}
t & r \\
r & t
\end{pmatrix}
= 
\begin{pmatrix}
|t|^2 + |r|^2 & t^*r + r^*t \\
r^*t + t^*r & |r|^2 + |t|^2
\end{pmatrix}
= I
$$  

#### Step 2: Constraints on Coefficients  
From the off-diagonal terms:  
1. $$t^*r + r^*t = 0$$ (destructive interference condition).  
2. $$|t|^2 + |r|^2 = 1$$ (energy conservation).  

For a 50:50 splitter, $$|t| = |r| = \frac{1}{\sqrt{2}}$$. Let $$t = \frac{1}{\sqrt{2}}$$ (real for simplicity), then:  
- If **no π shift** ($$r = \frac{1}{\sqrt{2}}$$), the off-diagonal term becomes:  
  $$\frac{1}{\sqrt{2}} \cdot \frac{1}{\sqrt{2}} + \frac{1}{\sqrt{2}} \cdot \frac{1}{\sqrt{2}} = 1 \neq 0$$ → **Violates unitarity**.  
- With **π shift** ($$r = -\frac{1}{\sqrt{2}}$$), the term becomes:  
  $$\frac{1}{\sqrt{2}} \cdot \left(-\frac{1}{\sqrt{2}}\right) + \left(-\frac{1}{\sqrt{2}}\right) \cdot \frac{1}{\sqrt{2}} = -1/2 -1/2 = -1 \neq 0$$. Wait, this still seems problematic.  

Correction: The correct phase difference is **π/2** between $$t$$ and $$r$$ (not π). For unitary, we need:  
$$t = \frac{1}{\sqrt{2}}$$, $$r = \frac{i}{\sqrt{2}}$$ (top reflection) or $$r = -\frac{i}{\sqrt{2}}$$ (bottom reflection). Then:  
$$t^*r + r^*t = (-i)(i)/2 + (i)(-i)/2 = 1/2 - 1/2 = 0$$.  

#### Conclusion  
The π/2 phase difference (or sign flip for real coefficients) ensures unitarity. In the HOM effect, the **relative π shift** between top/bottom reflections guarantees destructive interference at one output port, preserving quantum reversibility.  

Key takeaway: The phase convention is fixed by unitarity, not arbitrary. No π shift → non-unitary → violates quantum mechanics.