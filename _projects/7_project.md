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
{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/CHSH_Game.ipynb' | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/blog.ipynb %}{% endcapture %}
{% if notebook_exists == 'true' %}
  {% jupyter_notebook jupyter_path %}
{% else %}
  <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

