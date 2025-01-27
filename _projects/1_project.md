---
layout: page
title: The Structure of Polarized Vortices in the Unitary Fermi Gas
description: Project for Ph.D thesis
img: assets/img/quantum_vortex.jpeg
importance: 1
category: Research
# related_publications: true
---

Fermionic superfluids do not generally support polarization, and the nature of the ground state of a slightly polarized unitary Fermi gas remains an open question. However, vortices naturally support polarization since the pairing gap vanishes in the core of superfluid vortices. The structure of a polarized vortex is not well understood and may have some interesting properties. To study the microscopic structure of a vortex, we use a density functional theory called the asymmetric superfluid local density approximation (ASLDA) to simulate how vortexes interact, evolve and how energy transfers between paired and unpaired particles. In this talk, I will discuss the structure and properties of polarized vortices using the ASLDA, and how these related to polarized phases through the Thomas-Fermi (TF) approximation. 

---

## Some Note from Dr. Forbes

We start with the issue of regularization.  In our first version we use an extremely simple approach: we simply use all states in the box, and adjust the fixed coupling constant $$g_c$$ so as to reproduce a particular value of the gap $$\Delta$$.  As a baseline, we use the following known 2D solution.

$$
  n_+ = \frac{k_F^2}{2\pi}, \qquad
  \epsilon_F = \frac{\hbar^2 k_F^2}{2m}, \qquad
  \mathcal{E}_{FG} = \frac{k_F^4}{8m\pi} = \frac{1}{2}n_+\epsilon_F, \qquad
  \tilde{C} = 0,\\
  \frac{\mu}{\epsilon_F} = \frac{1}{2},\qquad
  \frac{\Delta}{\epsilon_F} = \sqrt{2}\\
$$

The $$T=0$$ equations in $$d$$ dimensions can be expressed in terms of the gap $$\Delta$$ and effective chemical potential $$\mu_{\text{eff}} = \mu_0 - g_cn_+/2$$ where $$g_c<0$$ represents an attractive interaction:

$$
  \Delta = g_c \nu_c, \qquad
  \epsilon_+ = \frac{\hbar^2k^2}{2m} - \mu_{\text{eff}}, \qquad
  \mathcal{E} = \frac{E}{V} 
              = \frac{\hbar^2\tau_c}{2m} + g_c(n_an_b+\nu_c^\dagger\nu_c)
              = \frac{\hbar^2\tau_c}{2m} + \Delta^\dagger\nu_c - \frac{(\mu_{\text{eff}} - \mu_0)n_+}{2},
$$

through the following integrals:
  
$$
  \nu_c = -\int_{c}\frac{d^d{k}}{(2\pi)^d}\;\frac{\Delta}{2\sqrt{\epsilon_+^2 + \Delta^2}}
  \sim -\int_{c}\frac{d^d{k}}{(2\pi)^d}\;\frac{m\Delta}{\hbar^2 k^2},\\
$$

$$
  \tau_c= \int_c\frac{d^d{k}}{(2\pi)^d}\; k^2
    \left[1 - \frac{\epsilon_+}{\sqrt{\epsilon_+^2 + {\Delta}^2}}\right]
 \sim \int_c\frac{d^d{k}}{(2\pi)^d}\;  
  \frac{2m^2{\Delta}^2}{\hbar^4 k^2},\\
$$

$$
  n_+ = \int_c\frac{d^d{k}}{(2\pi)^d}
    \left[1 - \frac{\epsilon_+}{\sqrt{\epsilon_+^2 + {\Delta}^2}}\right]
  \sim \int_c\frac{d^d{k}}{(2\pi)^d}\; 
  \frac{2m^2{\Delta}^2}{\hbar^4 k^4}.
$$

In 1D, these converge, but in 2D and higher, the quantities $$\tau_c$$ and $$\nu_c$$ diverge as $$\ln(k_c)$$ in 2D and as $$k_c$$ in 3D.  The density $$n_+$$ converges in both 2D and 3D, although slower in 3D.  Note that the divergence in $$\tau_c$$ and $$\nu_c$$ cancel in the combination

\begin{align}
  \kappa &=\int_c\frac{d^d{k}}{(2\pi)^d}\;\left(\frac{\hbar^2\tau_c}{2m} + \Delta^\dagger \nu_c\right) 
  &&\sim \int_c\frac{d^d{k}}{(2\pi)^d}\;\frac{2m^2{\Delta}^2\mu_{\text{eff}}}{\hbar^4 k^4},
\end{align}

which enters the energy density $$\mathcal{E}$$.

To regularize the theory, we must define some finite physical quantities that we can hold fixed as we take the cutoff to infinity so as to defined the parameters of the theory in a way that the physics becomes independent of the cutoff in the large cutoff limit.  In 3D we express this as follows (see [Bulgac:2011] Eq. (84) but we consider only unit effective mass $$\alpha_+ = 1$$):

\begin{align}
  \tilde{C}(n_a, n_b) &= \overbrace{\frac{\nu_c}{\Delta}}^{\frac{1}{g_c}} + \overbrace{\frac{1}{2}\int_c \frac{d^d{k}}{(2\pi)^d} \frac{1}{\epsilon_+ + i 0^+}}^{\Lambda_c} = \frac{1}{g_c} + \Lambda_c
  &&\sim \int_c \frac{d^d{k}}{(2\pi)^d} \frac{2m^3{\Delta}^2}{\hbar^6 k^6}.
\end{align}

where the integral is take in the principal value sense.  This is motivated by the familiar Eagles-Leggett model, where this quantity is related to the two-body scattering length $$a_s$$:

$$
  \tilde{C}(n_a, n_b) = \frac{m}{4\pi \hbar^2 a_s}.
$$

Strictly speaking, the denominator in the integral should have $$\epsilon_+ = \hbar^2k^2/2m$$ without the chemical potential because the calculation of the scattering length should take place in the vacuum. To improve convergence, however, we include the chemical potential in $$\epsilon_+ = \hbar^2k^2/2m - \mu$$ as advocated in [BY:2002fk].  This does not change the 3D result in the limit $$k_c \rightarrow \infty$$ but shifts the finite portion to improve convergence.  Without this shift, the integral would behave as $$\tilde{C} \sim -\int_cd^d{k}\;2m^2\mu_{\text{eff}}/(2\pi)^d\hbar^4 k^4$$.

The principal value integrals can now be performed analytically:

$$
  \Lambda_c^{1D} = \frac{m}{\hbar^2}\frac{1}{2\pi k_0}\ln\frac{k_c-k_0}{k_c+k_0}
  \rightarrow -\frac{m}{\hbar^2}\frac{1}{\pi k_c} \rightarrow 0,
$$

$$
  \Lambda_c^{2D} = \frac{m}{\hbar^2}\frac{1}{4\pi}
  \ln\left(\frac{k_c^2}{k_0^2}-1\right) 
  \rightarrow \frac{m}{\hbar^2}\frac{1}{2\pi}\ln\frac{k_c}{k_0},
$$

$$
  \Lambda_c^{3D} = \frac{m}{\hbar^2}\frac{k_c}{2\pi^2} 
  \left(1 - \frac{k_0}{2k_c}\ln\frac{k_c+k_0}{k_c-k_0}\right)
  \rightarrow \frac{m}{\hbar^2}\frac{k_c}{2\pi^2},
$$

where

$$
  \frac{\hbar^2k_0^2}{2m} - \mu = 0, \qquad
  \frac{\hbar^2k_c^2}{2m} - \mu = E_c.
$$

The latter equation allows us to replace the momentum cutoff $$k_c$$ in terms of an energy cutoff $$E_c$$ which is of use in inhomogeneous systems.

[BY:2002fk]: https://doi.org/10.1103/PhysRevLett.88.042504 'Aurel Bulgac and Yongle Yu, "Renormalization of the Hartree-Fock-Bogoliubov Equations in the Case of a Zero Range Pairing Interaction", prl 88(4), 042504 (2002) [nucl-th/0106062v3](http://arXiv.org/abs/nucl-th/0106062v3)'

[Bulgac:2011]: http://dx.doi.org/10.1007/978-3-642-21978-8_9 'Aurel Bulgac, Michael McNeil Forbes, and Piotr Magierski, "The Unitary Fermi Gas: From Monte Carlo to Density Functionals",  836, 305 -- 373 (2012) [1008.3933](http://arXiv.org/abs/1008.3933)'

**Comments:**

As we take the cutoff $$k_c\rightarrow \infty$$ we notice the following:

* In 1D, $$\Lambda_c \rightarrow 0$$:
  * This indicates that $$\tilde{C} = -\nu_c/\Delta = -1/g_c$$ is finite, and the theory is well defined in this limit with finite anomalous density $$\nu$$, and finite cutoff $$g=v_0$$.  In this case, no cutoff is needed, but one might still like to use the cutoff procedure to improve the convergence.  In particular, when working on a lattice, there is a maximum momentum that can be represented $$k_\max$$ which will limit the convergence roughly according to the behavior discussed above.  For example, $$\nu \sim 1/k_\max$$ will converge slowly, requiring large lattices to approach the physical limit.  Using the cutoff procedure and Thomas-Fermi completion discussed below will speed this convergence.
  * Since $$g$$ is finite, one must also include the Hartree corrections to the chemical potentials:
    
    $$
      \mu_{a,b}^{\mathrm{eff}} = \mu_{a,b} + g n_{b,a}.
    $$

    This complicates things a bit because now the effective potentials depend on the density.  One can still work with fixed $$\mu$$, but this means that the self-consistent solution is the solution in a funky background potential which has been chosen to absorb these corrections.
    
* In 2D and 3D, $$\Lambda_c \rightarrow \infty$$ divergence.  This means that if we fix $$\tilde{C}$$ to be finite, then $$g_c \rightarrow 0$$.  In this case, the Haretree corrections vanish and the effective chemical potentials do not depend on the state:

  $$
    \mu^{\mathrm{eff}} = \mu = \mu_0 - V(x).
  $$
  
  This allows us to easily work in the grand-canonical ensemble.
  
* In 3D, $$\Lambda_c$$ is independent of $$k_0$$ in the limit of large cutoff.  This means that the including the pole, which improves the convergence, does not affect the usual identification of the scattering length.

* In 2D, however, there remains a dependence on $$k_0$$ in the large cutoff limit.  This means that our procedure for specifying the functional through $$\tilde{C}$$ depends on $$k_0$$.  This is not ideal for a density function because it means that the physical interpretation of the results depend on the external potential - i.e. the DFT is not independent of the potential as it should be.  The previous point that Hartree terms vanish helps a bit since $$k_0$$ then depends only on the external trap and bare chemical potentials.  (Otherwise, the DFT would be state-dependent which would be even worse!)

  The results of this simple approach must be interpreted instead as the results of a DFT fixing the following combination:
  
  $$
    \tilde{C} - \frac{m}{2\pi \hbar^2}\ln k_0
  $$

  which becomes independent of $$k_c$$ in the limit of large cutoff.  Note that this diverges at the classical turning points where $$k_0 = 0$$.  I am not sure if this poses any issues, and perhaps is expected and related to some of the divergent behaviour in 2D where results depend on the boundary conditions quite strongly. *(One should include a dimensionless factor in the log to render $$k_0/\tilde{k}$$ dimensionless, but this will just be absorbed into the constant value.)*  In any case, this simple regularization procedure should be fine for qualitative and exploratory work keeping in mind that the results might depart strongly from "physical" 2D results near the turning points.

  ## Example: 2D

  As an example, consider homogeneous states in 2D.  Suppose one knows $$\Delta$$ and $$\mu_+$$, how should $$\tilde{C}$$ be determined?  In principle, one can simply compute:

$$
  \tilde{C}(n_a, n_b) = \lim_{k_c\rightarrow\infty}\left(
    \frac{\nu_c}{\Delta} + \frac{1}{2}\int_0^{k_c} \frac{d{k}}{2\pi} \frac{k}{\epsilon_+ + i 0^+}
  \right)
  = \frac{1}{2} \int_0^{\infty}\frac{d{k}}{2\pi}\left(- \frac{k}{\sqrt{\epsilon_+^2 + \Delta^2}} +  \frac{k}{\epsilon_+ + i 0^+}\right).
$$

However, numerically computing this integral can be challenging because of the pole.  We can proceed as we would were we performing the computation in a discrete basis. 

## Thomas Fermi Completion
To facilitate convergence in the case when the solutions vary slowly, we can include states with $$E>E_c$$ by assuming that on length-scales smaller than $$1/k_c$$ the solution is homogeneous and performing the integrals.  This can be done exactly (numerically completing the integrals) or as a series approximation in $$1/k_c$$.

As an example, consider the computation of the gap equation.  We will illustrate this with symmetric homogeneous matter in 2D.  As discussed above, this presents some difficulties due to the divergent behaviour of $$\Lambda_c$$.  In a typical calculation, this would proceed as follows:

1. First compute the anomalous density $$\nu_c$$ by diagonalizing the Hamiltonian and include only states with $$E<E_c$$ = $$\hbar^2k_c^2/2m $$.  For 2D homogeneous matter this would be

   $$
     \nu_c = -\int_{0}^{k_c}\frac{kd{k}}{2\pi}\;\frac{\Delta}{2\sqrt{\epsilon_+^2 + \Delta^2}}.
   $$

2. We would then use the regulated equation for $$\tilde{C}$$ to compute the coupling constant:

   $$
     g_c = \frac{1}{\tilde{C}-\Lambda_c}.
   $$
  
3. Finally, we would use the gap equation to find the self-consistency condition $$\Delta = g_c\nu_c$$.

Putting these together, we have:

$$
  \tilde{C}(n_a, n_b) = -\frac{\nu_c}{\Delta} + \Lambda_c + O(k_c^{-4}) 
  = -\int_{0}^{k_c}\frac{kd{k}}{2\pi}\;\frac{\Delta}{2\sqrt{\epsilon_+^2 + \Delta^2}}
  + \frac{1}{2}\int_{0}^{k_c}\frac{kd{k}}{2\pi}\; \frac{1}{\epsilon_+ + i 0^+}
  + O(k_c^{-4}).
$$

This is missing the contributions from the states above $$k_c$$ which would be corrected by including the full integrals:

$$
  \tilde{C}(n_a, n_b) = \frac{\nu_c}{\Delta} + \Lambda_c
  + \frac{1}{2}\int_{k_c}^{\infty}\frac{kd{k}}{2\pi}\;\left(
    \frac{1}{\epsilon_+ + i 0^+} -\frac{1}{\sqrt{\epsilon_+^2 + \Delta^2}}\right).
$$

We call this latter correction the "Thomas-Fermi Completion".  The idea is to assume that on length scales shorter than $$1/k_c$$, the system is approximately homogeneous and so one can use the homogeneous equations to complete the contributions to various pieces from the missing states.  One either computes the integrals above $$k_c$$ numerically, or performs a series expansion in $$ k_c^{-1} $$ to compute the corrections at each point in space.  (These corrections will in general depend on position because the quantities in the integrand such as $$\Delta(x)$$ will depend depend on position.)

*Aside: this procedure also allows us to compute $$\tilde{C}$$ in two dimensions.  Although the integral is finite, numerically computing through the pole is a challenge since one really needs a PV integral.  If we follow this procedure, however, we can compute $$\nu_c$$ numerically, $$\Lambda_c$$ analytically, then apply the TF completion.*

$$
  n_+ = \int{dk}\overbrace{\left(1 - \frac{\epsilon^+_k}{E_k}
               \underbrace{\bigl(f(\omega_-) - f(\omega_+)\bigr)}_{f_\nu}
          \right)}^{f_+}
$$
$$
n_- = \int{dk}\overbrace{\bigl(f(\omega_+) - f(-\omega_-)\bigr)}^{f_-}
$$

$$
\tau_+ = \int{dk} k^2f_+, \\
\tau_- = \int{dk} k^2f_-, \\
\nu = -\int{dk}\frac{\Delta}{2E_k}\overbrace{\bigl(f(\omega_-)-f(\omega_+)\bigr)}^{f_\nu}\\
$$

$$
  \kappa = \int{dk} \left(\frac{\hbar^2k^2}{2m_+}f_+ 
                         - \frac{\Delta^2}{2E_k}f_\nu\right),\\
  \tilde{C} = \int{dk} \frac{1}{2}\left(
    \frac{1}{\epsilon_+ + i 0^+} - \frac{f_\nu}{E_k}\right).
$$


$$
  n^{3D}_+ \approx \int_{E<E_c}\frac{d^d{k}}{(2\pi)^d}
    \left[1 - \frac{\epsilon_+}{\sqrt{\epsilon_+^2 + {\Delta}^2}}\right]
  + \frac{m^2{\Delta}^2}{k_c \hbar^4\pi^2}
  + \frac{4m^3{\Delta^2}\mu}{3\hbar^6 \pi^2 k_c^3}
  + O(k_c^{-5}),
$$

$$
  \kappa^{3D} \approx \int_{E<E_c}\frac{d^d{k}}{(2\pi)^d}\;\left(\frac{\hbar^2\tau_c}{2m} + \Delta^\dagger \nu_c\right)
  + \frac{m^2 \mu {\Delta}^2}{\hbar^4 \pi^2 k_c}
  + \frac{m^3{\Delta}^2(8\mu^2-{\Delta}^2)}{6\hbar^6\pi^2 k_c^3}
  +O(k_c^{-5}),  
$$

### 3D

Here we check the results for homogeneous matter in various dimensions.  In 3D can compare these with the results we know for the BdG equation (Eagles-Leggett model) at unitarity:

$$
  n_+ = n_a+n_b = \frac{k_F^3}{3\pi^2}, \qquad
  \epsilon_F = \frac{\hbar^2 k_F^2}{2m}, \qquad
  \mathcal{E}_{FG} = \frac{k_F^5}{10m\pi^2} = \frac{3}{5}n_+\epsilon_F, \qquad
  \tilde{C} = 0,
$$

$$
  \xi = \frac{\mathcal{E}}{\mathcal{E}_{FG}}    = \frac{\mu}{\epsilon_F} = 0.59060550703283853378393810185221521748413488992993\cdots
$$

$$
  \frac{\Delta}{\epsilon_F} = 0.68640205206984016444108204356564421137062514068346\cdots\\
$$

$$
  \frac{\Delta}{\mu} = 1.162200561790012570995259741628790656202543181557689\cdots.
$$
### 2D

In 2D, we must compute results but we seem to have:

$$
  n_+ = \frac{k_F^2}{2\pi}, \qquad
  \epsilon_F = \frac{\hbar^2 k_F^2}{2m}, \qquad
  \mathcal{E}_{FG} = \frac{k_F^4}{8m\pi} = \frac{1}{2}n_+\epsilon_F, \qquad
  \tilde{C} = 0,\\
  \frac{\mu}{\epsilon_F} = \frac{1}{2},\qquad
  \frac{\Delta}{\epsilon_F} = \sqrt{2}\\
$$

### 1D

In 1D, we have the following:

$$
  n_+ = \frac{k_F}{\pi}, \qquad 
  \epsilon_F = \frac{\hbar^2 k_F^2}{2m}, \qquad
  \mathcal{E}_{FG} = \frac{k_F^3}{3m\pi} = \frac{2}{3}n_+\epsilon_F, \qquad
$$

$$
  \tilde{C} = -\frac{m}{\hbar^2k_F},\\
  \frac{\mu}{\epsilon_F} = 0.28223521359741266,\qquad
  \frac{\Delta}{\epsilon_F} = 0.41172622996179004.
$$