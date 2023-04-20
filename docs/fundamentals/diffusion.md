# Fickian diffusion

## Fick's first law

Fick's first law of diffusion states that the flux of a substance is proportional to the concentration gradient of that substance. The constant of proportionality is the diffusion coefficient.

We can derive Fick's first law by considering the transport of ions between neighbouring planes.

Take two neighbouring volume elements, $A$ and $B$ separated by a distance $\delta x$. We define the number of particles that jump from one element to the next by $n\nu$, where $n$ is the number of particles and $\nu$ is the jump frequency. The flux of particles from $A$ to $B$ is given by

$$
\begin{aligned}
\delta n_{A\rightarrow B} = \frac{1}{6} \nu (n_A - n_B)
\end{aligned}
$$

Where the sixth accounts for the particles only jumping in one of 6 possible directions in 3D. Therefore the total flux out of $A$ is positive if there are more particles in $A$ than $B$. The number of particles in an elements is given by $c_X=n_X \delta V$, where $\delta V$ is the volume of the element. Consider the concentration gradient between $A$ and $B$

$$
\begin{aligned}
\frac{\partial c}{\partial x} = \frac{c_B - c_A}{\delta x} = \frac{n_B - n_A}{\delta V \delta x}
\end{aligned}
$$

Combining this with the flux equation gives

$$
\begin{aligned}
\delta n_{A\rightarrow B} = - \frac{1}{6} \nu \delta V \delta x (c_A - c_B) \\
\delta n_{A\rightarrow B} = - \frac{1}{6} \nu \delta V \delta x \frac{\partial c}{\partial x} \\
j_{A\rightarrow B} = - \frac{1}{6} \nu \delta x^2 \frac{\partial c}{\partial x}
\end{aligned}
$$

Taking the flux density, $j$, as the change in number of particles per unit area.

If we write the diffusion coefficient $D=\frac{1}{6} \nu \delta x^2$, we arrive at the general form of Fick's first law

$$
\begin{aligned}
j = - D \frac{\partial c}{\partial x}
\end{aligned}
$$

## Fick's second law

Consider two neighbouring volume elements, $A$ and $B$ separated by a distance $\delta x$ again. The flux of particles in $A$ is $j_{A}$ and the flux in $B$ is $j_{B}$.

We can write the flux in $A$ and $B$ as

$$
\begin{aligned}
j_{A} = - D \left( \frac{\partial c}{\partial x}\right)_{A} \\
j_{B} = - D \left( \frac{\partial c}{\partial x}\right)_{B}
= -D \left[\left( \frac{\partial c}{\partial x}\right)_{A} + \delta x \left( \frac{\partial^2 c}{\partial x^2}\right)_{B}\right]
\end{aligned}
$$

Now consider an increment of time $\delta t$. The change in the number of particles is the flux in minus the flux out in that time

$$
\begin{aligned}
\delta c \delta x = \delta t (j_{A} - j_{B}) \\
\end{aligned}
$$

Which leads to the general form of Fick's second law

$$
\begin{aligned}
\frac{\partial c}{\partial t} = D \frac{\partial^2 c}{\partial x^2}
\end{aligned}
$$

For a multicomponent system, the [Stefan-Maxwell equations](stefan-maxwell.md) provide a framework for deriving diffusion equations.

Useful references: [DoITPoMS](https://www.doitpoms.ac.uk/tlplib/diffusion/index.php).
