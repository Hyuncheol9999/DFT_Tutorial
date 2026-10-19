# Tutorials on Double Field Theory
### Hyun-Cheol Kim (kimhc8888@sogang.ac.kr)
I give a tutorial on Double Field Theory (DFT), aimed especially at undergraduate and master's students.
Since I do not like to be talkative, this tutorial focuses on concise explanations of core concepts in DFT.
Through this tutorial, readers will learn the computational techniques used in DFT.
To this end, I have included many examples of each concept in DFT.
This tutorial is based on `arXiv:2505.10163 [gr-qc]`. I will also mention other references if necessary.


## I. Motivation

Before turning to DFT, which is a rather specialized topic, let us first take a broad view of physics.
This will allow us to see where DFT is located on the map of physics.
In general, the fundamental laws of nature are described in the language of quantum field theory, and quantum field theories can be classified into renormalizable and non-renormalizable ones.
When the Lagrangian takes a simple form, as shown below, the theory is renormalizable.
In this case, the counterterms can be computed exactly, and therefore the RG flow can be predicted.
$$S[\phi]=-\frac{1}{2}\int\mathrm{d}^{2}x\left(\partial_{\mu}\phi\partial^{\mu}\phi+m^{2}\phi^{2}+\lambda\phi^{4}\right).$$
