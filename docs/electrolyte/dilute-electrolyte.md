# Dilute electrolyte theory

## Nernst-Planck equation

Dilute electrolyte theory is an extension of the diffusion equation to include the effect of electrostatic forces. Dilute electrolyte theory is often used to model the transport of ions in the electrolyte by considering the interactions between the ions and the solvent.

We start with a [continuity equation](../fundamentals/continuity.md) for the concentration of a charged species, but now accounting for the electric field. This is often referred to as the [Nernst-Planck equation](../fundamentals/nernst-planck.md)

$$\frac{\partial c}{\partial t} + \nabla \cdot \mathbf{N} = 0, \qquad \mathbf{N}=-D\nabla c + c\mathbf{v} + \frac{Dze}{k_B T} c \mathbf{E}$$

where $c$ is the concentration of ions, $\mathbf{N}$ is the flux of ions, $D$ is the diffusion coefficient, $\mathbf{v}$ is the flow velocity, $z$ is the charge of the species, $e$ is the elementary charge, $k_B$ is Boltzmann's constant, $T$ is the temperature, and $\mathbf{E}$ is the electric field. This equation attributes the flux of ions to three terms: diffusion, advection, and electromigration. For simplicity, we will assume that the flow velocity is zero (i.e. advection currents are negligible as only the ionic species can move). We can then write the electric field in terms of potential $\mathbf{E}=-\nabla \phi$ and use the relationship between the constants, namely $F/R=ze/k_B T$. This leaves us with the simplified Nernst-Planck flux

$$\mathbf{N}=-D\nabla c + \frac{DzF}{R T} c \nabla \phi$$

## Conductivity and transference

Now consider two opposite charge carriers (a binary electrolyte), for example Li<sup>+</sup> and a negative counter-ion. We can write the Nernst-Planck flux for each species as

$$\mathbf{N_{+}}=-D_{+}\left(\nabla c_{+} + \frac{F}{R T} c_{+} \nabla \phi\right), \qquad \mathbf{N_{-}}=-D_{-}\left(\nabla c_{-} - \frac{F}{R T} c_{-} \nabla \phi\right)$$

It has been observed that for the most part there is charge neutrality between the species, meaning the concentrations of the species are equal. This is because the attraction between the ions is strong compared to space charge effects. Now consider the electric current density $\mathbf{j}$, which is the sum of the fluxes of the two species

$$
\begin{aligned}
\mathbf{j}=F(\mathbf{N}_{+}-\mathbf{N}_{-}) \\
\mathbf{j}=F\left(-(D_+-D_-)\nabla c  - \frac{F}{RT}(D_+ +D_-)c\nabla \phi\right)\\
\end{aligned}
$$

We now define the transference number $t_{+}$, which indicates the relative strength of the diffusion of positive species compared to negative species and the electrical conductivity $\kappa(c)$.

$$
\begin{aligned}
 t_{+}=\frac{D_+}{D_++D_-} \\
\kappa(c) = \frac{F^2}{RT}(D_+ +D_-)c
\end{aligned}
$$

Substituting into the Nernst-Planck equation leaves us with the following expression for the electric current density

$$\mathbf{j}=-\kappa(c)\left(\nabla \phi  - \frac{RT}{F}(1-2 t_+)\frac{\nabla c}{c}\right), \qquad \nabla \cdot \mathbf{j} = 0$$

If the diffusivities of the two species are constant, then the transference number is constant. We also note that the conductivity is proportional to the concentration of the species. However, these results do not hold for all electrolytes. The conductivity often has a non-linear relationship with concentration and although the transference number often remains approximately constant, the diffusivities are normally concentration dependent. These effects arise from the interactions between ions and therefore the ideal dilute electrolyte theory does not suffice, we instead require [concentrated electrolyte theory](concentrated-electrolyte.md).
