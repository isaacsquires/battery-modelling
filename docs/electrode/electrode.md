# Electrode

There are two charge carriers that are transported in the electrode: lithium ions and electrons. This section deals with solid state transport (transport of charge through the solid electrode phase), see [electrolyte](../electrolyte/electrolyte.md) for transport through the liquid electrolyte.

The dominant processes in solid state transport are ionic diffusion and electronic conduction. The transport of lithium ions is described by [Fick's law](../fundamentals/diffusion.md) and the transport of electrons is described by [Ohm's law](https://en.wikipedia.org/wiki/Ohm%27s_law).

## Ionic diffusion

The crystal structure of the electrode determines exactly how Li-ions will move through the solid. Li-ions move through vacancies in the crystal structure. Depending on the structure, this transport can be 3D, 2D or 1D. In NMC, the transport is 2D due to the layered structure of the crystal. Whereas in LFP, the transport is 1D due to the olivine structure of the crystal. This suggests anisotropic transport models that account for the crystal structure of the electrode may be more accurate than isotropic models. However, isotropic models are often used in practice due to their simplicity and the fact that the effect of anisotropy may be "averaged out" for polycrystalline materials.

The isotropic transport of lithium ions in the electrode is described by Fick's law of diffusion (derived in [diffusion](../fundamentals/diffusion.md)). The resulting transport equation is:

$$\frac{\partial c}{\partial t} = D \nabla^2c$$

where $c$ is the concentration of lithium ions, $t$ is time, $\nabla^2$ is the Laplacian, and $D$ is the diffusion coefficient.

In reality, the diffusion coefficient is a strong function of concentration which leads to non-linear diffusion. The equation then becomes:

$$\frac{\partial c}{\partial t} = \nabla\cdot(D(c) \nabla c)$$

It is common to write the diffusion equation as a [continuity equation](../fundamentals/continuity.md) in the form

$$\frac{\partial c}{\partial t} + \nabla \cdot \mathbf{j_c} = 0, \qquad \mathbf{j_c}=-D(c)\nabla c$$

where $\mathbf{j_c}$ is the flux of lithium ions (note it is technically a flux density, but we will use the term flux for simplicity).

## Electronic conduction

The conduction of electrons in the electrode is described by Ohm's law. This is a linear relationship between the electric field and the current density

$$\mathbf{j_\phi} = \sigma \mathbf{E}$$

where $\mathbf{j_\phi}$ is the current density, $\sigma$ is the conductivity, and $\mathbf{E}$ is the electric field. We can write this in terms of the potential $\phi$ as

$$\mathbf{j_\phi} = -\sigma \nabla \phi$$

We can now use the conservation of charge to write a continuity equation

$$\nabla \cdot \mathbf{j_\phi} = 0, \qquad \mathbf{j_\phi} = -\sigma \nabla \phi$$

## Other approaches

There are other approaches to modelling the transport of lithium ions and electrons in the electrode. Among the most popular is the phase-field approach. The phase-field approach uses the Cahn-Hilliard equations to model phase separation. More information can be found in [@Richardson2022-wp].
