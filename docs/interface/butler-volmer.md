# Butler-Volmer equation

The Butler-Volmer equation describes the current density due to the intercalation reaction at the electrode and electrolyte interface. The derivation set out here predominantly comes from [@Bockris1998-sa]

Consider an ion in solution $A_+$ that must travel into the electrode and undergo electronation $A_+ + e^- \rightarrow D$. The ion must traverse the double-layer, overcoming an activation energy barrier

<!-- Plot of a potential energy landscape -->

This process has similarities to diffusion. The ion is jumping from one site to another with and must overcome an energy barrier. Consider a case where there is no electric field, this process is purely diffusive with the rate of this process governed by an Arrhenius equation

$$
\begin{aligned}
\mathbf{v_c} = k_c c_{A_+} \\
k_c = A_c \exp\left(-\frac{\Delta G_c^0}{RT}\right)
\end{aligned}
$$

where $v_c$ is the velocity of the reaction (i.e. how many moles per second are being transferred), $c$ is the concentration of $A_+$ ions in solution, $k_c$ is the rate constant for this purely chemical process, $A$ is the pre-exponential factor and $\Delta G_c^0$ is the free energy of activation with no electric field. Now we must consder the application of an electric field. The ion must do work to overcome the electric field as well as the activation energy barrier. The total free energy of activation now has an additional electronic component

$$
\begin{aligned}
\Delta G^0 &= \Delta G_c^0 + \Delta G_e^0 \\
\Delta G_e^0 &= \beta F \Delta \phi \\
\end{aligned}
$$

$\Delta \phi$ is the potential difference between the electrode and the electrolyte, but the contribution to the free energy of activation does not include all of this. Therefore we introduce $\beta$, the _symmetry factor_, which tells us how much of the step in potential contributes to altering the activation free energy. This leaves with the following expression for the forward current density

$$
\begin{aligned}
\mathbf{v_e} &= k_e c_{A_+} \\
&= \mathbf{v_c} \exp\left(\frac{-\beta F \Delta \phi}{RT}\right) \\
\mathbf{j_f} &= F \mathbf{v_e} \\
&= F k_c c_{A_+} \exp\left(\frac{-\beta F \Delta \phi}{RT}\right)
\end{aligned}
$$

Now consider the reverse reaction, where the species is de-electronated and moving back into the electrolyte. The species must now move through the remainder of the potential $(1-\beta)\Delta \phi$ and the field now assists ion transfer. The current density for this reverse process is

$$
\begin{aligned}
\mathbf{j_r} = F k_c c_D \exp\left(\frac{(1-\beta) F \Delta \phi}{RT}\right)
\end{aligned}
$$

Note the concentration here is $c_D$, the concentration of $D$ atoms in the electrode. Without an applied field, the forward and reverse currents eventually become equal and the charge in the solution and the electrode become constant, along with the field across the interface - the equilibrium potential difference, $\Delta \phi_e$. The current at this point is termed the _equilibrium exchange current density_ and is given by

$$
\begin{aligned}
i_0 = F k_c c_{A_+} \exp\left(\frac{-\beta F \Delta \phi_e}{RT}\right)= F k_c c_D \exp\left(\frac{(1-\beta) F \Delta \phi_e}{RT}\right)
\end{aligned}
$$

Now consider when the system is not in equilibrium. The current density is now the difference between the forward and reverse currents

$$
\begin{aligned}
\mathbf{j} &= \mathbf{j}_f - \mathbf{j}_r \\
&= F k_c c_{A_+} \exp\left(\frac{-\beta F \Delta \phi}{RT}\right) - F k_c c_D \exp\left(\frac{(1-\beta) F \Delta \phi}{RT}\right)
\end{aligned}
$$

We now write the potential difference in terms of the equilibrium potential and the overpotential

$$
\begin{aligned}
\Delta \phi &= \phi_e + \eta
\end{aligned}
$$

where $\eta$ is the overpotential. Combining these equations with $i_0$ leaves us with the **Butler-Volmer equation**

$$
\begin{aligned}
\mathbf{j} &= i_0 \left( \exp\left(\frac{(1-\beta)F \eta}{RT}\right) - \exp\left(\frac{-\beta F \eta}{RT}\right)\right)
\end{aligned}
$$
