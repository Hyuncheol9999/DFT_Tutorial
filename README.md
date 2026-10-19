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
&g_{yy}\to\frac{1}{g_{yy}},
&&g_{yi}\to\frac{B_{yi}}{g_{yy}},
&&B_{yi}\to\frac{g_{yi}}{g_{yy}},
\\
&g_{ij}\to g_{ij}-\frac{g_{yi}g_{yj}-B_{yi}B_{yj}}{g_{yy}},
&&B_{ij}\to B_{ij}-\frac{g_{yi}B_{yj}-B_{yi}g_{yj}}{g_{yy}},
&&\Phi\to\Phi-\frac{1}{2}\ln g_{yy},
\end{aligned}$$

where we decomposed the spacetime coordinates as $x^{\mu}=(y,x^{i})$ for convenience.
In this way, the fact that $(g,B,\phi)$ transform into one another suggests that $B$ and $\phi$ can also be interpreted as gravitational fields.
Indeed, in DFT, these quantities are combined to define the following block matrix.
DFT is the framework in which this quantity is interpreted as a gravitational field and physical phenomena are discussed in terms of it.

$$H_{AB}=\begin{pmatrix}g^{-1}&-g^{-1}B
\\
Bg^{-1}&g-Bg^{-1}B\end{pmatrix},\qquad e^{-2d}=e^{-2\phi}\sqrt{-g}.$$

Notice that the above $H_{AB}$ is usually written as a calligraphic letter (i.e., curly H), however it seems that Markdown on GitHub does not support the LaTeX command `\mathcal`, so I will use a roman H instead.


## II. a
