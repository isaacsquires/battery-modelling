# Concentrated electrolyte theory

Concentrated electrolyte theory builds on the dilute case, but can be applied more generally by accounting for interionic interactions. The derivation for this theory is outlined in [@Newman2012-vf] and uses the [Stefan-Maxwell](../fundamentals/stefan-maxwell.md) equations. For a more detailed derivation see [@Richardson2022-wp].

## Electrochemical potential

We consider the gradient of the electrochemical potential as the driving force for diffusion and migration. The electrochemical potential is the sum of the chemical potential and the electrostatic potential and can be written as

$$
\begin{aligned}
\mu_i = \mu_i^0 + RT \log\left(a_i\right) + z_iF\phi, \qquad
\end{aligned}
$$

Where $\mu_i^0$ is the chemical potential of the species in the absence of an electric field and $a_i$ is the activity of the species $i$.

## Stefan-Maxwell equations

The Stefan-Maxwell equations can be written in terms of the gradient of the electrochemical potential of a species and the interaction with other species in the form

$$
\begin{aligned}
c_i \nabla \mu_i = \sum_j K_{ij} (\mathbf{v_j} - \mathbf{v_i}) =  RT \sum_j \frac{c_i c_j}{c_T\mathscr{D}_{ij}}(\mathbf{v_j} - \mathbf{v_i})
\end{aligned}
$$

Where $K_{ij}$ is the interaction parameter between species $i$ and $j$, $\mathbf{v_i}$ is the velocity of species $i$ and $\mathscr{D}_{ij}$ is the diffusion coefficient describing the interaction of species $i$ and $j$, defined by

$$\mathscr{D}_{ij}=\frac{RTc_i c_j}{c_T K_{ij}}$$

This equation captures the resistances due to the interactions between all species present, not just the solvent like dilute theory. For $n$ species there are $\frac{1}{2}n(n-1)$ unique interaction parameters, as the interaction between species $i$ and $j$ is the same as the interaction between species $j$ and $i$, and self-interaction is not defined.

## Binary electrolyte

We now apply these equations to a binary electrolyte, consisting of a neutral solvent and two charged species

$$
\begin{aligned}
c_+ \nabla \mu_+ = K_{0+} (\mathbf{v_0} - \mathbf{v_+}) + K_{+-}(\mathbf{v_-} - \mathbf{v_+}) \\
c_- \nabla \mu_- = K_{0-} (\mathbf{v_0} - \mathbf{v_-}) + K_{+-}(\mathbf{v_+} - \mathbf{v_-})
\end{aligned}
$$

Noting that the ionic flux of each species is $\mathbf{N_i}=c_i\mathbf{v_i}$ then we can express the electric current density as $\mathbf{j}=Fc(\mathbf{v_+}-\mathbf{v_-})$. By making the assumption of charge neutrality ($c_+=c_-=c$), we can write the above equations in the form

$$
\begin{aligned}
c \nabla \mu_+ = K_{0+} (\mathbf{v_0} - \mathbf{v_+}) - K_{+-}\frac{\mathbf{j}}{Fc} \\
c \nabla \mu_- = K_{0-} (\mathbf{v_0} - \mathbf{v_-}) + K_{+-}\frac{\mathbf{j}}{Fc}
\end{aligned}
$$

Writing this in terms of the velocity of the ions gives

$$
\begin{aligned}
\mathbf{v_+} = \mathbf{v_0} - \frac{K_{+-}}{K_{0+}} \frac{\mathbf{j}}{Fc} - \frac{c}{K_{0+}}\nabla \mu_+ \\
\mathbf{v_-} = \mathbf{v_0} + \frac{K_{+-}}{K_{0-}} \frac{\mathbf{j}}{Fc} - \frac{c}{K_{0-}}\nabla \mu_-
\end{aligned}
$$

Combining the velocity equations and substituting the expression for the electrochemical potential along with the diffusion coefficients and rearranging gives

$$
\begin{aligned}
\mathbf{j} = -\kappa(c)\left(\nabla \phi+\frac{RT}{F}(t^0_+\nabla \log(a_+) - (1-t^0_+)\nabla\log(a_-)) \right), \qquad \nabla \cdot \mathbf{j_\phi}=0 \\
t_0^+=\frac{D_{0+}}{D_{-+}+D_{0-}}, \qquad \kappa(c)=\frac{F^2 c_T D_{+-} c (D_{0+}+D_{0-})}{RT (c (D_{0+}+D_{0-})+c_0 D_{+-})}
\end{aligned}
$$

This equation looks similar to the one arrived at in the dilute electrolyte case except with new conducitivity and transference relations, as well as a term accouting for both positive and negative ions.

We can express this in terms of the chemical potential of the electrolyte where

$$
\begin{aligned}
\mu_e(c) = \frac{\mu_- + \mu_+}{2} = \frac{\mu^0_-+\mu^0_+}{2} + RT \log((a_-a_+)^{1/2})
\end{aligned}
$$

and we define a new diffusion coefficient

$$
\begin{aligned}
\mathcal{D} = \frac{2 D_{0-}D_{0+}}{D_{0-}+D_{0+}}
\end{aligned}
$$

We can rewrite the equation for the velocity of the positive ions as

$$
\begin{aligned}
\mathbf{v_+} = \mathbf{v_0} - \frac{c_T}{RTc_0}\frac{D_{0-}D_{0+}}{D_{0+}+D_{0-}}(\nabla \mu_+ + \nabla \mu_-) + \frac{t_+^0}{Fc}\mathbf{j} \\
\mathbf{v_+} = \mathbf{v_0} - \frac{c_T}{RTc_0}\mathcal{D}\nabla \mu_e + \frac{t_+^0}{Fc}\mathbf{j}
\end{aligned}
$$

When we substitute this into the continuity equation for the positive ions

$$
\begin{aligned}
\frac{\partial c}{\partial t} + \nabla \cdot (c\mathbf{v_+}) = 0
\end{aligned}
$$

We arrive at

$$
\begin{aligned}
\frac{\partial c}{\partial t} + \nabla \cdot \left(-\frac{c_T}{RTc_0}c\mathcal{D}\nabla \mu_e \right) + \nabla \cdot (c\mathbf{v_0})= - \frac{t_+^0}{Fc}\mathbf{j}
\end{aligned}
$$

This can be compared to the [dilute electrolyte case](dilute-electrolyte.md), where we now have a new term as we have not assumed zero fluid velocity.
