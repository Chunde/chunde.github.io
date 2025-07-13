---
layout: post  
title: HOM Effect Phase Shift and Unitarity  
date: 2025-07-12 20:20:23  
description: Explanation of the π phase shift in beam splitter reflections and discrete proof of unitarity requirement.  
tags: Quantum-Optics Interference Unitarity Beam-Splitter  
categories: Physics  
tabs: true  
---

# Hong–Ou–Mandel (HOM) Effect: Why the Beam Splitter Needs a <span>$$\pi$$</span> Phase Shift

## 1. Introduction
In the Hong–Ou–Mandel (HOM) effect, two indistinguishable photons incident on a beam splitter interfere in such a way that they always exit the same output port (bunching). A key requirement is that **reflection from the bottom side introduces a $$\pi$$ phase shift**, while reflection from the top does not.

## 2. The Correct Beam Splitter Transformation
A 50:50 beam splitter transforms input modes ($$\hat{a}_1, \hat{a}_2$$) into output modes ($$\hat{a}_3, \hat{a}_4$$):

<div style="margin: 15px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px;">
$$
\begin{cases}
\hat{a}_1 \rightarrow \frac{1}{\sqrt{2}}(\hat{a}_3 + \hat{a}_4) \\
\hat{a}_2 \rightarrow \frac{1}{\sqrt{2}}(\hat{a}_3 - \hat{a}_4)
\end{cases}
$$
</div>

Matrix form:

<div style="margin: 15px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px;">
$$
U = \frac{1}{\sqrt{2}}\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}
$$
</div>

## 3. Proof of Unitarity
A matrix $$U$$ is unitary if $$U^\dagger U = I$$. Verification:

<div style="margin: 15px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px;">
$$
U^\dagger U = \frac{1}{2}\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}
\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}
= I
$$
</div>

**⇒ $$U$$ is unitary.**

## 4. Without $$\pi$$ Phase Shift
Incorrect transformation matrix:

<div style="margin: 15px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px;">
$$
U_{\text{wrong}} = \frac{1}{\sqrt{2}}\begin{pmatrix}
1 & 1 \\
1 & 1
\end{pmatrix}
$$
</div>

Fails unitarity check:

<div style="margin: 15px 0; padding: 10px; background-color: #f8f9fa; border-radius: 5px;">
$$
U_{\text{wrong}}^\dagger U_{\text{wrong}} = \begin{pmatrix}
1 & 1 \\
1 & 1
\end{pmatrix} \neq I
$$
</div>

## Key Results

| Case       | Matrix                                                          | Unitary? | HOM Effect?   |
| ---------- | --------------------------------------------------------------- | -------- | ------------- |
| Correct    | $$\frac{1}{\sqrt{2}}\begin{pmatrix}1 & 1\\1 & -1\end{pmatrix}$$ | ✅ Yes    | ✅ Bunching    |
| No π shift | $$\frac{1}{\sqrt{2}}\begin{pmatrix}1 & 1\\1 & 1\end{pmatrix}$$  | ❌ No     | ❌ No bunching |

## Conclusion
The $$\pi$$ phase shift ensures unitarity: $$U^\dagger U = I$$, required for destructive interference in the $$|1,1\rangle$$ output state. Essential for observing the HOM dip in coincidence measurements.