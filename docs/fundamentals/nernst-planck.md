# Nernst-Planck equation

The Nernst-Planck equation is a continuity relation for the transport of charged species in a mixture and under the influence of an electric field. This derivation is inspired by [Professor Brian J. Kirby's lecture](https://www.youtube.com/watch?v=4zlMjzC7NT8).

## Diffusion and convection

Consider the flux of a charged species through a control volume. The system obeys the continuity law

$$
\begin{aligned}
\frac{\partial c_i}{\partial t} + \nabla \cdot \mathbf{N_i} = 0
\end{aligned}
$$

where $c_i$ is the concentration of species $i$ and $\mathbf{N_i}$ is the flux of species $i$. The flux is given by

There are two contributions to the flux: the diffusive flux and the convective flux. These can be written as

$$
\begin{aligned}
\mathbf{N^d_i} = -D_i \nabla c_i \\
\mathbf{N^c_i} = c_i \mathbf{v_i} \\
\mathbf{N_i} = \mathbf{N^d_i} + \mathbf{N^c_i}
\end{aligned}
$$

where $D_i$ is the diffusion coefficient, $c_i$ is the concentration and $\mathbf{v_i}$ is the velocity of species $i$. The divergence of the total flux in the volume determines the change in the concentration of the species in the volume. This can be written as

$$
\begin{aligned}
\frac{\partial c_i}{\partial t} + \nabla \cdot \left( -D_i \nabla c_i + c_i \mathbf{v_i} \right) = 0
\end{aligned}
$$

## Electromigration

Now we introduce Ohm's law, where the Ohmic current can be written as

$$
\begin{aligned}
\mathbf{j_i} = \sigma_i \mathbf{E}
\end{aligned}
$$

where $\mathbf{j_i}$ is the current density, $\sigma_i$ is the conductivity and $\mathbf{E}$ is the electric field. We can relate this to the drift velocity of the species

$$
\begin{aligned}
\mathbf{v_i} = \mathbf{v} + \mathbf{v_{drift}} \\
\mathbf{v_{drift}} = \frac{\mathbf{j_i}}{A} = \frac{z_i D_i F}{RT} \mathbf{E}
\end{aligned}
$$

<!-- This equation needs explaining! -->

Where $z_i$ is the charge of species $i$ and $F$ is Faraday's constant. Assuming, incompressible fluid $\nabla \cdot \mathbf{v} = 0$, we can rewrite the Nerst-Planck equation in the familiar form

$$
\begin{aligned}
\frac{\partial c_i}{\partial t} + \nabla \cdot \left( -D_i \nabla c_i + \frac{z_i D_i F}{R T} c_i \mathbf{E} \right) = 0
\end{aligned}
$$
