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

$$\xi_{A}\chi^{A}=\xi^{\mu}\tilde{\chi}_{\mu}+\tilde{\xi}_{\mu}\chi^{\mu}.$$

For convenience, we will omit the tilde. That is, $\xi^{\mu}$ and $\xi\_{\mu}$ are completely independent tensors, and DFT does not use the rule shown below, in which indices are raised and lowered with the metric tensor:

$$\xi_{\mu}\ne g_{\mu\nu}\xi^{\nu},\qquad\xi^{\mu}\ne g^{\mu\nu}\xi_{\nu}.$$

Then, the Einstein summation convention is written as follows:

$$\xi_{A}\chi^{A}=\xi_{\mu}\chi^{A}+\xi^{\mu}\chi_{\mu}.$$

That is, the doubled index $A$ splits into the superscript ${}^{\mu}$ and the subscript ${}\_{\mu}$. Applying this to the derivative, we obtain the following, where $f$ is an arbitrary function:

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

That is, $J\_{AB}$ is invariant under the matrices that raise or lower indices, and therefore it is invariant under T-duality. If we extend T-duality, which is simply a transformation that exchanges coordinates, into the form of a rotation group, we obtain the group $\mathbf{O}(D,D)$, which is similar to the Lorentz group $\mathbf{O}(1,3)$ (recall that $D$ is the dimension of spacetime). Since $J\_{AB}$ is invariant under this group, it is called the $\mathbf{O}(D,D)$-invariant metric. Like $H\_{AB}$, which we saw earlier, $J\_{AB}$ should also be written in a calligraphic letter, but in this tutorial we will write it as a roman J.
