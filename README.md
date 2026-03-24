# Transport-of-planar-structures
MD data for the scattering angle distributions of planar molecules along with the determination of diffusion coefficients using gas-kinetic theory, along with Green-Kubo calculations for the diffusion coefficients of planar structures 


# File format

**PAH_scatter**\

Folder for all the MD scattering angle distributions. Please access this folder to view the scattering angle distributions for nitrogen-planar structure (benzene, naphthalene, phenanthrene, pyrene, coronene, ovalene) collisions.\

The data is grouped by temperature and the files scatter_data_i_relvel_gin.txt provides distributions for a list of 350 incident scattering angles (denoted by index i) and relative velocity given by gin. The data in these .txt files have 9 columns organized as\

gin  thetain  phiin  gout  thetout  phiout  x  y  z\

The incident relative velocity is given by gin[sin(thetain)*cos(phiin),sin(thetain)*sin(phiin),cos(thetain)] and the outgoing relative velocity is gout[cos(thetaout)*cos(phiout),cos(thetaout)*sin(phiout),sin(thetaout)] where gin and gout are in the units of Angstrom/ps; x y and z are the positions of the molecules in the collision cross-section in Angstroms.\

**PAH_GreenKubo**\

Folder of the diffusion coefficients evaluated using the Green-Kubo approach. Files D1.txt, D2.txt, .., D5.txt represent the diffusion coefficient evaluations for 5 independent simulation runs. The data has two columns - \
```math
$t$  $D_{\text{PAH}-\text{N}_2}(t)$\
```
where t is the time elapsed in fs and f(t) is the function given by,\
```math
D_{\text{PAH}-\text{N}_2}(t) = X_{\text{N}_2}\Lambda_{\text{PAH}}(t) + X_1\Lambda_{\text{N}_2}(t) + \frac{X_{\text{N}_2}}{X_{\text{PAH}}}\Lambda_{\text{PAH}-\text{PAH}}(t) + \frac{X_{\text{PAH}}}{X_{\text{N}_2}}\Lambda_{{\text{N}_2}-{\text{N}_2}}(t) - 2\Lambda_{\text{PAH}-{\text{N}_2}}(t)
```
where\
```math
\Lambda_{s}(t) &= \frac{1}{3}\int_0^{t}\langle \boldsymbol{v}^{s}_i(0)\cdot\boldsymbol{v}^{s}_i(\tau)\rangle\,d\tau,\\
\Lambda_{ss}(t) &= \frac{1}{3}\int_0^{t}\langle \boldsymbol{v}^{s}_i(0)\cdot\boldsymbol{v}^{s}_j(\tau)\rangle\,d\tau\,\,(i\neq j)\\
\Lambda_{sr}(t) &= \frac{1}{3}\int_0^{t}\langle \boldsymbol{v}^{s}_i(0)\cdot\boldsymbol{v}^{r}_j(\tau)\rangle\,d\tau\,\,(s\neq r),\\
```
and as $t\rightarrow\infty$, we obtain $D_{\text{PAH}-\text{N}_2}(t)\rightarrow D_{\text{PAH}-\text{N}_2}$.
