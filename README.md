## Modelling XRD intensity

$\ce{ La_{\frac{2}{3}}TiO_{3} }$ is formulated as $\mathrm{La1_{x}La2_{\frac{4}{3}-x}TiO_{3}}$, with the following structure factor basis:
```
La1 = (0,0,0.5)  
La2 = (0,0,0)  
Ti1 = (0.5,0.5,0.2594)  
Ti2 = (0.5,0.5,1-0.2594)  
O1 = (0.5,0.5,0.5)  
O2 = (0,0.5,0.23)  
O3 = (0.5,0,0.2412)  
O4 = (0.5,0.5,0)  
O5 = (0,0.5,1-0.23)  
O6 = (0.5,0,1-0.2412)
```
The atoms `La1,La2,Ti1,O1,O2,O3,O4` are sufficient to generate the $\ce{ La_{\frac{2}{3}}TiO_{3} }$ orthorhombic lattice under *Pmmm* symmetry; their atomic positional factors and the corresponding doubled perovskite lattice parameters were taken from [Kim et al](https://www.sciencedirect.com/science/article/pii/S0022459684713727). `Ti2,O5,O6` are added to the structure factor to complete unit cell stoichiometry.

The structure factor $S_{hkl}$ is formulated as a function of $x$,
$$S_{hkl}=(x)F_{\text{La1}}+\left( \frac{4}{3}-x \right)F_{\text{La2}}+F_{\text{Ti}}+F_{\text{O}}$$ where $F_{hkl}$ for each atom contains its angle-dependent atomic form factor $f_{hkl}$ and geometrical information on all of its $j$ basis positions:
$$F_{hkl} = f_{hkl}\sum_{j} \exp(2\pi i(hx_{j}+ky_{j}+lz_{j})).$$

Here, the atomic form factor includes only coherent scattering; anomalous dispersion is neglected. The coherent scattering as a function of $2\theta$ is analytically approximated by the 11-parameter sum of 5 Gaussians,
$$f \left(\frac{\sin \theta}{\lambda} \right) = \sum _{i=1}^N a_i \exp \left ( −b_i \frac {\sin ^2 \theta }{ \lambda ^2} \right ) + c$$
with parameters formulated by [Waasmaier & Kirfel](https://doi.org/10.1107/S0108767394013292). 

After obtaining structure factors, powder XRD intensity can be obtained as
$I_{hkl}=\text{Multiplicity}_{hkl} \cdot \text{Polarization}\cdot\text{Lorentz}\cdot |S_{hkl}|^{2},$

where ${1+\cos(2\theta)^{2}}$ is the polarization factor ([XRD book](https://onlinelibrary.wiley.com/iucr/itc/Cb/ch6o2v0001/sec6o2o2/)), and ${\sin(\theta)^{2}\cos(\theta)}$ is the powder Lorentz factor ([Lorentz-polarization](https://doi.org/10.1346/CCMN.1986.0340402)).

We verify that this model is thus far equivalent to RIETAN-FP by calculating the structure factor and peak intensities of $\ce{ SrTiO_{3} }$, using the crystallographic information file from [Schmidbauer et al](https://10.1107/S0108768111046738). The results of our model and RIETAN-FP are identical.

The modified intensity equation for calculating thin film peak intensity is 
$$I_{hkl}=\frac{{1+\cos(2\theta)^{2}}}{\sin(\theta)\cos(\theta)}\cdot |S_{hkl}|^{2}$$
where the multiplicity factor has become uniformly 1 for all $hkl$ and ${\sin(\theta)\cos(\theta)}$ is the single crystal Lorentz factor ([Lorentz-polarization](https://doi.org/10.1346/CCMN.1986.0340402)). 