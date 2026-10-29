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

As mentioned, the generalized metric cannot always be diagonalized with nonzero eigenvalues (since it can be non-Riemannian).
On the other hand, the projectors can always be diagonalized into flat metric:

$$P_{AB}=V_{Ap}V_{Bq}\eta^{pq},\qquad\overline{P}\_{AB}=\overline{V}\_{A\overline{p}}\overline{V}\_{B\overline{q}}\overline{\eta}^{\overline{p}\overline{q}},$$

where $\overline{\eta}^{\overline{p}\overline{q}}=-\eta^{pq}$. The corresponding similarity transformation matrices $V_{Ap}$ and $\overline{V}_{A\overline{p}}$ are called the DFT vielbein.
Recall that, in general relativity, the Riemannian vielbein is defined as

$$g_{\mu\nu}=\eta_{pq}e^{p}{}_{\mu}e^{q}{}_{\nu}.$$

In the matrix form, its inverse and transpose are

$$e^{\mu}{}_{p}=(e^{p}{}_{\mu})^{-1},\qquad e\_{\mu}{}^{p}=(e^{p}{}\_{\mu})^{T}.$$

In addition, we define the barred vielbein:

$$g_{\mu\nu}=-\overline{\eta}\_{\overline{p}\overline{q}}\overline{e}^{\overline{p}}{}\_{\mu}\overline{e}^{\overline{q}}{}\_{\nu}.$$

It is straightforward to notice that

$$e^{p\mu}=g^{\mu\nu}e^{p}{}\_{\nu},\qquad e_{p\mu}=\eta_{pq}e^{q}{}_{\mu}.$$

On the other hand, for the barred vielbein, the rules are different:

$$\overline{e}^{\overline{p}\mu}=-g^{\mu\nu}\overline{e}^{\overline{p}}{}\_{\nu},\qquad\overline{e}\_{\overline{p}\mu}=\overline{\eta}\_{\overline{p}\overline{q}}\overline{e}^{\overline{q}}{}\_{\mu}.$$

Based on these, the Riemannian parametrization of the DFT vielbeins is given as

$$V_{Ap}=\frac{1}{\sqrt{2}}\begin{pmatrix}e^{\mu}{}\_{p}
\\
e_{\mu p}+B_{\mu p}\end{pmatrix},\qquad
\overline{V}\_{A\overline{p}}=\frac{1}{\sqrt{2}}\begin{pmatrix}\overline{e}^{\mu}{}\_{\overline{p}}
\\
\overline{e}\_{\mu\overline{p}}+B_{\mu\overline{p}}\end{pmatrix},$$

where $B_{\mu p}=B_{\mu\nu}e^{\nu}{}\_{p}$ and $B_{\mu\overline{p}}=B_{\mu\nu}\overline{e}^{\nu}{}\_{\overline{p}}$.
In the non-Riemannian parametrization, finding the DFT vielbein requires some calculation.


### 3. DFT Gamma Matrices

The gamma matrix is defined based on the flat metric:

$$\lbrace\gamma^{p},\gamma^{q}\rbrace=2\eta^{pq}.$$

This is called the $SO(1,D-1)$ gamma matrix, since the flat metric can be diagonalized as

$$\eta^{pq}=\mathrm{diag}(-1,1,\cdots,1).$$

In DFT, we have another kind of flat metric $\overline{\eta}{}^{\overline{p}\overline{q}}=-\eta^{pq}$.
The corresponding gamma matrix is defined as

$$\lbrace\overline{\gamma}{}^{\overline{p}},\overline{\gamma}{}^{\overline{q}}\rbrace=2\overline{\eta}{}^{\overline{p}\overline{q}}.$$

This is called the $SO(D-1,1)$ gamma matrix, since the flat metric $\overline{\eta}{}^{\overline{p}\overline{q}}$ can be diagonalized as

$$\overline{\eta}{}^{\overline{p}\overline{q}}=\mathrm{diag}(1,-1,\cdots,-1).$$

Accordingly, DFT has an $SO(1,D-1)$ spinor $\psi$ and an $SO(D-1,1)$ spinor $\psi'$, which forms the $N=2$ supersymmetry of type-II string theory.
Each spinor acts to the gamma matrices as

$$\gamma^{p}\psi,\qquad\overline{\gamma}{}^{\overline{p}}\psi'.$$


### 4. Trace of Projector

In the Riemannian parametrization, it is straightforward to show that

$$J^{AB}H_{AB}=\delta^{\mu}{}\_{\nu}H_{\mu}{}^{\nu}+\delta_{\mu}{}^{\nu}H^{\mu}{}\_{\nu}=\delta^{\mu}{}\_{\nu}(Bg^{-1})_{\mu}{}^{\nu}-\delta_{\mu}{}^{\nu}(g^{-1}B)^{\mu}{}\_{\nu}=0.$$

Hence,

$$J^{AB}P_{AB}=J^{AB}\overline{P}\_{AB}=\frac{1}{2}J^{AB}J_{AB}=D.$$

For the non-Riemannian parametrization, we consider

$$H_{AB}=\begin{pmatrix}0&0&1&0
\\
0&0&0&-1
\\
1&0&0&0
\\
0&-1&0&0\end{pmatrix}
\qquad\implies\qquad
J^{AB}H_{AB}=0.$$

However, there exists another non-Riemannian case where $J^{AB}H_{AB}\ne0$:

$$H_{AB}=\begin{pmatrix}0&0&1&0
\\
0&0&0&1
\\
1&0&0&0
\\
0&1&0&0\end{pmatrix}
\qquad\implies\qquad
J^{AB}H_{AB}=4.$$

Since $J^{AB}H\_{AB}$ always takes integer values, it cannot change continuously, and thus unless $J^{AB}H\_{AB}=0$, its value would have to change discontinuously.
Therefore, the condition $J^{AB}H\_{AB}=0$ is essential for Riemannian geometry and non-Riemannian geometry to coexist.
Of course, when non-Riemannian geometry exists on its own, $J^{AB}H\_{AB}\ne0$ is possible.
In this tutorial, however, we will always assume $J^{AB}H\_{AB}=0$, and therefore $J^{AB}P\_{AB}=D$.


### 5. Useful Shorthand Notation

From now, we use the following shorthand notation for the projected indices:

$$T_{\mathring{A}}=P_{AB}T^{B},\qquad T_{\overline{A}}=\overline{P}\_{AB}T^{B}.$$

Then, the decomposition of vector can be written as

$$T_{A}=T_{\mathring{A}}+T_{\overline{A}}.$$

And, a matrix can be decomposed as follows:

$$M_{AB}=M_{\mathring{A}\mathring{B}}+M_{\overline{A}\overline{B}}+M_{\mathring{A}\overline{B}}+M_{\overline{A}\mathring{B}}.$$

- Example

Let us compute the following expression:

$$\delta H_{AB}\delta H^{AB}=(\delta H_{\mathring{A}\overline{B}}+\delta H_{\overline{A}\mathring{B}})(\delta H^{\mathring{A}\overline{B}}+\delta H^{\overline{A}\mathring{B}})=\delta H_{\mathring{A}\overline{B}}\delta H^{\mathring{A}\overline{B}}+\delta H_{\overline{A}\mathring{B}}\delta H^{\overline{A}\mathring{B}}.$$

Since $P_{AB}$ is a symmetric matrix, we notice that

$$\delta H_{\overline{A}\mathring{B}}=(\overline{P}\delta HP)_{AB}=(P\delta H\overline{P})\_{BA}.$$

Hence, we obtain

$$\delta H_{AB}\delta H^{AB}=2\delta H_{\mathring{A}\overline{B}}\delta H^{\mathring{A}\overline{B}}.$$


## VIII. DFT Christoffel Connection

In general relativity, the connection with the metric compatibility and the torsion-free condition, is called the Levi--Civita connection.
And, the component of the Levi-Civita connection in coordinate bases, is called the Christoffel symbol.
In DFT, we impose the same condition (i.e., metric compatibility and torsion-free condition), yet it is mathematically distinct from the usual Levi--Civita connection.
Hence, we call the DFT connection as *DFT Christoffel connection* following `arXiv:2505.10163 [gr-qc]`.
Recall that in general relativity, the rules of the covariant derivative are different for vectors and 1-forms.

$$\nabla_{\mu}A^{\alpha}=\partial_{\mu}A^{\alpha}+\Gamma_{\mu\beta}^{\alpha}A^{\beta},\qquad\nabla_{\mu}\zeta_{\alpha}=\partial_{\mu}\zeta_{\alpha}-\Gamma_{\mu\alpha}^{\beta}\zeta_{\beta}.$$

On the other hand, when we use orthonormal indices, the gauge group becomes the rotation group, and in this case the covariant derivative is given in terms of the spin connection.

$$\nabla_{\mu}A^{a}=\partial_{\mu}A^{a}+\omega_{\mu}{}^{a}{}_{b}A^{b},\qquad\nabla_{\mu}\zeta_{a}=\partial_{\mu}\zeta_{a}-\omega_{\mu}{}^{b}{}_{a}\zeta\_{b}.$$

Since the spin connection is antisymmetric, we can see that the two expressions above are in fact identical.

$$\nabla_{\mu}\zeta_{a}=\partial_{\mu}\zeta_{a}+\omega_{\mu a}{}^{b}\zeta\_{b}\qquad\implies\qquad\nabla_{\mu}\zeta^{a}=\partial_{\mu}\zeta^{a}+\omega_{\mu}{}^{a}{}_{b}\zeta^{b}.$$

Likewise, the gauge group in DFT is the orthogonal group $O(D,D)$, and there is no distinction between vectors and 1-forms.
Hence, the DFT covariant derivative is defined as

$$\nabla_{A}T^{B}=\partial_{A}T^{B}+\Gamma_{A}{}^{B}{}_{C}T^{C}-w\Gamma^{C}{}_{CA}T^{B},$$

where $w$ denotes the weight of a tensor density.
Notice that since the gauge group in DFT is the orthogonal group, the connection is antisymmetric in the last two indices:

$$\omega_{\mu}{}^{ab}+\omega_{\mu}{}^{ba}=0\qquad\Longleftrightarrow\qquad\Gamma_{ABC}+\Gamma_{ACB}=0.$$


### 1. How to Construct the DFT Connection

Let us consider the following covariant derivative:

$$\begin{aligned}
\nabla_{A}(P_{BC}T^{C})&=\partial_{A}(P_{BC}T^{C})+\Gamma_{AB\mathring{C}}T^{\mathring{C}}
\\
&=P_{BC}\partial_{A}T^{C}+T^{C}\partial_{A}P_{BC}+\Gamma_{AB\mathring{C}}T^{\mathring{C}}.
\end{aligned}$$

Using the metric compatibility $\nabla_{A}P_{BC}=0$, we recast the left-hand side as

$$P_{BC}\nabla_{A}T^{C}=P_{BC}\partial_{A}T^{C}+\Gamma_{A\mathring{B}C}T^{C}.$$

Then, we obtain

$$\Gamma_{A\mathring{B}C}T^{C}=T^{C}\partial_{A}P_{BC}+\Gamma_{AB\mathring{C}}T^{\mathring{C}}.$$

And, we apply the decomposition $T_{A}=T_{\mathring{A}}+T_{\overline{A}}$:

$$\Gamma_{A\mathring{B}\mathring{C}}T^{\mathring{C}}+\Gamma_{A\mathring{B}\overline{C}}T^{\overline{C}}=T^{\mathring{C}}\partial_{A}P_{BC}+T^{\overline{C}}\partial_{A}P_{BC}+\Gamma_{A\mathring{B}\mathring{C}}T^{\mathring{C}}+\Gamma_{A\overline{B}\mathring{C}}T^{\mathring{C}}.$$

Simplifying both sides, we have the follownig result:

$$T^{\overline{C}}(\Gamma_{A\mathring{B}\overline{C}}-\partial_{A}P_{BC})-T^{\mathring{C}}(\Gamma_{A\overline{B}\mathring{C}}+\partial_{A}P_{BC})=0.$$

Recall that $\partial_{A}P_{BC}=\frac{1}{2}\partial_{A}H_{BC}$, and

$$\partial_{A}H_{BC}=(P\partial_{A}H\overline{P})\_{BC}+(\overline{P}\partial_{A}HP)\_{BC}=(P\partial_{A}H\overline{P})\_{BC}+(P\partial_{A}H\overline{P})\_{CB},$$

where we used the fact that $P_{AB}$ is a symmetric matrix.
Then, we conclude that

$$T^{\overline{C}}\left[\Gamma_{A\mathring{B}\overline{C}}-\frac{1}{2}(P\partial_{A}H\overline{P})_{BC}\right]-T^{\mathring{C}}\left[\Gamma_{A\overline{B}\mathring{C}}+\frac{1}{2}(P\partial_{A}H\overline{P})\_{CB}\right]=0.$$

Therefore, we obtain the projected components of the DFT Christoffel connection:

$$\Gamma_{A\mathring{B}\overline{C}}=\frac{1}{2}(P\partial_{A}H\overline{P})\_{BC},\qquad\Gamma_{A\overline{B}\mathring{C}}=-\frac{1}{2}(P\partial_{A}H\overline{P})\_{CB}.$$

Using the same method, we obtain

$$\Gamma_{\overline{A}\mathring{B}\mathring{C}}=\frac{1}{2}(P\partial_{\mathring{C}}H\overline{P})\_{BA}-\frac{1}{2}(P\partial_{\mathring{B}}H\overline{P})\_{CA},
\qquad\Gamma_{\mathring{A}\overline{B}\overline{C}}=\frac{1}{2}(P\partial_{\overline{B}}H\overline{P})\_{AC}-\frac{1}{2}(P\partial_{\overline{C}}H\overline{P})\_{AB}.$$

If we perform the same projection to all three indices, we have

$$\Gamma_{\mathring{A}\mathring{B}\mathring{C}}=\frac{2}{D-1}(P_{AC}\mathring{\delta}\_{B}-P_{AB}\mathring{\delta}\_{C}),\qquad
\Gamma_{\overline{A}\overline{B}\overline{C}}=\frac{2}{D-1}(\overline{P}\_{AC}\overline{\delta}\_{B}-\overline{P}\_{AB}\overline{\delta}\_{C}),$$

where

$$\mathring{\delta}\_{B}=\partial_{\mathring{B}}d+\frac{1}{2}\Gamma^{\overline{E}}{}\_{\overline{E}\mathring{B}},\qquad
\overline{\delta}\_{B}=\partial_{\overline{B}}d+\frac{1}{2}\Gamma^{\mathring{E}}{}\_{\mathring{E}\overline{B}}.$$

> In fact, some components of $\Gamma_{ABC}$ remain undetermined under the metric compatibility. Hence, we need another projection condition with a 6-index projector (see `arXiv:2505.10163 [gr-qc]`) to completely determine $\Gamma_{ABC}$.

Since we have completely constructed the DFT Christoffel connection, the DFT covariant derivative $\nabla_{A}T_{B}$ can also be well-defined.
However, it is not tensorial (i.e., $`\delta_{\xi}(\nabla_{A}T_{B})\ne\hat{L}_{\xi}(\nabla_{A}T_{B})`$), but the following projections are only tensorial:

$$\nabla_{\mathring{A}}T^{\overline{B}\overline{C}\overline{D}},\qquad\nabla_{\overline{A}}T^{\mathring{B}\mathring{C}\mathring{D}},\qquad\nabla_{\mathring{A}}T^{\mathring{A}\overline{B}\overline{C}},\qquad\nabla_{\overline{A}}T^{\overline{A}\mathring{B}\mathring{C}}.$$

> This non-tensorial nature is because we have imposed the projection condition with 6-index projector. From the reason, the DFT Christoffel connection is called the semi-covariant connection. There exists another method to construct the DFT connection, but it does not yield a well-defined fermion.

In DFT, the metric compatibility includes the DFT dilaton:

$$\nabla_{A}J_{AB}=\nabla_{A}H_{BC}=0,\qquad\nabla_{A}d=\partial_{A}+\frac{1}{2}\Gamma^{B}{}_{BA}=0.$$

Also, the DFT Christoffel symbol has the following properties:

$$\Gamma_{ABC}+\Gamma_{ACB}=0,\qquad\Gamma_{ABC}+\Gamma_{BCA}+\Gamma_{CAB}=0.$$

For the other properties, refer to `arXiv:2505.10163 [gr-qc]`. The last relation (cyclic symmtry on the indices $ABC$) is the torsion-free condition, which allows us to replace the partial derivatives by the covariant derivatives in the generalized Lie derivative:

$$\hat{L}\_{\xi}T^{A}=\xi^{B}\nabla_{B}T^{A}-T^{B}\nabla_{B}\xi^{A}+T_{B}\nabla_{A}\xi^{B}.$$

- Example: DFT Yang--Mills theory

In DFT, the field strength in gauge theory is not a tensor:

$$F_{AB}=\nabla_{A}A_{B}-\nabla_{B}A_{A}.$$

Hence, we use its projected components to construct the Lagrangian:

$$L=e^{-2d}F_{\mathring{A}\overline{B}}F^{\mathring{A}\overline{B}}=P^{AC}\overline{P}{}^{BC}F_{AB}F_{CD}.$$


### 2. Master Derivative

In general relativity, the covariant derivative accompanies with the Christoffel symbol and the spin connection:

$$\nabla_{\mu}e_{\nu}^{p}=\partial_{\mu}e_{\nu}^{p}-\Gamma_{\mu\nu}^{\lambda}e_{\lambda}^{p}+\omega_{\mu}{}^{p}{}_{q}e_{\nu}^{q}.$$

However, in DFT, we distinguish the following two expressions:

$$\begin{aligned}
\nabla_{A}V_{Bp}&=\partial_{A}V_{Bp}+\Gamma_{AB}{}^{C}V_{Cp},
\\
D_{A}V_{Bp}&=\partial_{A}V_{Bp}+\Gamma_{AB}{}^{C}V_{Cp}+\Phi_{Ap}{}^{q}V_{Bq}.
\end{aligned}$$

The first on $\nabla_{A}$ is the DFT covariant derivative, which only contains the DFT Christoffel connection, not the DFT spin connection.
The latter one $D_{A}$ is called the *master derivative*, which also accompanies with the DFT spin connection $\Phi_{Apq}$.
Note that the master derivative should be written in the calligraphic letter, but due to the rendering limit of Markdown documents in GitHub, we use a roman D.
Also, notice the fact that, DFT has two different local Lorentz indices $p$ and $\overline{p}$, hence it has two different spin connections:

$$\Phi_{Apq},\qquad\overline{\Phi}\_{A\overline{p}\overline{q}},$$

which acts as

$$D_{A}T_{Bp\overline{q}}=\partial_{A}T_{Bp\overline{q}}+\Gamma_{AB}{}^{C}T_{Cp\overline{q}}+\Phi_{Ap}{}^{r}T_{Br\overline{q}}+\overline{\Phi}_{A\overline{q}}{}^{\overline{s}}T_{Bp\overline{s}}.$$

The DFT spin connection is defined from the metric compatibility:

$$D_{A}V_{Bp}=\nabla_{A}V_{Bp}+\Phi_{Ap}{}^{q}V_{Bq}=0,$$

which determines

$$\Phi_{Apq}=V^{B}{}\_{p}\nabla_{A}V_{Bq},\qquad\overline{\Phi}_{A\overline{p}\overline{q}}=\overline{V}{}^{B}{}\_{\overline{p}}\nabla_{A}\overline{V}\_{B\overline{q}}.$$

Then, we can show that $\Phi_{Apq}$ is antisymmetric in $p\leftrightarrow q$.
For the $SO(1,D-1)$ and $SO(D-1,1)$ spinors, the spin connections act as

$$D_{A}\psi=\partial_{A}\psi+\frac{1}{4}\Phi_{Apq}\gamma^{pq}\psi,\qquad D_{A}\psi'=\partial_{A}\psi'+\frac{1}{4}\overline{\Phi}\_{A\overline{p}\overline{q}}\overline{\gamma}{}^{\overline{p}\overline{q}}\psi',$$

where $\gamma^{pq}=\gamma^{[p}\gamma^{q]}$. For each spinor, the gravitino Killing spinor equations are given as

$$D_{\overline{p}}\varepsilon=0,\qquad D_{p}\varepsilon'=0.$$

Also, the dilatino Killing spinor equations are

$$\gamma^{p}D_{p}\varepsilon=0,\qquad\overline{\gamma}{}^{\overline{p}}D_{\overline{p}}\varepsilon'=0.$$

Here, we focus on the gravitino Killing spinor equation:

$$D_{\overline{p}}\varepsilon=\partial_{\overline{p}}\varepsilon+\frac{1}{4}\Phi_{\overline{p}qr}\gamma^{qr}\varepsilon=0,$$

where $\partial_{\overline{p}}=\overline{V}{}^{A}{}\_{\overline{p}}\partial_{A}$.
In the DFT Christoffel connection, the DFT dilaton is included only in $\Gamma_{\mathring{A}\mathring{B}\mathring{C}}$ and $\Gamma_{\overline{A}\overline{B}\overline{C}}$, which do not contribute to $\Phi_{\overline{p}qr}$.
Therefore, if the generalized metric is decomposed as a block matrix form;

$$H_{\mathrm{10d}}=H_{\mathrm{AdS}\_{5}}\oplus H_{S^{5}}\qquad\text{in AdS}_{5}\times S^{5},$$

then it is enough to solve the gravitino Killing spinor equations with the lower-dimensional gamma matrices.
However, for the dilatino Killing spinor equations, the full 10d gamma matrices are required.


## IX. Concluding Remarks

In this tutorial, I have introduced the basic concepts and computational techniques used in DFT.
The DFT concepts that are not covered in this tutorial are as follows:

- DFT curvature

- DFT energy-momentum tensor

- Einstein Double Field Equation

- Linear perturbation

First, DFT curvature is not included in this tutorial because it does not require much explanation.
The other concepts go beyond the fundamental level, so they are not covered here.
Detailed explanations of them can be found in `arXiv:2505.10163 [gr-qc]` and references therein.
