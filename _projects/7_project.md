---
layout: page
title: CHSH inequality
description: The CHSH inequality is a quantum mechanical test that measures correlations between entangled particles. In the CHSH Game, two players attempt to coordinate their responses without communicating, demonstrating how quantum strategies overcome classical limitations.
citation: true
img: /assets/img/CHSH_portada.png
importance: 1
category: work
related_publications: true
---

"A Bell theorem, which shows that certain predictions of quantum mechanics are inconsistent with the entire class of local hidden-variable theories, is generalized so that it can be applied to feasible experiments. A proposed extension of the Kocher and Commins experiment, on the polarization correlation of a pair of optical photons, will provide a decisive test between quantum mechanics and local hidden-variable theories."
{% cite CHSH1969 %}
“A Bell theorem, which shows that certain predictions of quantum mechanics are inconsistent with the entire class of local hidden-variable theories, is generalized so that it can be applied to feasible experiments. A proposed extension of the Kocher and Commins experiment, on the polarization correlation of a pair of optical photons, will provide a decisive test between quantum mechanics and local hidden-variable theories.” (Clauser et al., 1969)

In a seminal article, Einstein, Podolsky, and Rosen (EPR) described a paradox that led them to question the completeness of quantum mechanics. They argued that quantum theory does not provide a full description of physical systems and should be supplemented with “hidden variables,” which would predetermine the outcomes of any measurement within the system.

EPR viewed the predictions of quantum mechanics as correct only in a statistical sense, derived from these hidden variables. In response, Bohr argued that the supposed paradox disappears if one understands quantum mechanics as describing the interaction between microsystems and measuring devices, rather than attempting to reveal intrinsic properties of the particles themselves.

Bell later showed, using a thought experiment based on Bohm’s version of EPR, that no local hidden-variable theory can fully reproduce the statistical predictions of quantum mechanics. This is particularly striking given Einstein’s belief that quantum theory could not be complete without postulating such variables to preserve locality.

Bell’s theorem also has significant implications: it provides a theoretical foundation for testing whether local hidden-variable theories can account for correlations predicted by quantum mechanics. 

It is assumed that correlations between particles arise from hidden variables, and that locality means a measurement does not depend on what is done at a distant device. By removing the need for perfect correlations, a **mathematical inequality** can be derived that clearly distinguishes the predictions of quantum mechanics from those of local hidden-variable theories.  

Interestingly, in the CHSH scenario, the maximum violation occurs when the measurement angles for the two parties (often called Alice and Bob) are set at **0°, 45° for Alice** and **22.5°, 67.5° for Bob**. With these settings, the CHSH parameter reaches the quantum maximum of  

$$
S_\text{max} = 2\sqrt{2} \approx 2.828,
$$  

which clearly exceeds the classical bound of 2. This result illustrates how entanglement allows correlations that cannot be explained by any local hidden-variable theory.

## CHSH Game
### Classical Case
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CHSH/Clascase.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CHSH/Clascase.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A simple, elegant caption looks good between image rows, after each row, or doesn't have to be there at all.
</div>

The CHSH game can be understood as a simple interrogation problem with two players, Alice and Bob. They are placed in separate rooms and cannot communicate. Each player receives a binary question independently: Alice receives $x \in \{0,1\}$ and Bob receives $y \in \{0,1\}$. They must each provide a binary answer $a, b \in \{0,1\}$, which can be interpreted as 0 = “No” and 1 = “Yes”. The goal is to satisfy the referee’s winning condition:

$$
a \oplus b = x \cdot y
$$

where $\oplus$ denotes addition modulo 2. In words, this condition requires that Alice and Bob give the same answer in three cases ($ (x,y) = (0,0), (0,1), (1,0) $) and different answers in the one remaining case ($ (x,y) = (1,1) $).

Before the game begins, Alice and Bob can agree on a deterministic classical strategy, meaning they decide in advance what their answers will be for each possible question. Let us define:

$$
a(0), a(1) \in \{0,1\} \quad \text{for Alice}, \quad b(0), b(1) \in \{0,1\} \quad \text{for Bob}.
$$

The winning condition then translates into four equations:

$$
\begin{aligned}
(x,y) = (0,0) &\implies a(0) \oplus b(0) = 0 \quad \Rightarrow \quad a(0) = b(0),\\
(x,y) = (0,1) &\implies a(0) \oplus b(1) = 0 \quad \Rightarrow \quad a(0) = b(1),\\
(x,y) = (1,0) &\implies a(1) \oplus b(0) = 0 \quad \Rightarrow \quad a(1) = b(0),\\
(x,y) = (1,1) &\implies a(1) \oplus b(1) = 1 \quad \Rightarrow \quad a(1) \neq b(1).
\end{aligned}
$$

From the first three conditions, we can derive:

$$
a(0) = b(0) = b(1), \quad a(1) = b(0) \quad \Rightarrow \quad a(0) = a(1) = b(0) = b(1).
$$

However, the last condition requires $a(1) \neq b(1)$, which **directly contradicts** the previous equalities. This demonstrates mathematically that **no classical deterministic strategy can satisfy all four cases simultaneously**.

Given this limitation, the best classical strategy is to maximize the number of satisfied conditions. For example, choosing:

$$
a(0) = a(1) = b(0) = 0, \quad b(1) = 0
$$

and applying the winning condition for each input:

| x | y | a ⊕ b | x ⋅ y | Win? |
|---|---|-------|-------|------|
| 0 | 0 | 0     | 0     | ✔    |
| 0 | 1 | 0     | 0     | ✔    |
| 1 | 0 | 0     | 0     | ✔    |
| 1 | 1 | 0     | 1     | ✖    |

Alice and Bob **win 3 out of 4 cases**, which is the best possible outcome classically.  

Since the inputs $(x,y)$ are chosen uniformly at random, each with probability $1/4$, the maximum classical success probability is

$$
P_\text{max classical} = \frac{3}{4} = 75\%.
$$

This result shows explicitly, with all steps, that **classical correlations cannot achieve 100% success in the CHSH game**, and at least one round will always fail, no matter what pre-agreed strategy Alice and Bob choose.

### Quantum Case
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CHSH/Clascase.png" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/CHSH/Clascase.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A simple, elegant caption looks good between image rows, after each row, or doesn't have to be there at all.
</div>

Unlike the classical strategy, in the quantum case Alice and Bob share **a pair of entangled qubits** before being separated. Specifically, they share the Bell state:
 
$$|\Phi^+\rangle = \frac{1}{\sqrt{2}}\left(|00\rangle + |11\rangle\right)$$
 
This state cannot be written as a product of individual states, which means that Alice's and Bob's measurements are **correlated in a non-classical way**, even when spatially separated.

The first thing we need to do is to define a qubit state vector. For each real number (angle) $$\theta$$ in radians, we define:
 
$$
|\psi_\theta\rangle = \cos(\theta)|0\rangle + \sin(\theta)|1\rangle
$$
Let $$|\psi_{a}\rangle$$ denote the state of Alice's qubit, and let $$|\psi_{b}\rangle$$ denote the state of Bob's qubit. 

Then:

$$
|\psi_{a}\rangle = \cos(a)\,|0\rangle + \sin(a)\,|1\rangle
$$

$$
|\psi_{b}\rangle = \cos(b)\,|0\rangle + \sin(b)\,|1\rangle
$$

Looking at the general form, we observe that the inner product between any two such states can be expressed by first writing explicitly the corresponding bra associated with $$\vert\psi_a\rangle$$. In particular, taking the Hermitian conjugate, we obtain:

\begin{equation}
\langle \psi_a \vert = \cos(a)\,\langle 0 \vert + \sin(a)\,\langle 1 \vert
\end{equation}

Thus, the inner product between $$\vert\psi_a\rangle$$ and $$\vert\psi_b\rangle$$ reads:

\begin{equation}
\langle \psi_{a} \vert \psi_{b} \rangle
=
\left( \cos(a)\,\langle 0 \vert + \sin(a)\,\langle 1 \vert \right)
\left( \cos(b)\,\vert 0\rangle + \sin(b)\,\vert 1\rangle \right)
\end{equation}

Expanding this expression by linearity of the inner product, we obtain:

\begin{equation}
\langle \psi_{a} \vert \psi_{b} \rangle
=
\cos(a)\cos(b)\,\langle 0 \vert 0 \rangle
+\cos(a)\sin(b)\,\langle 0 \vert 1 \rangle
+\sin(a)\cos(b)\,\langle 1 \vert 0 \rangle
+\sin(a)\sin(b)\,\langle 1 \vert 1 \rangle
\end{equation}

Using the orthonormality relations of the computational basis:

\begin{equation}
\langle 0 \vert 0 \rangle = 1, \quad
\langle 1 \vert 1 \rangle = 1, \quad
\langle 0 \vert 1 \rangle = 0, \quad
\langle 1 \vert 0 \rangle = 0
\end{equation}

the four terms reduce as follows: the cross terms vanish, and only the diagonal terms survive:

\begin{equation}
\langle \psi_{a} \vert \psi_{b} \rangle
=
\cos(a)\cos(b)\cdot 1
+\cos(a)\sin(b)\cdot 0
+\sin(a)\cos(b)\cdot 0
+\sin(a)\sin(b)\cdot 1
\end{equation}

which simplifies to:

\begin{equation}
\langle \psi_{a} \vert \psi_{b} \rangle
= \cos(a)\cos(b) + \sin(a)\sin(b)
\end{equation}

Finally, we recognize the **cosine difference identity** from trigonometry:

\begin{equation}
\cos(a - b) = \cos(a)\cos(b) + \sin(a)\sin(b)
\end{equation}

Applying this identity directly, we obtain the compact result:

\begin{equation}
\langle \psi_{a} \vert \psi_{b} \rangle = \cos(a-b)
\end{equation}

This is a remarkably clean result: the inner product between two qubit states of this form depends only on the **difference of their angles**. In particular, orthogonal states correspond to $$a - b = \pi/2$$, and identical states give $$\langle \psi_a \vert \psi_a \rangle = \cos(0) = 1$$, confirming normalization.

In detail, since all entries in these state vectors are real numbers, there are no complex conjugates to worry about: the inner product reduces simply to the product of the cosines plus the product of the sines. Applying the angle difference formula from trigonometry then leads directly to the simplification above. This result reveals the geometric interpretation of the inner product between real unit vectors as the cosine of the angle between them.

We now compute the inner product of the tensor product of any two of these qubit states with the Bell state. Recall that:

$$
\vert\Phi^+\rangle = \frac{1}{\sqrt{2}}\left(\vert 00\rangle + \vert 11\rangle\right)
$$

**Step 1: Write the tensor product state.**

According to the postulates of quantum mechanics, the state space of a composite system is the **tensor product** of the state spaces of its subsystems. If Alice's qubit has state space $$\mathcal{H}_A \cong \mathbb{C}^2$$ and Bob's qubit has state space $$\mathcal{H}_B \cong \mathbb{C}^2$$, then the joint system lives in:
 
$$\mathcal{H}_A \otimes \mathcal{H}_B \cong \mathbb{C}^4$$
 
When the two qubits are **unentangled** (i.e., prepared independently), their joint state is a **product state**, where the first factor belongs to $$\mathcal{H}_A$$ and the second to $$\mathcal{H}_B$$. Substituting the explicit form of each qubit state:
 
\begin{equation} \vert\psi_\alpha\rangle \otimes \vert\psi_\beta\rangle = \left(\cos(\alpha)\vert 0\rangle + \sin(\alpha)\vert 1\rangle\right) \otimes \left(\cos(\beta)\vert 0\rangle + \sin(\beta)\vert 1\rangle\right) \end{equation}
 

Given two qubit states defined by angles $$\alpha$$ and $$\beta$$, their tensor product expands as:

\begin{equation} \vert\psi_\alpha\rangle \otimes \vert\psi_\beta\rangle = \left(\cos(\alpha)\vert 0\rangle + \sin(\alpha)\vert 1\rangle\right) \otimes \left(\cos(\beta)\vert 0\rangle + \sin(\beta)\vert 1\rangle\right) \end{equation}

**Step 2: Expand the tensor product.**

Distributing by bilinearity:

\begin{equation} \vert\psi_\alpha\rangle \otimes \vert\psi_\beta\rangle = \cos(\alpha)\cos(\beta)\vert 00\rangle + \cos(\alpha)\sin(\beta)\vert 01\rangle + \sin(\alpha)\cos(\beta)\vert 10\rangle + \sin(\alpha)\sin(\beta)\vert 11\rangle \end{equation}

**Step 3: Take the corresponding bra.**

Taking the Hermitian conjugate (all coefficients are real, so no complex conjugates arise):

\begin{equation} \langle\psi_\alpha \vert \otimes \langle\psi_\beta \vert = \cos(\alpha)\cos(\beta)\langle 00\vert + \cos(\alpha)\sin(\beta)\langle 01\vert + \sin(\alpha)\cos(\beta)\langle 10\vert + \sin(\alpha)\sin(\beta)\langle 11\vert \end{equation}

**Step 4: Set up the inner product with the Bell state.**

We now evaluate the full expression:

\begin{equation} \langle\psi_\alpha \vert \otimes \langle\psi_\beta \vert \Phi^+\rangle = \frac{1}{\sqrt{2}} \Bigl( \cos(\alpha)\cos(\beta)\langle 00\vert + \cos(\alpha)\sin(\beta)\langle 01\vert + \sin(\alpha)\cos(\beta)\langle 10\vert + \sin(\alpha)\sin(\beta)\langle 11\vert \Bigr) \bigl(\vert 00\rangle + \vert 11\rangle\bigr) \end{equation}

**Step 5: Evaluate each term using orthonormality.**

Applying the orthonormality relation $$\langle ij \vert kl\rangle = \delta_{ik}\,\delta_{jl}$$, the cross terms vanish and only the diagonal terms survive:

\begin{equation} \langle\psi_\alpha \vert \otimes \langle\psi_\beta \vert \Phi^+\rangle = \frac{1}{\sqrt{2}} \Bigl( \cos(\alpha)\cos(\beta)\cdot 1 + \cos(\alpha)\sin(\beta)\cdot 0 + \sin(\alpha)\cos(\beta)\cdot 0 + \sin(\alpha)\sin(\beta)\cdot 1 \Bigr) \end{equation}

**Step 6: Simplify.**

\begin{equation} \langle\psi_\alpha \vert \otimes \langle\psi_\beta \vert \Phi^+\rangle = \frac{\cos(\alpha)\cos(\beta) + \sin(\alpha)\sin(\beta)}{\sqrt{2}} \end{equation}

**Step 7: Apply the cosine difference identity.**

Recognizing the trigonometric identity $$\cos(\alpha - \beta) = \cos(\alpha)\cos(\beta) + \sin(\alpha)\sin(\beta)$$, we arrive at the compact result:

\begin{equation}
\langle\psi_\alpha \vert \otimes \langle\psi_\beta \vert \Phi^+\rangle = \frac{\cos(\alpha - \beta)}{\sqrt{2}}
\end{equation}


This expression mirrors the two-qubit inner product computed earlier, with the only difference being the factor of $$1/\sqrt{2}$$ inherited from the normalization of the Bell state. The result shows that the overlap between a product state and the maximally entangled state depends solely on the angular difference $$\alpha - \beta$$ between the two qubit states.

Next, define a unitary matrix for each angle $$\theta$$ as follows:

$$U_\theta = \vert 0\rangle\langle\psi_\theta\vert + \vert 1\rangle\langle\psi_{\theta+\pi/2}\vert$$

because its purpose is to transform the eigenvectors of the observable measured at angle $$\theta$$ into the computational basis, where physical measurement can be performed. The bras $$\langle\psi_\theta\vert$$ and $$\langle\psi_{\theta+\pi/2}\vert$$ encode exactly the measurement directions required by the game, and the kets $$\vert 0\rangle$$ and $$\vert 1\rangle$$ represent the accessible outcomes. This definition ensures that measurements at any angle $$\theta$$ are implemented correctly using only standard measurements while preserving the orthogonality of the states.

To make the structure of $$U_\theta$$ more transparent, we can write it explicitly in matrix form. Recalling that the columns of a unitary matrix are the images of the basis vectors, and substituting the components of each bra, we obtain:

$$U_\theta = \begin{pmatrix} \cos(\theta) & \sin(\theta) \\ \cos(\theta+\pi/2) & \sin(\theta+\pi/2) \end{pmatrix}$$

Applying the standard trigonometric identities $$\cos(\theta + \pi/2) = -\sin(\theta)$$ and $$\sin(\theta + \pi/2) = \cos(\theta)$$, this simplifies to:

$$U_\theta = \begin{pmatrix} \cos(\theta) & \sin(\theta) \\ -\sin(\theta) & \cos(\theta) \end{pmatrix}$$

This matrix has a well-known geometric interpretation: it acts on two-dimensional real vectors by rotating them by an angle of $$-\theta$$ about the origin. The appearance of cosines on the diagonal and sines on the off-diagonal, with the sign alternation, is precisely the hallmark of a **rotation matrix** in $$\mathbb{R}^2$$.

Under the standard parameterization of single-qubit rotations, the family of rotation matrices about the $$y$$-axis of the Bloch sphere is defined as:

$$R_y(\theta) = \begin{pmatrix} \cos(\theta/2) & -\sin(\theta/2) \\ \sin(\theta/2) & \cos(\theta/2) \end{pmatrix}$$

Comparing the two expressions, one can verify directly that substituting $$-2\theta$$ into $$R_y$$ recovers exactly $$U_\theta$$:

$$U_\theta = R_y(-2\theta)$$

The factor of 2 arises from the half-angle convention in the Bloch sphere parameterization, where a physical rotation by angle $$\phi$$ in three-dimensional space corresponds to a unitary rotation by $$\phi/2$$ acting on the qubit state vector.

{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/CHSH_Game.ipynb' | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/blog.ipynb %}{% endcapture %}
{% if notebook_exists == 'true' %}
  {% jupyter_notebook jupyter_path %}
{% else %}
  <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

{% cite delosrios_chsh_2026 %}

