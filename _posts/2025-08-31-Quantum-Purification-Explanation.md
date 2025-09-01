---
layout: post
title: Quantum Purification
date: 2024-12-31 20:20:10
description: Detailed explanation of quantum purification with specific examples in quantum information theory
tags: quantum-computing quantum-information purification entanglement
tabs: true
---

Quantum purification is a fundamental concept in quantum information theory that allows the conversion of a mixed quantum state into a pure entangled state by extending the Hilbert space. This process is crucial for understanding quantum entanglement, quantum error correction, and quantum communication protocols.

## Mathematical Foundation

Given a mixed state $$ \rho_A $$ acting on Hilbert space $$ \mathcal{H}_A $$, purification constructs a pure state $$ |\psi\rangle_{AB} $$ on the extended space $$ \mathcal{H}_A \otimes \mathcal{H}_B $$ such that:

$$ \text{Tr}_B(|\psi\rangle_{AB}\langle\psi|) = \rho_A $$

The purification always exists and can be constructed using the spectral decomposition of $$ \rho_A $$.

## Construction Method

For a mixed state $$ \rho_A = \sum_i p_i |\phi_i\rangle\langle\phi_i| $$, a purification is:

$$ |\psi\rangle_{AB} = \sum_i \sqrt{p_i} |\phi_i\rangle_A \otimes |i\rangle_B $$

where $$ \{|i\rangle_B\} $$ is an orthonormal basis for the ancillary system B.

## Example 1: Single Qubit Mixed State

Consider a mixed qubit state: $$ \rho = \frac{1}{2}|0\rangle\langle 0| + \frac{1}{2}|1\rangle\langle 1| $$

**Purification:**
$$ |\psi\rangle_{AB} = \frac{1}{\sqrt{2}}|0\rangle_A \otimes |0\rangle_B + \frac{1}{\sqrt{2}}|1\rangle_A \otimes |1\rangle_B $$

This is the Bell state $$ |\Phi^+\rangle $$, and tracing out system B gives back the original mixed state.

## Example 2: Partially Depolarized Qubit

For a state: $$ \rho = (1-p)\frac{I}{2} + p|\psi\rangle\langle\psi| $$ where $$ |\psi\rangle = \alpha|0\rangle + \beta|1\rangle $$

**Purification:**
$$ |\psi\rangle_{AB} = \sqrt{1-p}|0\rangle_A \otimes |0\rangle_B + \sqrt{p}|\psi\rangle_A \otimes |1\rangle_B $$

## Example 3: Thermal State

For a thermal state: $$ \rho = \frac{e^{-\beta H}}{Z} $$ with Hamiltonian H and partition function Z

**Purification (Thermofield Double State):**
$$ |\psi\rangle_{AB} = \frac{1}{\sqrt{Z}} \sum_n e^{-\beta E_n/2} |n\rangle_A \otimes |n\rangle_B $$

This is the famous thermofield double state used in quantum field theory and black hole physics.

## Applications

1. **Quantum Error Correction**: Purification helps in understanding the recovery of quantum information from noisy channels
2. **Entanglement Theory**: Provides a way to quantify mixed state entanglement through entanglement of purification
3. **Quantum Communication**: Used in protocols like quantum state redistribution and quantum channel capacities
4. **AdS/CFT Correspondence**: The thermofield double state purification plays a key role in holographic duality

## Properties

- **Uniqueness**: Purification is unique up to unitary transformations on the ancillary system
- **Monotonicity**: Entanglement of purification is non-increasing under local operations and classical communication (LOCC)
- **Additivity**: For tensor product states, the entanglement of purification is additive

Quantum purification demonstrates the deep connection between mixed states and pure entangled states, revealing that every mixed state can be viewed as part of a larger pure quantum system.