# Stefan-Maxwell equations

The Stefan-Maxwell equations describes diffusive flux in a multi-component system. The equations account for inter-species interactions. The derivation outlined here is taken from [@Bothe2011-ix].

## Motivation

Starting from the continuity equation for mass, we can describe the reaction-diffusion dynamics of each species with

$$
\begin{aligned}
\frac{\partial c_i}{\partial t} + \nabla \cdot (c_i\mathbf{v} + \mathbf{N}_i) = r_i
\end{aligned}
$$

where $c_i$ is the concentration of species $i$, $\mathbf{N}_i$ is the flux of species $i$ and $r_i$ is the rate of change of molar mass of species $i$. We can write the flux as

$$
\begin{aligned}
\mathbf{N}_i = c_i (\mathbf{v_i} - \mathbf{v})
\end{aligned}
$$

where $\mathbf{v_i}$ is the velocity of species $i$ and $\mathbf{v}$ is the molar averaged velocity. We consider the case where $\mathbf{v}=0$, the above equations can be written as

$$
\begin{aligned}
\frac{\partial c_i}{\partial t} + \nabla \cdot \mathbf{N_i} = r_i
\end{aligned}
$$

The individual fluxes of each species need to be modelled by constitutive equations. In Fick's Law, these are given by

$$
\begin{aligned}
\mathbf{N}_i = -D_i \nabla c_i
\end{aligned}
$$

where $D_i$ is the diffusion constant of species $i$. This does not account for inter-species interactions. Instead we can write the flux more generally as

$$
\begin{aligned}
\mathbf{N}_i = -\sum_j D_{ij} \nabla c_j
\end{aligned}
$$

where $D_{ij}$ is the diffusion constant of species $i$ in the presence of species $j$. This forms the motivation for the Stefan-Maxwell equations, which give us a way to model the diffusion constants $D_{ij}$.

## Deriving the Stefan-Maxwell equations

We start by considering inter-species force balances. Consider a thermodynamic driving force $\mathbf{d_i}$ acting on species $i$. We will use molar fractions $x_i=c_i/c_T$. We can write the driving force as

$$
\begin{aligned}
\mathbf{d_i} = \frac{x_i}{RT} \nabla \mu_i
\end{aligned}
$$

Where the the electrochemical potential can be written as

$$
\begin{aligned}
\mu_i = \mu_i^0 + RT \log\left(a_i\right)
\end{aligned}
$$

We assume that the mutual friction force between species is proportional to their relative velocity and their molar fractions, and can be written as

$$
\begin{aligned}
\mathbf{F_ij} = f_{ij}x_i x_j (\mathbf{v_i} - \mathbf{v_j})
\end{aligned}
$$

where $f_{ij}$ is the friction coefficient between species $i$ and $j$. We also assume that the driving force is balanced by the frictional force, leading to

$$
\begin{aligned}
\mathbf{d_i} = -\sum_{j\neq i}f_{ij}x_i x_j (\mathbf{v_i} - \mathbf{v_j})
\end{aligned}
$$

Relating this to the electrochemical potential we get

$$
\begin{aligned}
\frac{x_i}{RT} \nabla \mu_i = -\sum_{j\neq i}f_{ij}x_i x_j (\mathbf{v_i} - \mathbf{v_j})
\end{aligned}
$$

Which written in terms of concentration and defining the diffusion coefficients $\mathcal{D_{ij}}=1/f_{ij}$ leaves us with the familiar form of the Stefan-Maxwell equations

$$
\begin{aligned}
c_i \nabla \mu_i = RT\sum_{j}\frac{c_i c_j}{c_T\mathcal{D_{ij}}} (\mathbf{v_j} - \mathbf{v_i})
\end{aligned}
$$
