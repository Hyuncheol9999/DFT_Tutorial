# Tutorials on Double Field Theory: Part II
### Hyun-Cheol Kim (kimhc8888@sogang.ac.kr)
Since the Markdown document in GitHub has a length limit to be rendered (especially for equations), I continue my tutorial here in Part II.


## VI. Doubled String

Since DFT originates from the string theory, the string worldsheet action must be written in terms of the generalized metric (not the Riemannian metric).
In this section, we discuss how to construct the string theory in DFT, and its physical meaning.


### 1. Basis Vector in DFT

In general relativity, the basis vectors are $\frac{\partial}{\partial x^{\mu}}$ and the basis 1-forms are $\mathrm{d}x^{\mu}$, as shown below:

$$A=A^{\mu}\frac{\partial}{\partial x^{\mu}},\qquad\omega=\omega_{\mu}\mathrm{d}x^{\mu}.$$

In DFT, on the other hand, vectors and 1-forms are not distinguished.
For example, in the generalized Lie derivative, the operation on vectors and the operation on 1-forms take the same form.
Therefore, in DFT, the basis vectors are denoted by $\mathrm{D}x_{A}$, and the basis 1-forms are denoted by $\mathrm{D}x^{A}$, obtained by raising the index with the $O(D,D)$-invariant metric.

$$T=T^{A}\mathrm{D}x_{A}=T_{A}\mathrm{D}x^{A}.$$

As we saw earlier, there is a gauge symmetry in doubled spacetime.
Therefore, we can define the basis vectors by treating $\mathrm{D}$ as a kind of gauge covariant derivative and introducing a gauge potential $a^{A}$.

$$\mathrm{D}x^{A}=\mathrm{d}x^{A}-a^{A}.$$

Now, let us consider the following 1-form for a function $f$:

$$\mathrm{d}f=(\partial_{A}f)\mathrm{D}x^{A}=(\partial_{A}f)\mathrm{d}x^{A}-a^{A}\partial_{A}f.$$

Since the chain rule $\mathrm{d}f=(\partial_{A}f)\mathrm{d}x^{A}$ must hold for the left-hand side of the above equation, we obtain the following:

$$a^{A}\partial_{A}=a^{\mu}\partial_{\mu}=0\qquad\implies\qquad a^{\mu}=0\qquad\implies\qquad a^{A}=(a_{\mu},0).$$

(In the above equation, we used the section condition $\partial^{\mu}=0$.)
For the gauge potential, the diffeomorphism transformation is defined as follows:

$$\delta_{\xi}a^{A}=\mathrm{D}x^{B}\partial^{A}\xi_{B}.$$

Then, after a short calculation, we obtain the following:

$$\delta_{\xi}(\mathrm{D}x^{A})=\mathrm{D}x^{B}(\partial_{B}\xi^{A}-\partial^{A}\xi_{B}).$$

As a result, we can confirm that the diffeomorphism transformation coincides with the generalized Lie derivative.

$$\begin{aligned}
\delta_{\xi}T&=\delta_{\xi}\big(T_{A}(x)\mathrm{D}x^{A}\big)
\\
&=T_{A}(x+\xi)(\mathrm{D}x^{A}+\delta_{\xi}\mathrm{D}x^{A})-T_{A}(x)\mathrm{D}x^{A}
\\
&=(\xi^{B}\partial_{B}T_{A}-T^{B}\partial_{B}\xi_{A}+T^{B}\partial_{A}\xi_{B})\mathrm{D}x^{A}
\\
&=(\hat{L}\_{\xi}T_{A})\mathrm{D}x^{A}.
\end{aligned}$$


### 2. Doubled Point Particle

In most cases, the concept of DFT basis vectors only improves mathematical completeness and is not needed in physical calculations.
The only exception is when we deal with physical objects such as point particles or strings, where these concepts play a physical role.
For a point particle, the DFT basis vectors should be pulled back to the one-dimensional worldline (with coordinate $\tau$):

$$\mathrm{D}_{\tau}x^{A}=\frac{dx^{A}}{d\tau}-a^{A}.$$

Applying the section condition, we notice that

$$\mathrm{D}\_{\tau}x^{A}=\left(\frac{d\tilde{x}\_{\mu}}{d\tau}-a_{\mu},\frac{dx^{\mu}}{d\tau}\right).$$

Since $\tilde{x}\_{\mu}$ is independent of physics due to the section condition, we absorb it into $a_{\mu}$:

$$\mathrm{D}\_{\tau}x^{A}=\left(-a_{\mu},\frac{dx^{\mu}}{d\tau}\right).$$

Using the einbein $e$ in the worldline, the Lagrangian of a point particle can be written in terms of the generalized metric:

$$\begin{aligned}
L&=\frac{1}{2e}(H_{AB}\mathrm{D}\_{\tau}x^{A}\mathrm{D}\_{\tau}x^{B}-m^{2}e^{2})
\\
&=\frac{1}{2e}\left(H_{\mu\nu}\frac{dx^{\mu}}{d\tau}\frac{dx^{\nu}}{d\tau}-2H_{\mu}{}^{\nu}\frac{dx^{\mu}}{d\tau}a_{\nu}+H^{\mu\nu}a_{\mu}a_{\nu}-m^{2}e^{2}\right),
\end{aligned}$$

where we used $H_{\mu}{}^{\nu}=H^{\nu}{}\_{\mu}$.
To utilize the Riemannian parametrization, we abbreviate (for convenience) as $B_{\mu\nu}\frac{dx^{\nu}}{d\tau}=b_{\mu}$ and $a^{\mu}=g^{\mu\nu}a_{\nu}$:

$$\begin{aligned}
L&=\frac{1}{2e}\left(g_{\mu\nu}\frac{dx^{\mu}}{d\tau}\frac{dx^{\nu}}{d\tau}+b_{\mu}b^{\mu}+2b_{\mu}a^{\mu}+a_{\mu}a^{\mu}-m^{2}e^{2}\right)
\\
&=\frac{1}{2e}\left(g_{\mu\nu}\frac{dx^{\mu}}{d\tau}\frac{dx^{\nu}}{d\tau}-m^{2}e^{2}\right),
\end{aligned}$$

where we integrated out the auxiliary field $a^{\mu}$. The result matches the standard Lagrangian of a point particle.


### 3. Doubled String

We first define the worldsheet lightcone coordinates as

$$\sigma=\sigma^{0}+\sigma^{1},\qquad\overline{\sigma}=\sigma^{0}-\sigma^{1}.$$

Notice that we assume the Lorentzian (not Euclidean) worldsheet. The worldsheet derivatives are denoted as

$$\partial=\frac{\partial}{\partial\sigma},\qquad\overline{\partial}=\frac{\partial}{\partial\overline{\sigma}}.$$

Then, the DFT basis vector is pulled back to the worldsheet as

$$\mathrm{D}x^{A}=(-a_{\mu},\partial x^{\mu}),\qquad\overline{\mathrm{D}}x^{A}=(-\overline{a}_{\mu},\overline{\partial}x^{\mu}).$$

Based on the above expressions, the worldsheet Lagrangian can be written in terms of the generalized metric:

$$L=\frac{1}{4\pi\alpha'}\left(-\frac{1}{2}\sqrt{-h}h^{\alpha\beta}\mathrm{D}\_{\alpha}x^{A}\mathrm{D}\_{\beta}x^{B}H_{AB}+\epsilon^{\alpha\beta}a_{\alpha A}\mathrm{D}_{\beta}x^{B}\right),$$

where $h_{\alpha\beta}$ is the worldsheet metric, and the worldsheet Levi--Civita symbol is defined as

$$\epsilon^{01}=1,\qquad\epsilon^{\sigma\overline{\sigma}}=-1.$$

To simplify, we impose the worldsheet conformal gauge:

$$\sqrt{-h}h^{\alpha\beta}=\begin{pmatrix}0&-1
\\
-1&0\end{pmatrix}.$$

Then, the worldsheet Lagrangian of doubled string reads as

$$\begin{aligned}
L&=\frac{1}{4\pi\alpha'}(H_{AB}\mathrm{D}x^{A}\overline{\mathrm{D}}x^{B}+\overline{a}\_{A}\mathrm{D}x^{A}-a_{A}\overline{\mathrm{D}}x^{A})
\\
&=\frac{1}{4\pi\alpha'}\left[H_{\mu\nu}\partial x^{\mu}\overline{\partial}x^{\nu}-H_{\mu}{}^{\nu}(a_{\nu}\overline{\partial}x^{\mu}+\overline{a}_{\nu}\partial x^{\mu})+H^{\mu\nu}a\_{\mu}\overline{a}\_{\nu}+\overline{a}\_{\mu}\partial x^{\mu}-a_{\mu}\overline{\partial}x^{\mu}\right].
\end{aligned}$$

Likewise, we abbreviate $B_{\mu\nu}\partial x^{\nu}=b_{\mu}$ and $B_{\mu\nu}\overline{\partial}x^{\nu}=\overline{b}_{\mu}$ for the Riemannian parametrization:

$$\begin{aligned}
L&=\frac{1}{4\pi\alpha'}\left[g_{\mu\nu}\partial x^{\mu}\overline{\partial}x^{\nu}+b_{\mu}\overline{b}{}^{\mu}+a_{\mu}(\overline{b}{}^{\mu}-\overline{\partial}x^{\mu})+\overline{a}\_{\mu}(b^{\mu}+\partial x^{\mu})+a_{\mu}\overline{a}{}^{\mu}\right]
\\
&=\frac{1}{4\pi\alpha'}\left[2g_{\mu\nu}\partial x^{\mu}\overline{\partial}x^{\nu}+b_{\mu}\overline{\partial}x^{\mu}-\overline{b}\_{\mu}\partial x^{\mu}+(a\_{\mu}+b\_{\mu}+\partial x\_{\mu})(\overline{a}{}^{\mu}+\overline{b}{}^{\mu}-\overline{\partial}x^{\mu})\right]
\\
&=\frac{1}{4\pi\alpha'}(2g_{\mu\nu}\partial x^{\mu}\overline{\partial}x^{\nu}+b_{\mu}\overline{\partial}x^{\mu}-\overline{b}\_{\mu}\partial x^{\mu})
\\
&=\frac{1}{2\pi\alpha'}(g_{\mu\nu}+B_{\mu\nu})\partial x^{\mu}\overline{\partial}x^{\nu},
\end{aligned}$$

where we integrated out the auxiliary field $a^{\mu}$. This matches the standard Polyakov action:

$$L_{\mathrm{Polyakov}}=-\frac{1}{4\pi\alpha'}\left(\sqrt{-h}h^{\alpha\beta}\partial_{\alpha}x^{\mu}\partial_{\beta}x^{\nu}g_{\mu\nu}+\epsilon^{\alpha\beta}\partial_{\alpha}x^{\mu}\partial_{\beta}x^{\nu}B_{\mu\nu}\right).$$


### 4. Non-Riemannian Background

Recall the Lagrangian of the doubled point particle:

$$L_{\mathrm{particle}}=\frac{1}{2e}\left(H_{\mu\nu}\frac{dx^{\mu}}{d\tau}\frac{dx^{\nu}}{d\tau}-2H_{\mu}{}^{\nu}\frac{dx^{\mu}}{d\tau}a_{\nu}+H^{\mu\nu}a_{\mu}a_{\nu}-m^{2}e^{2}\right).$$

In the non-Riemannian parametrization $H^{\mu\nu}=0$, we have

$$L_{\mathrm{particle}}=\frac{1}{2e}\left(H_{\mu\nu}\frac{dx^{\mu}}{d\tau}\frac{dx^{\nu}}{d\tau}-2H_{\mu}{}^{\nu}\frac{dx^{\mu}}{d\tau}a_{\nu}-m^{2}e^{2}\right).$$

Now, the auxiliary field $a_{\mu}$ becomes the Lagrange multiplier, giving

$$\frac{dx^{\mu}}{d\tau}=0.$$

Hence, particles do not move in the non-Riemannian geometry. For the doubled string, we have

$$L_{\mathrm{string}}=\frac{1}{4\pi\alpha'}\left[H_{\mu\nu}\partial x^{\mu}\overline{\partial}x^{\nu}-H_{\mu}{}^{\nu}(a_{\nu}\overline{\partial}x^{\mu}+\overline{a}_{\nu}\partial x^{\mu})+H^{\mu\nu}a\_{\mu}\overline{a}\_{\nu}+\overline{a}\_{\mu}\partial x^{\mu}-a_{\mu}\overline{\partial}x^{\mu}\right].$$

Here, we substitute the following non-Riemannian background:

$$H_{AB}=\begin{pmatrix}0&0&1&0
\\
0&0&0&-1
\\
1&0&0&0
\\
0&-1&0&0\end{pmatrix}.$$

The resulting theory is the chiral string;

$$L_{\mathrm{string}}=\frac{1}{2\pi\alpha'}(\overline{a}\_{2}\partial x^{2}-a_{1}\overline{\partial}x^{1}),$$

which means the string does not have the center-of-mass motion, but the chiral behavior exists:

$$\partial x^{2}=\overline{\partial}x^{1}=0.$$


## VII. Projector

The generalized metric has the property that its square equals 1, as shown below:

$$H_{A}{}^{B}H_{B}{}^{C}=\delta_{A}{}^{C}.$$

Hence, it naturally defines the projectors:

$$P_{AB}=\frac{1}{2}(J_{AB}+H_{AB}),\qquad\overline{P}_{AB}=\frac{1}{2}(J\_{AB}-H\_{AB}).$$

We can easily observe the projection properties:

$$P_{A}{}^{B}P_{B}{}^{C}=P_{A}{}^{C},\qquad\overline{P}_{A}{}^{B}\overline{P}_{B}{}^{C}=\overline{P}_{A}{}^{C},\qquad P\_{A}{}^{B}\overline{P}{}_{B}{}^{C}=0.$$

From the definition of projectors, we find that

$$J_{AB}=P_{AB}+\overline{P}\_{AB},\qquad H_{AB}=P_{AB}-\overline{P}\_{AB}.$$

Using $J_{AB}=P_{AB}+\overline{P}\_{AB}$, the vectors can always be decomposed as

$$T_{A}=P_{AB}T^{B}+\overline{P}\_{AB}T^{B}.$$

And, the matrices can always be decomposed as follows:

$$M_{AB}=(PMP)_{AB}+(\overline{P}M\overline{P})\_{AB}+(PM\overline{P})\_{AB}+(\overline{P}MP)\_{AB}.$$

Notice that the generalized metric can also be decomposed as above.
Imposing the constraint $H_{A}{}^{B}H_{B}{}^{C}=\delta_{A}{}^{C}$, we find that

$$H_{AB}=(PHP)_{AB}+(\overline{P}H\overline{P})\_{AB}.$$

That is, $(PH\overline{P})\_{AB}=(\overline{P}HP)\_{AB}=0$.
The infinitesimal variation of the projectors are given as

$$\delta H_{AB}=2\delta P_{AB}=-2\delta\overline{P}_{AB}.$$

We have the same relations for the derivatives: $\partial_{C}H_{AB}=2\partial_{C}P_{AB}=-2\partial_{C}\overline{P}\_{AB}$. From the constraint $H_{A}{}^{B}H_{B}{}^{C}=\delta_{A}{}^{C}$, we notice that

$$\delta H_{AB}=(P\delta H\overline{P})\_{AB}+(\overline{P}\delta HP)\_{AB}.$$


### 1. DFT Equations of Motion

In general relativity, the Einstein field equations are simply given as follows:

$$\frac{\delta S}{\delta g^{\mu\nu}}=0.$$

However, in DFT, the generlized metric is constrained as $H_{A}{}^{B}H_{B}{}^{C}=\delta_{A}{}^{C}$, which means that the equations of motion are given as

$$\left.\frac{\delta S}{\delta H^{AB}}\right|_{H_{I}{}^{J}H_{J}{}^{K}=\delta_{I}{}^{K}}=0.$$

Since this constraint can be recast as $\delta H_{AB}=(P\delta H\overline{P})\_{AB}+(\overline{P}\delta HP)\_{AB}$, the DFT equations of motion can be written as follows:

$$P_{A}{}^{C}\frac{\delta S}{\delta H^{CD}}\overline{P}{}^{D}{}_{B}=0.$$


### 2. DFT Vielbein



















## VIII. DFT Christoffel Connection

In general relativity, the connection with the metric compatibility and the torsion-free condition, is called the Levi-Civita connection.
And, the component of the Levi-Civita connection in coordinate bases, is called the Christoffel symbol.




## IX. DFT Curvature






## X. Einstein Double Field Equations




## XI. Linear Perturbation





$$\delta_{\mathrm{p}}^{2}H_{AB}=\delta_{\mathrm{p}}h_{AB}=-\frac{1}{2}h^{CD}\delta(H_{AC}H_{BD}).$$




1
