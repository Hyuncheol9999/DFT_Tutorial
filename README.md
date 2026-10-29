# Tutorials on Double Field Theory
### Hyun-Cheol Kim (kimhc8888@sogang.ac.kr)
I give a tutorial on Double Field Theory (DFT), aimed especially at undergraduate and master's students.
Since I do not like to be talkative, this tutorial focuses on concise explanations of core concepts in DFT.
Through this tutorial, readers will learn the computational techniques used in DFT.
To this end, I have included many examples of each concept in DFT.
This tutorial is based on `arXiv:2505.10163 [gr-qc]`. I will also mention other references if necessary.


## I. Motivation

### 1. String Theory as Quantum Gravity

Before turning to DFT, which is a rather specialized topic, let us first take a broad view of physics.
This will allow us to see where DFT is located on the map of physics.
In general, the fundamental laws of nature are described in the language of quantum field theory, and quantum field theories can be classified into renormalizable and non-renormalizable ones.
When the Lagrangian takes a simple form, as shown below, the theory is renormalizable.
In this case, the counterterms can be computed exactly, and therefore the RG flow can be predicted.

$$S[\phi]=-\frac{1}{2}\int\mathrm{d}^{4}x\left(\partial_{\mu}\phi\partial^{\mu}\phi+m^{2}\phi^{2}+\lambda\phi^{4}\right).$$

On the other hand, when the Lagrangian takes a complicated form, the theory is non-renormalizable. In this case, the counterterms cannot be fully determined, and therefore only limited information about the RG flow can be obtained. Hence, we arrive at the following conclusion:

> Non-renormalizable theories are low-energy effective theories, which are valid only below a certain energy scale.

Let us now consider the theory of gravity.
It is described by the Einstein--Hilbert action, and linearizing it around a flat background yields the following action.
(Of course, one can also linearize it around a curved background, but this merely leads to a more complicated theory.)

$$S[h_{\mu\nu}]=\frac{1}{4}\int\mathrm{d}^{4}x\left(-\frac{1}{2}\partial_{\lambda}h_{\mu\nu}\partial^{\lambda}h^{\mu\nu}+\partial_{\mu}h_{\nu\lambda}\partial^{\nu}h^{\mu\lambda}-\partial_{\mu}h^{\mu\nu}\partial_{\nu}h+\frac{1}{2}\partial_{\lambda}h\partial^{\lambda}h\right).$$

Since this Lagrangian takes a complicated form, it is clear that the theory is non-renormalizable.
In other words, Einstein's theory of gravity holds only at low energies and ceases to be valid in high-energy situations such as the Big Bang.
String theory emerged as an alternative to resolve this problem.
A string is a one-dimensional object, and as it evolves in time, it sweeps out a two-dimensional surface called the worldsheet.
The dynamics of the string is described by the following action.

$$S[x^{\mu},\gamma^{ab}]=-\frac{1}{4\pi\alpha'}\int\mathrm{d}^{2}\sigma\sqrt{-\gamma}\gamma^{ab}\partial_{a}x^{\mu}\partial_{b}x^{\nu}g_{\mu\nu}(x).$$

The above theory is renormalizable.
However, its symmetry survives the RG flow, and the theory stays well defined, only if the function $g_{\mu\nu}(x)$ has a special form.
The conditions that $g_{\mu\nu}(x)$ must satisfy for this are as follows:

$$R_{\mu\nu}=0\qquad(\text{Einstein equations in vacuum}).$$

This means that Einstein's equations must hold for string theory to be well defined.
To be more specific, when we renormalize the above action, we assume that the constant $\alpha'$ is small and compute perturbatively.
Since $\alpha'$ has dimensions of length squared, a small $\alpha'$ means that the lengths we deal with in the laboratory are very large.
This in turn means low energies, so we can summarize the result as follows:

> For string theory to be well defined at low energies, Einstein's equations must hold. Therefore, Einstein's theory of gravity is the low-energy effective theory of string theory.


### 2. T-Duality

The string theory action we saw earlier is called the worldsheet action, and its full extension is given as follows:

$$S[x^{\mu},\gamma^{ab}]=-\frac{1}{4\pi\alpha'}\int\mathrm{d}^2\sigma\left(\sqrt{-\gamma}\gamma^{ab}g_{\mu\nu}(x)\partial_{a}x^{\mu}\partial_{b}x^{\nu}+\epsilon^{ab}B_{\mu\nu}(x)\partial_{a}x^{\mu}\partial_{b}x^{\nu}+\alpha'\sqrt{-\gamma}R(\gamma)\phi(x)\right).$$

Here, $B_{\mu\nu}$ is called the Kalb--Ramond field, and $\phi$ is called the dilaton.
It is important to interpret the above action physically.
The field $g_{\mu\nu}$ is interpreted as the curvature of spacetime, that is, gravity.
On the other hand, the newly added fields $B_{\mu\nu}$ and $\phi$ appear from the extension of the worldsheet action, so they are usually interpreted as matter that sources gravity.
However, string theory has a property called T-duality, and when we apply it, these variables transform as follows:

$$\begin{aligned}
&g_{yy}\to\alpha'\frac{1}{g_{yy}},
&&g_{yi}\to\alpha'\frac{B_{yi}}{g_{yy}},
&&B_{yi}\to\alpha'\frac{g_{yi}}{g_{yy}},
\\
&g_{ij}\to g_{ij}-\frac{g_{yi}g_{yj}-B_{yi}B_{yj}}{g_{yy}},
&&B_{ij}\to B_{ij}-\frac{g_{yi}B_{yj}-B_{yi}g_{yj}}{g_{yy}},
&&\phi\to\phi-\frac{1}{2}\ln\frac{g_{yy}}{\alpha'},
\end{aligned}$$

where we decomposed the spacetime coordinates as $x^{\mu}=(y,x^{i})$.
In this way, the fact that $(g,B,\phi)$ transform into one another suggests that $B$ and $\phi$ can also be interpreted as gravitational fields.
Indeed, in DFT, these quantities are combined to define the following block matrix.
DFT is the framework in which this quantity is interpreted as a gravitational field and physical phenomena are discussed in terms of it.

$$H_{AB}=\begin{pmatrix}g^{-1}&-g^{-1}B
\\
Bg^{-1}&g-Bg^{-1}B\end{pmatrix},\qquad e^{-2d}=e^{-2\phi}\sqrt{-g}.$$

Notice that the above $H_{AB}$ is usually written as a calligraphic letter (i.e., curly H), however it seems that Markdown on GitHub does not support the LaTeX command `\mathcal`, so I will use a roman H instead.


## II. Doubled Spacetime

From now on, we let $D$ denote the dimension of spacetime.
DFT uses the concept of doubled spacetime, which means that the dimension of spacetime is doubled.
That is, to describe $D$-dimensional physics, DFT uses a $2D$-dimensional doubled spacetime.
To understand this, we need to know about T-duality in string theory.
As before, we split the spacetime coordinates as $x^{\mu}=(y,x^{i})$.
Ordinary coordinates take values in $x\in\mathbb{R}$, but for the coordinate $y$, we assume the following range:

$$0\le y\lt R\qquad (R\text{ is a constant}).$$

That is, $y$ plays a role similar to an angle, and the coordinate axis described by $y$ is not a straight line but a circle.
As a result, physical quantities take an $R$-dependent form.
According to T-duality in string theory, the laws of physics are invariant under the transformation $R\to\frac{\alpha'}{R}$.
Since the radius has changed, the new circle is different from the original one, and therefore it must be described by a new coordinate $\tilde{y}$.

$$0\le\tilde{y}\lt\frac{\alpha'}{R}.$$

The spaces described by the coordinates $y$ and $\tilde{y}$ are completely different spaces.
For example, four-dimensional flat spacetime can be described by the coordinates $(t,r,\theta,\phi)$, and the Schwarzschild black hole can also be described by the coordinates $(t,r,\theta,\phi)$, but no coordinate transformation relates the two.
In other words, T-duality is not a coordinate transformation (which is familiar to physicists), but rather a transformation between spaces.


### 1. Definition

In order to express T-duality in the language of coordinate transformation, DFT introduces the concept of doubled spacetime.
For example, for the coordinates $(t,x,y,z)$ of four-dimensional spacetime, the coordinates of the doubled spacetime are eight-dimensional, as given below:

$$x^{A}=(\tilde{t},\tilde{x},\tilde{y},\tilde{z},t,x,y,z).$$

In ordinary spacetime, T-duality between the coordinates $y$ and $\tilde{y}$ was a transformation of spacetime that cannot be expressed as a coordinate transformation.
In doubled spacetime, however, it is described simply as a coordinate transformation that exchanges $y$ and $\tilde{y}$.
In arbitrary dimensions, the coordinates are written in block matrix form as follows (recall that, as mentioned earlier, DFT uses a block matrix $H_{AB}$ consisting of $g_{\mu\nu}$ and $B_{\mu\nu}$):

$$x^{A}=\begin{pmatrix}\tilde{x}_{\mu}
\\
x^{\mu}\end{pmatrix}.$$

In the above expression, $x^{\mu}$ are the ordinary coordinates, $\tilde{x}\_{\mu}$ are called the dual coordinates, and $x^{A}$ is called the doubled coordinate.
Since the dual coordinates do not appear in the laws of physics, all physical quantities must be independent of $\tilde{x}\_{\mu}$.
That is, the derivative with respect to the doubled coordinate $x^{A}=(\tilde{x}\_{\mu},x^{\mu})$ is given as follows:

$$\partial_{A}=\begin{pmatrix}\tilde{\partial}{}^{\mu}
\\
\partial_{\mu}\end{pmatrix}=\begin{pmatrix}0
\\
\partial_{\mu}\end{pmatrix}.$$

As we saw earlier, T-duality in DFT is given by a coordinate transformation that exchanges the ordinary coordinates $x^{\mu}$ and the dual coordinates $\tilde{x}\_{\mu}$.
To make this more explicit, DFT expresses this exchange of coordinates as raising or lowering a vector index, as shown below:

$$x^{A}=\begin{pmatrix}\tilde{x}\_{\mu}
\\
x^{\mu}\end{pmatrix}
\qquad\longleftrightarrow\qquad
x\_{A}=\begin{pmatrix}x^{\mu}
\\
\tilde{x}\_{\mu}\end{pmatrix}.$$


### 2. Section Condition

The index of the ordinary coordinate $x^{\mu}$ is written as a superscript, whereas the index of the dual coordinate $\tilde{x}\_{\mu}$ is written as a subscript. Based on this, a doubled vector is defined in terms of a vector $\xi^{\mu}$ and a 1-form $\tilde{\xi}\_{\mu}$ as follows:

$$\xi^{A}=\begin{pmatrix}\tilde{\xi}_{\mu}
\\
\xi^{\mu}\end{pmatrix}.$$

Under T-duality, this is transformed into a doubled 1-form, which, as we saw earlier, is defined by exchanging the vector and the 1-form.

$$\xi_{A}=\begin{pmatrix}\xi^{\mu}
\\
\tilde{\xi}_{\mu}\end{pmatrix}.$$

Keep in mind that when the doubled index $A$ is a superscript, the subscripted $\tilde{\xi}\_{\mu}$ appears first in the block matrix representation, whereas when the doubled index $A$ is a subscript, the superscripted $\xi^{\mu}$ appears first.
Based on this, we apply the Einstein summation convention to compute the contraction of vectors and obtain the following:

$$\xi\_{A}\chi^{A}=\xi^{\mu}\tilde{\chi}\_{\mu}+\tilde{\xi}\_{\mu}\chi^{\mu}.$$

For convenience, we will omit the tilde. That is, $\xi^{\mu}$ and $\xi\_{\mu}$ are completely independent tensors, and DFT does not use the rule shown below, in which indices are raised and lowered with the metric tensor:

$$\xi_{\mu}\ne g_{\mu\nu}\xi^{\nu},\qquad\xi^{\mu}\ne g^{\mu\nu}\xi_{\nu}.$$

Then, the Einstein summation convention is written as follows:

$$\xi_{A}\chi^{A}=\xi_{\mu}\chi^{A}+\xi^{\mu}\chi_{\mu}.$$

That is, the doubled index $A$ splits into the superscript $(\cdots)^{\mu}$ and the subscript $(\cdots)\_{\mu}$. Applying this to the derivative, we obtain the following, where $f$ is an arbitrary function:

$$\partial_{A}\partial^{A}f=\partial_{\mu}\tilde{\partial}{}^{\mu}f+\tilde{\partial}{}^{\mu}\partial_{\mu}f=2\partial_{\mu}\tilde{\partial}{}^{\mu}f=0.$$

In the last equation, we used the condition $\tilde{\partial}{}^{\mu}=0$ that we learned earlier. For two arbitrary functions $f$ and $g$, the following holds:

$$\partial_{A}f\partial^{A}g=0.$$

The above two equations are called the *section condition*. The section condition is a kind of gauge condition; for a detailed explanation, see `arXiv:1304.5946 [hep-th]`, `arXiv:1307.8377 [hep-th]`, and `arXiv:2505.10163 [gr-qc]`. In other words, since a gauge condition exists in doubled spacetime, it is sometimes called doubled-yet-gauged spacetime. In this tutorial, however, we will not discuss this gauge symmetry in detail.


## III. Doubled Tensors

To define the doubled vector $\xi^{A}$, we needed an ordinary vector $\xi^{\mu}$ and a 1-form $\xi\_{\mu}$.
Similarly, a doubled matrix is defined by arranging four different matrices $M^{\mu\nu}$, $M^{\mu}{}\_{\nu}$, $M\_{\mu}{}^{\nu}$, and $M\_{\mu\nu}$ in block matrix form.

$$M_{AB}=\begin{pmatrix}M^{\mu\nu}&M^{\mu}{}_{\nu}
\\
M_{\mu}{}^{\nu}&M_{\mu\nu}\end{pmatrix}.$$

When $M\_{AB}$ is written in block matrix form, the upper-left block contains $M^{\mu\nu}$, whose indices are both flipped to superscripts, while the lower-right block contains $M\_{\mu\nu}$, whose indices are subscripts, just like those of $M\_{AB}$. By the same rule, we can define doubled tensors whose doubled indices are raised or lowered.

$$M^{AB}=\begin{pmatrix}M_{\mu\nu}&M_{\mu}{}^{\nu}
\\
M^{\mu}{}_{\nu}&M^{\mu\nu}\end{pmatrix},\qquad
M\_{A}{}^{B}=\begin{pmatrix}M^{\mu}{}\_{\nu}&M^{\mu\nu}
\\
M\_{\mu\nu}&M_{\mu}{}^{\nu}\end{pmatrix},\qquad
M^{A}{}\_{B}=\begin{pmatrix}M\_{\mu}{}^{\nu}&M\_{\mu\nu}
\\
M^{\mu\nu}&M^{\mu}{}\_{\nu}\end{pmatrix}.$$

Next, we define the identity matrix $\delta^{\mu}\_{\nu}=\delta\_{\nu}{}^{\mu}$ and the zero matrix $0\_{\mu\nu}$.

$$\delta^{\mu}{}\_{\nu}=\delta\_{\nu}{}^{\mu}=\mathrm{diag}(1,\cdots,1),\qquad0\_{\mu\nu}=\mathrm{diag}(0,\cdots,0).$$

By combining these, we can define the following doubled tensor:

$$J\_{AB}=\begin{pmatrix}0^{\mu\nu}&\delta^{\mu}{}\_{\nu}
\\
\delta\_{\mu}{}^{\nu}&0\_{\mu\nu}\end{pmatrix},\qquad
J^{AB}=\begin{pmatrix}0\_{\mu\nu}&\delta\_{\mu}{}^{\nu}
\\
\delta^{\mu}{}\_{\nu}&0^{\mu\nu}\end{pmatrix},\qquad
J\_{A}{}^{B}=\begin{pmatrix}\delta^{\mu}{}\_{\nu}&0^{\mu\nu}
\\
0\_{\mu\nu}&\delta\_{\mu}{}^{\nu}\end{pmatrix},\qquad
J^{A}{}\_{B}=\begin{pmatrix}\delta\_{\mu}{}^{\nu}&0\_{\mu\nu}
\\
0^{\mu\nu}&\delta^{\mu}{}\_{\nu}\end{pmatrix}.$$

Writing it in matrix form, we find the following:

$$J\_{AB}=J^{AB}=\begin{pmatrix}0&&&1&&
\\
&\ddots&&&\ddots&
\\
&&0&&&1
\\
1&&&0&&
\\
&\ddots&&&\ddots&
\\
&&1&&&0\end{pmatrix},\qquad
J\_{A}{}^{B}=J^{B}{}\_{A}=\delta\_{A}^{B}.$$

That is, $J\_{AB}$ is invariant under the matrices that raise or lower indices, and therefore it is invariant under T-duality.
If we extend T-duality, which is simply a transformation that exchanges coordinates, into the form of a rotation group, we obtain the group $O(D,D)$, which is similar to the Lorentz group $O(1,3)$ (recall that $D$ is the dimension of spacetime).
Since $J\_{AB}$ is invariant under this group, it is called the $O(D,D)$-invariant metric. Like $H\_{AB}$, which we saw earlier, $J\_{AB}$ should also be written in a calligraphic letter, but in this tutorial we will write it as a roman J.
Multiplying a doubled vector by the $O(D,D)$-invariant metric, we obtain the following:

$$J\_{AB}\xi^{B}=\begin{pmatrix}0^{\mu\nu}&\delta^{\mu}{}\_{\nu}
\\
\delta\_{\mu}{}^{\nu}&0\_{\mu\nu}\end{pmatrix}
\begin{pmatrix}\xi_{\nu}
\\
\xi^{\nu}\end{pmatrix}
=\begin{pmatrix}\xi^{\mu}
\\
\xi_{\mu}\end{pmatrix}=\xi_{A}.$$

That is, the indices of doubled tensors are raised and lowered with the $O(D,D)$-invariant metric. For example,

$$M_{AB}=J_{AC}J_{BD}M^{CD}.$$


### 1. Generalized Lie Derivative

In general relativity, the metric tensor $g\_{\mu\nu}$ represents a given geometry.
If the Lie derivative of the metric tensor vanishes, this means that the geometry has a certain symmetry.
In DFT, on the other hand, the $O(D,D)$-invariant metric $J\_{AB}$ represents T-duality, which is a more fundamental concept than geometry.
For example, when a black hole is present, the symmetry of the geometry can be broken, but T-duality, which the theory itself must have, must never be broken.
The extension of the Lie derivative to DFT is called the generalized Lie derivative, and it is denoted by $\hat{L}\_{\xi}$ (as before, we use a roman L instead of a calligraphic L because of the Markdown issue on GitHub).
Under the generalized Lie derivative, the $O(D,D)$-invariant metric must always be preserved:

$$\hat{L}\_{\xi}J\_{AB}=0.$$

In general, the generators of rotations are antisymmetric matrices.
$J\_{AB}$ is invariant under the rotations in $O(D,D)$, and using an infinitesimal vector $\xi^{A}$, we can write the corresponding antisymmetric matrix as $\partial^{[A}\xi^{B]}=\frac{1}{2}(\partial^{A}\xi^{B}-\partial^{B}\xi^{A})$.
Then, for a doubled vector $T^{A}$, the generalized Lie derivative is defined as follows:

$$\hat{L}\_{\xi}T^{A}=\xi^{B}\partial\_{B}T^{A}+2\partial^{[A}\xi^{B]}T_{B}.$$

Multiplying both sides of the above equation by $J\_{CA}$, we obtain the generalized Lie derivative of $T\_{C}$.
For a tensor with two indices, the following holds:

$$\hat{L}\_{\xi}M^{AB}=\xi^{C}\partial\_{C}M^{AB}+2\partial^{[A}\xi^{C]}M\_{C}{}^{B}+2\partial^{[B}\xi^{C]}M^{A}{}\_{C}.$$

For the generalized Lie derivative of a tensor density of weight $w$, we have

$$\hat{L}\_{\xi}T^{A}=\xi^{B}\partial_{B}T^{A}-T^{B}\partial_{B}\xi^{A}+T_{B}\partial^{A}\xi^{B}+wT^{A}\partial_{B}\xi^{B}.$$

We will denote the generalized Lie derivative by $\hat{L}\_{\xi}$ and the ordinary Lie derivative by $L\_{\xi}$.
The formulas for the Lie derivative of a vector and a 1-form are summarized as follows:

$$\begin{aligned}
\hat{L}\_{\xi}T^{A}&=\xi^{B}\partial\_{B}T^{A}-T^{B}\partial\_{B}\xi^{A}+T\_{B}\partial^{A}\xi^{B},
\\
L\_{\xi}u^{\mu}&=\xi^{\nu}\partial\_{\nu}u^{\mu}-u^{\nu}\partial\_{\nu}\xi^{\mu},
\\
L\_{\xi}\omega\_{\mu}&=\xi^{\nu}\partial\_{\nu}\omega\_{\nu}+\omega\_{\nu}\partial\_{\mu}\xi^{\nu}.
\end{aligned}$$

Looking closely at the above equation, we see that the generalized Lie derivative of a doubled vector is a combination of the ordinary Lie derivatives of a vector and a 1-form.
This is natural, since a doubled vector $T^{A}=(T\_{\mu},T^{\mu})$ is itself made up of a vector and a 1-form.


### 2. How to Calculate Generalized Lie Derivative

Let us recall the following relation:

$$\hat{L}\_{\xi}T^{A}=\xi^{B}\partial\_{B}T^{A}-T^{B}\partial\_{B}\xi^{A}+T\_{B}\partial^{A}\xi^{B}.$$

The doubled index $A$ consists of the upper index $(\cdots)^{\mu}$ and the lower index $(\cdots)\_{\mu}$.
First, taking the upper-index component $(\cdots)^{\mu}$ of the doubled index $A$ on both sides of the above equation, we obtain the following:

$$\hat{L}\_{\xi}T^{\mu}=\xi^{B}\partial\_{B}T^{\mu}-T^{B}\partial\_{B}\xi^{\mu}.$$

In the above equation, we used the section condition $\partial^{\mu}=0$.
Since the Einstein summation convention in DFT reads $(\cdots)\_{B}(\cdots)^{B}=(\cdots)\_{\nu}(\cdots)^{\nu}+(\cdots)^{\nu}(\cdots)\_{\nu}$, applying this convention gives the following:

$$\hat{L}\_{\xi}T^{\mu}=\xi^{\nu}\partial\_{\nu}T^{\mu}-T^{\nu}\partial\_{\nu}\xi^{\mu}=L\_{\xi}T^{\mu}.$$

In other words, for a tensor with an upper index, $T^{\mu}$, the generalized Lie derivative is the same as the ordinary Lie derivative.
Next, for a tensor with a lower index, $T\_{\mu}$, we obtain

$$\begin{aligned}
\hat{L}\_{\xi}T\_{\mu}&=\xi^{B}\partial\_{B}T\_{\mu}-T^{B}\partial\_{B}\xi\_{\mu}+T\_{B}\partial\_{\mu}\xi^{B}
\\
&=\xi^{\nu}\partial\_{\nu}T\_{\mu}-T^{\nu}\partial\_{\nu}\xi\_{\mu}+T\_{\nu}\partial\_{\mu}\xi^{\nu}+T^{\nu}\partial\_{\mu}\xi\_{\nu}
\\
&=\xi^{\nu}\partial\_{\nu}T\_{\mu}+T\_{\nu}\partial\_{\mu}\xi^{\nu}-2T^{\nu}\partial\_{[\nu}\xi\_{\mu]}
\\
&=L\_{\xi}T\_{\mu}-2T^{\nu}\partial\_{[\nu}\xi\_{\mu]}.
\end{aligned}$$

In this way, for a tensor $T_{\mu}$ with a lower index, the generalized Lie derivative differs from the ordinary Lie derivative, and an additional term appears.
(The physical meaning of this additional term will become clear shortly.)
The same rule can be applied to general tensors, and the generalized Lie derivative is given by the ordinary Lie derivative plus additional terms associated with the lower indices:

$$\hat{L}\_{\xi}T^{\mu\nu}{}\_{\lambda\rho}=L\_{\xi}T^{\mu\nu}{}\_{\lambda\rho}-2T^{\mu\nu\alpha}{}\_{\rho}\partial\_{[\alpha}\xi_{\lambda]}-2T^{\mu\nu}{}\_{\lambda}{}^{\alpha}\partial\_{[\alpha}\xi_{\rho]}.$$


### 3. Example: Invariance of $J\_{AB}$

When computing $\hat{L}\_{\xi}J\_{AB}$, we take the upper- and lower-index components of each of the doubled indices $A$ and $B$.
First, when both indices are upper indices, we obtain the following:

$$\hat{L}\_{\xi}J^{\mu\nu}=L\_{\xi}J^{\mu\nu}=0.$$

Since $J\_{AB}$ is a symmetric tensor, we have $J\_{A}{}^{B}=J^{B}{}\_{A}$.
When one of the two indices is an upper index and the other is a lower index, we obtain the following:

$$\hat{L}\_{\xi}J^{\mu}{}\_{\nu}=L\_{\xi}J^{\mu}{}\_{\nu}-2J^{\mu\alpha}\partial\_{[\alpha}\xi_{\nu]}=L\_{\xi}\delta^{\mu}{}\_{\nu}=0.$$

Finally, when both indices are lower indices, we obtain

$$\hat{L}\_{\xi}J\_{\mu\nu}=L\_{\xi}J\_{\mu\nu}-2J^{\alpha}{}\_{\nu}\partial\_{[\alpha}\xi\_{\mu]}-2J_{\mu}{}^{\alpha}\partial_{[\alpha}\xi_{\nu]}=-2\delta^{\alpha}{}_{\nu}\partial\_{[\alpha}\xi_{\mu]}-2\delta_{\mu}{}^{\alpha}\partial_{[\alpha}\xi_{\nu]}=0.$$

That is, the $O(D,D)$-invariant metric is preserved under the generalized Lie derivative.


## IV. Generalized Metric

In general relativity, the metric tensor is defined as follows:

$$g_{\mu\nu}g^{\nu\lambda}=\delta_{\mu}{}^{\lambda},\qquad g_{\mu\nu}=g_{\nu\mu}.$$

In DFT, we use a quantity called the *generalized metric*, which is also defined based on the same manner:

$$H_{AB}H^{BC}=\delta_{A}{}^{C},\qquad H_{AB}=H_{BA}.$$

However, unlike $g^{\nu\lambda}$, $H^{BC}$ is not an inverse matrix, but the generalized metric whose doubled indices are raised with the $O(D,D)$-invariant metric. That is, the equation $g\_{\mu\nu}g^{\nu\lambda}=\delta\_{\mu}{}^{\lambda}$ in general relativity holds automatically by definition, whereas the equation $H\_{AB}H^{BC}=\delta\_{A}{}^{C}$ in DFT is a kind of constraint. There are two ways to solve this constraint: the first is called the Riemannian parametrization, and the other is called the non-Riemannian parametrization.


### 1. Riemannian Parametrization

Let us consider the following generalized metric:

$$H_{AB}=\begin{pmatrix}H^{\mu\nu}&H^{\mu}{}\_{\nu}
\\
H_{\mu}{}^{\nu}&H_{\mu\nu}\end{pmatrix}.$$

Diagonalizing the above matrix diagonalizes $H^{\mu\nu}$ and $H\_{\mu\nu}$.
The Riemannian parametrization is the method in which we assume that the eigenvalues after diagonalization are nonzero.
In this case, $H^{\mu\nu}$ and $H\_{\mu\nu}$ are invertible matrices, so we can introduce the inverse metric $g^{\mu\nu}$ as follows:

$$H^{\mu\nu}=g^{\mu\nu}=g_{\mu\nu}^{-1}.$$

That is, the Riemannian parametrization is the method that uses the Riemannian metric $g\_{\mu\nu}$. Now, we solve the constraint $H_{A}{}^{B}H_{B}{}^{C}=\delta_{A}{}^{C}$:

$$\begin{aligned}
H_{A}{}^{B}H_{B}{}^{C}
&=\begin{pmatrix}H^{\mu}{}_{\nu}&g^{\mu\nu}
\\
H_{\mu\nu}&H_{\mu}{}^{\nu}\end{pmatrix}
\begin{pmatrix}H^{\nu}{}_{\lambda}&g^{\nu\lambda}
\\
H_{\nu\lambda}&H_{\nu}{}^{\lambda}\end{pmatrix}
\\
&=\begin{pmatrix}H^{\mu}{}\_{\nu}H^{\nu}{}\_{\lambda}+g^{\mu\nu}H\_{\nu\lambda}&H^{\mu}{}\_{\nu}g^{\nu\lambda}+g^{\mu\nu}H\_{\nu}{}^{\lambda}
\\
H_{\mu\nu}H^{\nu}{}_{\lambda}+H_{\mu}{}^{\nu}H_{\nu\lambda}&H\_{\mu\nu}g^{\nu\lambda}+H\_{\mu}{}^{\nu}H\_{\nu}{}^{\lambda}\end{pmatrix}
\\
&=\begin{pmatrix}H^{\mu}{}\_{\nu}H^{\nu}{}\_{\lambda}+g^{\mu\nu}H\_{\nu\lambda}&2H^{(\mu}{}_{\nu}g^{\lambda)\nu}
\\
2H\_{(\mu}{}^{\nu}H\_{\lambda)\nu}&H\_{\mu\nu}g^{\nu\lambda}+H\_{\mu}{}^{\nu}H\_{\nu}{}^{\lambda}\end{pmatrix}.
\end{aligned}$$

Solving $H_{A}{}^{B}H_{B}{}^{C}=\delta_{A}{}^{C}$, we obtain

$$H^{\mu}{}\_{\nu}H^{\nu}{}\_{\lambda}+g^{\mu\nu}H\_{\nu\lambda}=\delta^{\mu}{}_{\lambda},\qquad H^{(\mu}{}_{\nu}g^{\lambda)\nu}=H\_{(\mu}{}^{\nu}H\_{\lambda)\nu}=0,\qquad H\_{\mu\nu}g^{\nu\lambda}+H\_{\mu}{}^{\nu}H\_{\nu}{}^{\lambda}=\delta_{\mu}{}^{\lambda}.$$

That is, $H^{\mu}{}_{\nu}g^{\lambda\nu}$ is antisymmetric in $\mu\leftrightarrow\lambda$, hence we identify it with the Kalb--Ramond field:

$$H^{\mu}{}_{\nu}g^{\lambda\nu}=-B^{\mu\lambda}\qquad\implies\qquad H^{\mu}{}_{\nu}=-(g^{-1}B)^{\mu}{}_{\nu}.$$

Since $H_{AB}$ is a symmetric matrix, we obtain

$$H_{AB}=\begin{pmatrix}g^{\mu\nu}&-(g^{-1}B)^{\mu}{}_{\nu}
\\
(Bg^{-1})_{\mu}{}^{\nu}&H\_{\mu\nu}\end{pmatrix}.$$

From the constraint $H_{A}{}^{B}H_{B}{}^{C}=\delta_{A}{}^{C}$, it is straightforward to obtain

$$H_{\mu\nu}=(g-Bg^{-1}B)_{\mu\nu}.$$


### 2. Kalb--Ramond Gauge Transformation

We have learned that the following holds for the generalized Lie derivative:

$$\hat{L}_{\xi}H^{\mu\nu}=L_{\xi}H^{\mu\nu}.$$

Applying the Riemannian parametrization, we obtain

$$\hat{L}_{\xi}g^{-1}=L_{\xi}g^{-1}$$

Next, we consider the following relation:

$$\hat{L}\_{\xi}H\_{\mu}{}^{\nu}=L\_{\xi}H\_{\mu}{}^{\nu}-2H^{\alpha\nu}\partial_{[\alpha}\xi_{\mu]}.$$

Applying the Riemannian parametrization, we obtain

$$\hat{L}_{\xi}(Bg^{-1})_{\mu}{}^{\nu}=L\_{\xi}(Bg^{-1})\_{\mu}{}^{\nu}-2g^{\alpha\nu}\partial\_{[\alpha}\xi_{\mu]}.$$

Applying the Leibniz rule $L\_{\xi}(Bg^{-1})=(L\_{\xi}B)g^{-1}+B(L\_{\xi}g^{-1})$, we obtain

$$(\hat{L}\_{\xi}B_{\mu\alpha})g^{\alpha\nu}=(L\_{\xi}B_{\mu\alpha})g^{\alpha\nu}-2g^{\alpha\nu}\partial_{[\alpha}\xi_{\mu]}.$$

Hence,

$$\hat{L}\_{\xi}B_{\mu\nu}=L\_{\xi}B_{\mu\nu}+2\partial_{[\mu}\xi_{\nu]}.$$

The first term on the right-hand side is the diffeomorphism transformation of spacetime, and the second term is the gauge transformation of the Kalb--Ramond field.
For reference, the gauge transformation of a gauge potential given as a 1-form is $\delta A=\mathrm{d}\lambda$ (where $\lambda$ is a 0-form), and the gauge transformation of the Kalb--Ramond field, given as a 2-form, is $\delta B=\mathrm{d}\xi$ (where $\xi$ is a 1-form).
Therefore, the physical meaning of the doubled vector $\xi^{A}=(\xi\_{\mu},\xi^{\mu})$ is as follows:

$$\xi^{\mu}=(\text{diffeomorphism transformation}),\qquad\xi_{\mu}=(\text{Kalb--Ramond gauge transformation}).$$


### 3. Non-Riemannian Parametrization

The Riemannian parametrization assumes that the matrix $H^{\mu\nu}$ is invertible. As a typical case in which this assumption does not hold, we can consider the following matrix:

$$H^{\mu\nu}=\mathrm{diag}(0,1,1,1).$$

As a more explicit case, we will consider the case $H^{\mu\nu}=0$. In this case, computing the constraint $H\_{A}{}^{B}H\_{B}{}^{C}=\delta\_{A}{}^{C}$, we obtain the following:

$$H_{A}{}^{B}H_{B}{}^{C}=\begin{pmatrix}H^{\mu}{}_{\nu}H^{\nu}{}_{\lambda}&0
\\
2H\_{(\mu}{}^{\nu}H\_{\lambda)\nu}&H\_{\mu}{}^{\nu}H\_{\nu}{}^{\lambda}\end{pmatrix}.$$

Since $H^{\nu}{}\_{\mu}$ is a transposition of $H\_{\mu}{}^{\nu}$, the constraint $H\_{A}{}^{B}H\_{B}{}^{C}=\delta\_{A}{}^{C}$ yields the following two conditions:

$$H_{\mu}{}^{\nu}H_{\nu}{}^{\lambda}=\delta_{\mu}{}^{\lambda},\qquad H_{(\mu}{}^{\nu}H_{\lambda)\nu}=0.$$

We make the following substitution:

$$H_{\lambda\nu}=H_{\nu}{}^{\alpha}B_{\alpha\lambda}\qquad\implies\qquad B_{\mu\nu}+B_{\nu\mu}=0.$$

> When the matrix $H^{\mu\nu}$ is non-invertible, the Riemannian metric $g\_{\mu\nu}$ does not exist, but the Kalb--Ramond field $B\_{\mu\nu}$ still exists.

Finding a matrix $H_{\mu}{}^{\nu}$ satisfying $H_{\mu}{}^{\nu}H_{\nu}{}^{\lambda}=\delta_{\mu}{}^{\lambda}$ is straightforward, and we find that the following generalized metric satisfies the constraint $H\_{A}{}^{B}H\_{B}{}^{C}=\delta\_{A}{}^{C}$:

$$H_{AB}=\begin{pmatrix}0&&&\pm1&&
\\
&\ddots&&&\ddots&
\\
&&0&&&\pm1
\\
\pm1&&&\bigcirc&\bigcirc&\bigcirc
\\
&\ddots&&\bigcirc&\bigcirc&\bigcirc
\\
&&\pm1&\bigcirc&\bigcirc&\bigcirc\end{pmatrix},$$

where $\bigcirc$ denotes the components of $H_{\mu\nu}$. The above form of the generalized metric is called the *non-Riemannian parametrization*. For a general form of the non-Riemannian parametrization, see `arXiv:1707.03713 [hep-th]` and `arXiv:2505.10163 [gr-qc]`.


### 4. Non-Riemannian Geometry

In general relativity, the Riemannian metric $g\_{\mu\nu}$ represents geometry.
In DFT, on the other hand, the Kalb--Ramond field is also part of the gravitational field, so the generalized metric $H\_{AB}$, which combines it with $g\_{\mu\nu}$, represents gravity, that is, geometry.
When the Riemannian parametrization is possible, $H\_{AB}$ reduces to $g\_{\mu\nu}$, as we saw earlier, and thus the generalized metric represents an ordinary Riemannian manifold.
On the other hand, the geometry that appears when the non-Riemannian parametrization is applied differs from an ordinary Riemannian manifold, so it is called *non-Riemannian geometry*.
To understand non-Riemannian geometry, we define the lightcone coordinates in two-dimensional spacetime as follows:

$$x^{\pm}=\frac{t\pm x}{c\sqrt{2}}.$$

Then, the Riemannian metric is given as follows (the constant $c$ is introduced for convenience and is not the speed of light):

$$\mathrm{d}^{2}s=-\mathrm{d}t^{2}+\mathrm{d}x^{2}=-2c\mathrm{d}x^{+}\mathrm{d}x^{-}.$$

In general relativity, the perturbation of the Riemannian metric is the gravitational potential.
Therefore, in a divergent situation such as $c\to\infty$, the gravitational potential becomes infinitely large, and physical phenomena are not well defined.
On the other hand, when the Kalb--Ramond field exactly cancels the effect of the gravitational potential, as shown below, physical phenomena are well defined even in the limit $c\to\infty$:

$$B=c\mathrm{d}x^{-}\wedge\mathrm{d}x^{+}.$$

References related to this include the Gomis--Ooguri nonrelativistic string `arXiv:hep-th/0009181` and the long string in $AdS_{3}$ `arXiv:hep-th/0001053`.
According to these references, when a Kalb--Ramond field like the one above is present, physical phenomena still occur even when the Riemannian metric diverges. In this case, the generalized metric in Riemannian parametrization is given as

$$H_{AB}=\begin{pmatrix}0&-\frac{1}{c}&1&0
\\
-\frac{1}{c}&0&0&-1
\\
1&0&0&0
\\
0&-1&0&0\end{pmatrix}.$$

In the $c\to\infty$ limit, the geometry becomes non-Riemannian:

$$H_{AB}=\begin{pmatrix}0&0&1&0
\\
0&0&0&-1
\\
1&0&0&0
\\
0&-1&0&0\end{pmatrix}.$$

Notice that the generalized metric reflects physical phenomena more clearly than the Riemannian metric does.
In the limit $c\to\infty$ with an appropriate Kalb--Ramond field, the Riemannian metric diverges, so physical phenomena cannot be defined in terms of it.
The generalized metric, on the other hand, remains finite in this limit, and thus it correctly captures the stringy fact that physical phenomena still occur.


### 5. Examples

- Buscher Transformation

For simplicity, let us consider the two-dimensional spacetime with the coordinates $(t,x)$, and ignore the Kalb--Ramond field:

$$H_{AB}=\begin{pmatrix}\frac{g_{xx}}{g_{tt}g_{xx}-g_{tx}^{2}}&-\frac{g_{tx}}{g_{tt}g_{xx}-g_{tx}^{2}}&0&0
\\
-\frac{g_{tx}}{g_{tt}g_{xx}-g_{tx}^{2}}&\frac{g_{tt}}{g_{tt}g_{xx}-g_{tx}^{2}}&0&0
\\
0&0&g_{tt}&g_{tx}
\\
0&0&g_{tx}&g_{xx}\end{pmatrix}.$$

THe T-duality transformation exchanging $x\leftrightarrow\tilde{x}$ is described by the following matrix:

$$T^{AB}=\begin{pmatrix}1&0&0&0
\\
0&0&0&1
\\
0&0&1&0
\\
0&1&0&0\end{pmatrix}.$$

Then, the T-duality is given as

$$T^{AB}H_{BC}T^{CD}=\begin{pmatrix}\frac{g_{xx}}{g_{tt}g_{xx}-g_{tx}^{2}}&0&0&-\frac{g_{tx}}{g_{tt}g_{xx}-g_{tx}^{2}}
\\
0&g_{xx}&g_{tx}&0
\\
0&g_{tx}&g_{tt}&0
\\
-\frac{g_{tx}}{g_{tt}g_{xx}-g_{tx}^{2}}&0&0&\frac{g_{tt}}{g_{tt}g_{xx}-g_{tx}^{2}}\end{pmatrix}.$$

Now, we recall the following T-duality transformation we have learned before (with $\alpha'=1$):

$$g_{xx}'=\frac{1}{g_{xx}},\qquad B_{tx}'=\frac{g_{xt}}{g_{xx}},\qquad g_{tt}'=g_{tt}-\frac{g_{xt}^{2}}{g_{xx}}.$$

That is, we have the following Riemannian parametrization:

$$g_{\mu\nu}'=\frac{1}{g_{xx}}\begin{pmatrix}g_{tt}g_{xx}-g_{tx}^{2}&0
\\
0&1\end{pmatrix},\qquad B_{\mu\nu}'=\frac{1}{g_{xx}}\begin{pmatrix}0&g_{tx}
\\
-g_{tx}&0\end{pmatrix},$$

whose corresponding generalized metric is given as

$$H_{AB}'=\begin{pmatrix}g'^{-1}&-g'^{-1}B'
\\
B'g'^{-1}&g'-B'g'^{-1}B'\end{pmatrix}
=\begin{pmatrix}\frac{g_{xx}}{g_{tt}g_{xx}-g_{tx}^{2}}&0&0&-\frac{g_{tx}}{g_{tt}g_{xx}-g_{tx}^{2}}
\\
0&g_{xx}&g_{tx}&0
\\
0&g_{tx}&g_{tt}&0
\\
-\frac{g_{tx}}{g_{tt}g_{xx}-g_{tx}^{2}}&0&0&\frac{g_{tt}}{g_{tt}g_{xx}-g_{tx}^{2}}\end{pmatrix}=(THT)_{AB}.$$


- Isometry of Riemannian Geometry

For a constant $c$, let us consider the following generalized metric. Since $H^{\mu\nu}$ is invertible, this is Riemannian. In fact, we have already seen that this comes from the two-dimensional spacetime with Kalb--Ramond field:

$$H_{AB}=\begin{pmatrix}0&-c&1&0
\\
-c&0&0&-1
\\
1&0&0&0
\\
0&-1&0&0\end{pmatrix}.$$

In the lightcone coordinates $\xi^{A}=(\xi_{+},\xi_{-},\xi^{+},\xi^{-})$, the generalized Lie derivative is given by

$$\hat{L}\_{\xi}H\_{AB}=\begin{pmatrix}2c\partial_{-}\xi^{+}&c(\partial_{+}\xi^{+}+\partial_{-}\xi^{-})&c(\partial_{-}\xi_{+}-\partial_{+}\xi_{-})&2\partial_{-}\xi^{+}
\\
c(\partial_{+}\xi^{+}+\partial_{-}\xi^{-})&2c\partial_{+}\xi^{-}&-2\partial_{+}\xi^{-}&c(\partial_{+}\xi_{-}-\partial_{-}\xi_{+})
\\
c(\partial_{-}\xi_{+}-\partial_{+}\xi_{-})&-2\partial_{+}\xi^{-}&0&2(\partial_{-}\xi_{+}-\partial_{+}\xi_{-})
\\
2\partial_{-}\xi^{+}&c(\partial_{+}\xi_{-}-\partial_{-}\xi_{+})&2(\partial_{-}\xi_{+}-\partial_{+}\xi_{-})&0
\end{pmatrix}.$$

In DFT, we always have $\hat{L}\_{\xi}J\_{AB}=0$, while the condition $\hat{L}\_{\xi}H\_{AB}=0$ means the geometry has symmetries. That is, the DFT Killing vector is defined by $\hat{L}\_{\xi}H\_{AB}=0$. In this case, the Killing vector satisfies the following relations:

$$\xi^{+}=\xi^{+}(x^{+}),\qquad\xi^{-}=\xi^{-}(x^{-}),\qquad\partial_{+}\xi^{+}+\partial_{-}\xi^{-}=0,\qquad\partial_{+}\xi_{-}-\partial_{-}\xi_{+}=0.$$

Solving these, we obtain

$$\xi^{+}=a_{1}x^{+}+a_{2},\qquad\xi^{-}=-a_{1}x^{-}+a_{3},\qquad\xi_{+}=\partial_{+}\chi,\qquad\xi_{-}=\partial_{-}\chi,$$

where $a_{1},a_{2},a_{3}$ are constants and $\chi$ is an arbitrary function. First of all, the 1-form $\xi_{\mu}$ does not generate the Kalb--Ramond gauge transformation:

$$\xi_{\mu}\mathrm{d}x^{\mu}=\mathrm{d}\chi\qquad\implies\qquad\delta B=\mathrm{d}\xi=0.$$

The vector $\xi^{\mu}$ is a linear combination of the following three vectors:

$$\begin{pmatrix}1
\\
0\end{pmatrix},\qquad
\begin{pmatrix}0
\\
1\end{pmatrix},\qquad
\begin{pmatrix}x^{+}
\\
-x^{-}\end{pmatrix}.$$

The first two vectors are spacetime translations, and the last vector is the Lorentz boost:

$$x^{+}\partial_{+}-x^{-}\partial_{-}=t\partial_{x}+x\partial_{t},$$

where we used $x^{\pm}=\frac{t\pm x}{\sqrt{2}}$. Therefore, we conlcude that:

> Killing vectors of generalized metric in the Riemannian parametrization, corresponds to the Killing vectors of the Riemannian manifold.


- Isometry of Non-Riemannian Geometry

Consider the following non-Riemannian generalized metric:

$$H_{AB}=\begin{pmatrix}0&0&1&0
\\
0&0&0&-1
\\
1&0&0&0
\\
0&-1&0&0\end{pmatrix}.$$

In the lightcone coordinates, the generalized Lie derivative reads as

$$\hat{L}\_{\xi}H\_{AB}=\begin{pmatrix}0&0&0&2\partial_{-}\xi^{+}
\\
0&0&-2\partial_{+}\xi^{-}&0
\\
0&-2\partial_{+}\xi^{-}&0&2(\partial_{-}\xi_{+}-\partial_{+}\xi_{-})
\\
2\partial_{-}\xi^{+}&0&2(\partial_{-}\xi_{+}-\partial_{+}\xi_{-})&0\end{pmatrix}.$$

In this case, the Killing vectors are given by

$$\xi^{+}=\xi^{+}(x^{+}),\qquad\xi^{-}=\xi^{-}(x^{-}),\qquad\xi_{+}=\partial_{+}\chi,\qquad\xi_{-}=\partial_{-}\chi.$$

There are infinitely many Killing vectors, which matches the two-dimensional local conformal symmetries.


## V. Double Field Theory

### 1. Doubled Diffeomorphism

In general relativity, let us take an infinitesimal diffeomorphism $x^{\mu}\to x^{\mu}+\xi^{\mu}(x)$ to a 1-form $\omega=\omega_{\mu}(x)\mathrm{d}x^{\mu}$:

$$\begin{aligned}
\delta_{\xi}\omega&=\omega_{\mu}(x+\xi)\mathrm{d}(x^{\mu}+\xi^{\mu})-\omega_{\mu}(x)\mathrm{d}x^{\mu}
\\
&=\xi^{\nu}(\partial_{\nu}\omega_{\mu})\mathrm{d}x^{\mu}+\omega_{\mu}(x)\mathrm{d}\xi^{\mu}
\\
&=(\xi^{\nu}\partial_{\nu}\omega_{\mu}+\omega_{\nu}\partial_{\mu}\xi^{\nu})\mathrm{d}x^{\mu}
\\
&=(L_{\xi}\omega_{\mu})\mathrm{d}x^{\mu}.
\end{aligned}$$

If $\Omega_{\mu\nu\lambda}$ is a tensor, the following property must hold:

$$\delta_{\xi}\Omega_{\mu\nu\lambda}=L_{\xi}\Omega_{\mu\nu\lambda}.$$

Likewise, in DFT, $T_{ABC}$ is a tensor if the following relation holds:

$$\delta_{\xi}T_{ABC}=\hat{L}\_{\xi}T_{ABC}.$$

As a example, let us show that $\partial_{A}f$ is a tensor in DFT. To this end, we use the fact that $\delta_{\xi}$ commutes with the partial derivative (which is because $\delta_{\xi}$ is a transformation of tensors, not the coordinates):

$$\delta_{\xi}(\partial_{A}f)=\partial_{A}(\delta_{\xi}f)=\partial_{A}(\hat{L}_{\xi}f)=\partial\_{A}(\xi^{B}\partial\_{B}f).$$

And, we compute the following generalized Lie derivative:

$$\hat{L}\_{\xi}(\partial\_{A}f)=\xi^{B}\partial\_{B}\partial_{A}f-\partial^{B}f\partial\_{B}\xi\_{A}+\partial_{B}f\partial_{A}\xi^{B}=\delta_{\xi}(\partial_{A}f),$$

where we used the section condition $\partial^{B}f\partial_{B}\xi_{A}=0$, Hence, $\partial_{A}f$ is a tensor. On the other hand, $\partial_{A}T_{B}$ is not a tensor since it is not written in terms of the covariant derivative. For the generalized metric, consider the following expression which is a usual kinetic term in the Lagrangian:

$$H^{AB}\partial_{A}H_{CD}\partial_{B}H^{CD}.$$

This is not a tensor. Hence, we can add an additional term to compensate the difference:

$$\frac{1}{4}H^{AB}\partial_{A}H_{CD}\partial_{B}H^{CD}-H^{AB}\partial_{B}H^{CD}\partial_{D}H_{AC}.$$

Yet, this is not a tensor as well. Again, we add an additional term to define

$$Q=\frac{1}{4}H^{AB}\partial_{A}H_{CD}\partial_{B}H^{CD}-H^{AB}\partial_{B}H^{CD}\partial_{D}H_{AC}-2\partial_{A}\partial_{B}H^{AC}.$$

In this case, $(\delta_{\xi}-\hat{L}_{\xi})Q$ is a total derivative, but nonzero. Hence, $Q$ is not a tensor. We will further discuss the tensorial nature in the next subsection.


### 2. Definition

Remark: Since the Markdown rendering on GitHub does not support calligraphic letters, we will denote the Lagrangian by $L_{0}$ and the Lagrangian density by $L$.
In general, the action is expressed as the integral of the Lagrangian:

$$S=\int\mathrm{d}^{D}x\sqrt{-g}L_{0}.$$

Since the expression $\sqrt{-g}$ does not exist in DFT, we replace it as follows (for convenience, we include the dilaton $\phi$ in this definition):

$$e^{-2d}=e^{-2\phi}\sqrt{-g}.$$

Here, $d$ is called the DFT dilaton.
Since $\sqrt{-g}$ is a scalar density of weight 1, $e^{-2d}$ is also a scalar density of weight 1.
Therefore, its generalized Lie derivative is given as follows:

$$\hat{L}\_{\xi}e^{-2d}=\xi^{A}\partial_{A}e^{-2d}+e^{-2d}\partial_{A}\xi^{A}=e^{-2d}(-2\xi^{A}\partial_{A}d+\partial_{A}\xi^{A}).$$

Using the Leibniz rule $\hat{L}\_{\xi}e^{-2d}=-2e^{-2d}\hat{L}_{\xi}d$, we obtain

$$\hat{L}\_{\xi}d=\xi^{A}\partial_{A}d-\frac{1}{2}\partial_{A}\xi^{A}.$$

If we take an infinitesimal variation $\delta$ on both sides, we notice that

$$\hat{L}\_{\xi}\delta d=\xi^{A}\partial_{A}\delta d.$$

Therefore, $\delta d$ is a scalar (not a density).
The generalized Lie derivative of $d$ takes a somewhat unusual form, so one might think that $d$ is a strange variable rather than a tensor.
However, $\delta d$, which appears when we take a linear perturbation, is a scalar, and therefore $d$ is a physically well-defined variable.
Using the two variables $H_{AB}$ and $d$, we can construct the following scalar (originally constructed in `arXiv:1006.4823 [hep-th]`):

$$S_{(0)}=4(H^{AB}\partial_{A}\partial_{B}d-H^{AB}\partial_{A}d\partial_{B}d+\partial_{A}H^{AB}\partial_{B}d)+\frac{1}{8}H^{AB}\partial_{A}H_{CD}\partial_{B}H^{CD}-\frac{1}{2}H^{AB}\partial_{B}H^{CD}\partial_{D}H_{AC}-\partial_{A}\partial_{B}H^{AB}.$$

Based on this observation, we can contruct the following action (in the integral measure, the doubled coordinate $\tilde{x}_{\mu}$ will be ignored under the section condition $\tilde{\partial}{}^{\mu}=0$):

$$S[H_{AB},d]=\int\mathrm{d}^{D}x\ e^{-2d}S_{(0)}.$$

The theory defined by the above action, is called the Double Field Theory.


### 3. Reduction to Supergravity Action

The above action does not have the Dirichlet boundary condition, since it contains second-order derivatives $\partial_{A}\partial_{B}d$ and $\partial_{A}\partial_{B}H^{AB}$. Hence, we perform an integration by parts and obtain the following quadratic action (i.e., quadratic in first-order derivatives):

$$S[H_{AB},d]=\int\mathrm{d}^{D}x\ e^{-2d}\left(4H^{AB}\partial_{A}d\partial_{B}d-2\partial_{A}H^{AB}\partial_{B}d+\frac{1}{8}H^{AB}\partial_{A}H_{CD}\partial_{B}H^{CD}-\frac{1}{2}H^{AB}\partial_{B}H^{CD}\partial_{D}H_{AC}\right).$$

If we take the Riemannian parametrization, the above action is reduced into the following form:

$$S[g_{\mu\nu},B_{\mu\nu},\phi]=\int\mathrm{d}^{D}x\sqrt{-g}e^{-2\phi}\left[g^{\mu\nu}(\Gamma_{\mu\alpha}^{\beta}{}\Gamma_{\nu\beta}^{\alpha}-\Gamma_{\mu\nu}^{\alpha}{}\Gamma_{\alpha\beta}^{\beta})-\frac{1}{12}H_{\mu\nu\lambda}H^{\mu\nu\lambda}+4\partial_{\mu}\phi\partial^{\mu}\phi+2(g^{\alpha\beta}\Gamma_{\alpha\beta}^{\mu}-g^{\mu\alpha}\Gamma_{\alpha\beta}^{\beta})\partial_{\mu}\phi\right],$$

where the 3-form $H=\mathrm{d}B$ is the $H$-flux (not the generalized metric). Using the integration by parts, we can recover

$$S[g_{\mu\nu},B_{\mu\nu},\phi]=\int\mathrm{d}^{D}x\sqrt{-g}e^{-2\phi}\left(R-\frac{1}{12}H_{\mu\nu\lambda}H^{\mu\nu\lambda}+4\partial_{\mu}\phi\partial^{\mu}\phi\right).$$


## Since GitHub's Markdown renderer seems to have a limit on the length,
## this tutorial is continued in [Part2.md](Part2.md).
