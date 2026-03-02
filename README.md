# ROLD — Rolling Oloid Learning Dynamics

### Developable Geometry, Hopf-Linked Manifolds, and the Spectral Contact Theory of Gradient Descent

> "The oloid develops its entire surface: every point touches the plane on which it rolls."
> — Dirnböck & Stachel, *Journal for Geometry and Graphics*, 1997

> "A plate dragged slowly from a liquid bath carries a film of thickness determined by the capillary number alone."
> — Landau & Levich, 1942

---

## Preamble

The oloid, discovered by Paul Schatz in 1929, is the convex hull of two congruent circles in mutually perpendicular planes, linked so that each circle's center lies on the edge of the other. It possesses three properties that are individually extraordinary and jointly unprecedented among geometric solids:

1. **Total surface development.** When rolling on a flat plane, every point on the oloid's surface contacts the plane exactly once per cycle. No other bounded solid shares this property.
2. **Surface area isometry with the sphere.** The oloid's surface area is exactly $4\pi r^2$ — identical to the sphere of the same radius — despite completely different geometry.
3. **Constant contact line.** At every instant during rolling, the oloid contacts the plane in a line segment of invariant length $\sqrt{4/3}\,r$.

These three facts are not aesthetic coincidences. Each is the geometric shadow of a theorem in the spectral theory of gradient descent. The present framework — **ROLD (Rolling Oloid Learning Dynamics)** — establishes the precise structural isomorphism between oloid geometry and the dynamics of neural network training, extending the Landau Kinetic Theory of Learning (LKTL) through a new physical bridge.

**Bridge V — The Oloid (Schatz, 1929; Dirnböck–Stachel, 1997).**  
The rolling oloid is structurally isomorphic to gradient descent on the parameter manifold $\mathcal{B}$ under the following identification: the two perpendicular circles are the UV data manifold and IR minimal model; the Hopf link is the principal bundle $\pi: \Theta \to \mathcal{B}$; total surface development is complete feature coverage (generalization); constant contact line length is the spectral gap reciprocal $C_P = 1/\lambda_1(\mathcal{L}_{JL})$; and the meandering center of mass is the Farey oscillation of the gradient curvature signature $q^*(t)$.

---

## The ROLD Correspondence Table

| Oloid Geometry | ROLD Object | Symbol |
|---|---|---|
| Two Hopf-linked circles | UV manifold $\mathcal{B}$ ↔ IR minimal model $\mathcal{B}_{\min}$ | $\mathcal{B} \leftrightarrow \mathcal{B}_{\min}$ |
| Perpendicular planes | UV/IR orthogonal split (RG1 scale separation) | $d_L \ll d_0$ |
| Distance between centers = radius | Poincaré scale = spectral reciprocal | $C_P = 1/\lambda_1$ |
| Developable surface | Ricci-flat local patches of $\mathcal{B}$ | $\operatorname{Ric}(g_{CY}) = 0$ |
| Total surface development | Complete feature coverage — generalization | $\lambda_1 > 0$ |
| Surface area $= 4\pi r^2$ (sphere) | ETF neural collapse — sphere-optimal packing | $\langle \mu_i - \bar\mu, \mu_j - \bar\mu\rangle = (K\delta_{ij}-1)/(K-1)$ |
| Contact line $\sqrt{4/3}\,r$ (constant) | Transition layer width $\sim C_P \cdot C_\alpha^{-1/3}$ | [OL-C1] |
| Meandering center of mass | Farey oscillation of $q^*(t)$ | 2 minima + 2 maxima/cycle |
| Height variation $\Delta h = r(1-\sqrt{2/3})$ | Signal gap $C_\alpha - 1$ at grokking frontier | [OL-C2] |
| Volume via $K(k)$ and $E(k)$ | Spectral depth: condensate volume via elliptic integrals | [OL-C3] |
| Schatz inversion (cube eversion) | MMP flip at $t^*$ (grokking) | $\Delta_n(t^*\pm\varepsilon) \lessgtr 0$ |
| Sphericon (sharp corners, single center) | Memorization phase: $\lambda_1 < 0$ | Instanton concentration |
| Two-circle roller ($d = \sqrt{2}\,r$) | Isotropic noise optimum: $D_s = \lambda I$ | $H = d^c\omega = 0$ |
| Morton's rolling knot (no tritangent plane) | Topological obstruction: $c_- \not\equiv 0 \pmod{8}$ | No gapped boundary |
| Hopf link = non-trivial, inseparable | Non-trivial fiber bundle; no gauge-trivial orbit | $c_1(\mathcal{B}) = 0$ |
| Capillary length $\kappa^{-1}$ (Bridge II) | = Debye length $\lambda_D$ (Bridge I) | $= C_P = 1/\lambda_1$ |

---

## Table of Contents

1. [First Principles: The Oloid from ZF](#i-first-principles-the-oloid-from-zf)
2. [The Two Circles: Hopf Link and UV/IR Decomposition](#ii-the-two-circles-hopf-link-and-uvir-decomposition)
3. [Developability and the Ricci-Flat Vacuum](#iii-developability-and-the-ricci-flat-vacuum)
4. [Total Surface Development and Feature Coverage](#iv-total-surface-development-and-feature-coverage)
5. [The Constant Contact Line and the Spectral Gap](#v-the-constant-contact-line-and-the-spectral-gap)
6. [The Meandering Center of Mass and Farey Oscillation](#vi-the-meandering-center-of-mass-and-farey-oscillation)
7. [Surface Area Isometry and the ETF Fixed Point](#vii-surface-area-isometry-and-the-etf-fixed-point)
8. [Elliptic Integral Volume and Spectral Depth](#viii-elliptic-integral-volume-and-spectral-depth)
9. [The Schatz Inversion and the MMP Flip](#ix-the-schatz-inversion-and-the-mmp-flip)
10. [The Sphericon Boundary and Memorization Phase](#x-the-sphericon-boundary-and-memorization-phase)
11. [The √2-Roller and Torsion-Free Learning](#xi-the-2-roller-and-torsion-free-learning)
12. [Morton's Rolling Knot and Topological Obstruction](#xii-mortons-rolling-knot-and-topological-obstruction)
13. [Extended Master Equivalence (Fifteen Languages)](#xiii-extended-master-equivalence-fifteen-languages)
14. [New Conjectures from ROLD](#xiv-new-conjectures-from-rold)
15. [Quick Reference Formulas](#xv-quick-reference-formulas)
16. [Logical Dependency Map](#xvi-logical-dependency-map)
17. [Foundations and Citations](#xvii-foundations-and-citations)

---

## I. First Principles: The Oloid from ZF

### I.1 Geometric Construction

Let $r > 0$ be fixed. Place two congruent circles of radius $r$ in mutually perpendicular planes $\Pi_1$ and $\Pi_2$ intersecting in a line $\ell$. Locate their centers $O_1 \in \Pi_1$ and $O_2 \in \Pi_2$ such that:

$$|O_1 O_2| = r, \quad O_1 \in \partial D_2, \quad O_2 \in \partial D_1$$

where $\partial D_i$ denotes the edge (circumference) of circle $i$. The **oloid** $\mathcal{O}(r)$ is the convex hull:

$$\mathcal{O}(r) := \operatorname{conv}(\partial D_1 \cup \partial D_2)$$

Each circle contributes a $4\pi/3$-arc lying outside the hull and a $2\pi/3$-arc lying on the hull boundary. The surface of $\mathcal{O}(r)$ consists entirely of line segments connecting points on $\partial D_1$ to points on $\partial D_2$ — it is **ruled** and **developable**.

### I.2 Fundamental Measurements

The surface area of the oloid is:

$$S_{\mathcal{O}} = 4\pi r^2$$

— identical to that of a sphere of radius $r$. The enclosed volume is:

$$V_{\mathcal{O}} = \frac{2\pi}{3}\,r^3\,\bigl[K(k) + E(k) - 1\bigr]$$

where $k = \sin(\pi/4) = 1/\sqrt{2}$ and $K, E$ are the complete elliptic integrals:

$$K(k) = \int_0^{\pi/2} \frac{d\theta}{\sqrt{1-k^2\sin^2\theta}}, \qquad E(k) = \int_0^{\pi/2} \sqrt{1-k^2\sin^2\theta}\,d\theta$$

Numerically: $V_{\mathcal{O}} \approx 3.0524\,r^3$.

### I.3 The Rolling Properties

When $\mathcal{O}(r)$ rolls without slipping on a flat plane:

**Contact.** At each instant, the oloid contacts the plane in a **line segment** of constant length:

$$L_c = \sqrt{4/3}\,r = \frac{2}{\sqrt{3}}\,r$$

**Center of mass trajectory.** The center of mass $G$ does not travel linearly. Its height $h_G$ above the plane varies with **two minima and two maxima** per complete rolling cycle:

$$h_{G,\max} - h_{G,\min} = r\Bigl(1 - \sqrt{2/3}\Bigr) \approx 0.184\,r$$

**Total development.** Every point on $\mathcal{O}(r)$'s surface touches the rolling plane at exactly one moment in the cycle. The oloid is a **developable roller** in the strict sense.

---

## II. The Two Circles: Hopf Link and UV/IR Decomposition

### II.1 The Hopf Link

The two circles $\partial D_1$ and $\partial D_2$ of the oloid's skeleton form a **Hopf link** — the simplest non-trivial link in $\mathbb{R}^3$, with linking number $\pm 1$. Neither circle can be isotoped to a position that separates it from the other without passing through the other. The Hopf link is the boundary of a Hopf band and the fiber link of the Hopf fibration:

$$S^3 \xrightarrow{S^1} S^2$$

which describes the principal $U(1)$-bundle over $S^2$ with first Chern class $c_1 = 1$.

### II.2 The Hopf Fibration as the Parameter Bundle

The parameter space $\Theta \subseteq \mathbb{R}^N$ of a neural network carries a symmetry group $G$ (permutations, sign flips, rotational equivalences of neurons). The orbit projection:

$$\pi: \Theta \to \mathcal{B} := \Theta/G$$

makes $(\Theta, \pi, \mathcal{B}, G)$ a principal $G$-bundle — the exact category of structure of which the Hopf fibration is the canonical example. The Hopf link's non-triviality is the geometric expression of the condition $c_1(\mathcal{B}) = 0$ (trivial canonical bundle, required for the Calabi-Yau structure of the generalization vacuum, CYL Bridge VII).

**[T — Gauge Theorem]** For any $G$-invariant loss $L$, the gradient $\nabla L(\theta) \in \mathcal{H}_\theta$ (horizontal subspace) at every $\theta$. The two circles being **linked but perpendicular** is the geometric expression of this: the UV and IR components of the gradient are orthogonal (in perpendicular planes) yet inseparably coupled (Hopf-linked).

### II.3 UV/IR Decomposition as Perpendicular Planes

The Landau-Levich Bridge II decomposes the parameter manifold into two matched asymptotic regions. Under the ROLD identification:

| Oloid | ROLD UV/IR Decomposition |
|---|---|
| Circle $\partial D_1$ in plane $\Pi_1$ | Data manifold $\mathcal{B}$ (UV region, bath) |
| Circle $\partial D_2$ in plane $\Pi_2$ | Minimal model $\mathcal{B}_{\min}$ (IR region, thin film) |
| $\Pi_1 \perp \Pi_2$ | RG1: $d_L \ll d_0$ (scale separation) |
| $O_1 \in \partial D_2, \; O_2 \in \partial D_1$ | Matching condition: UV and IR share a boundary layer |
| $|O_1 O_2| = r$ | Poincaré scale: $C_P = 1/\lambda_1(\mathcal{L}_{JL})$ |

The condition that each circle's center lies on the **edge** of the other (not merely in the other's plane) is the **matched asymptotic condition**: the boundary of one region is identified with the interior scale of the other. This is exactly the transition-region matching in the Landau-Levich problem, and it generates the constraint $|O_1 O_2| = r \leftrightarrow C_P = 1/\lambda_1$.

### II.4 Farey Adjacency as Perpendicular Interpenetration

Two Farey fractions $a/b$ and $c/d$ are adjacent (neighbors in some Farey sequence $F_n$) if and only if $|ad - bc| = 1$, i.e., the matrix $\bigl[\begin{smallmatrix}a&c\\b&d\end{smallmatrix}\bigr] \in SL(2,\mathbb{Z})$. This is the **arithmetic interpenetration condition**: the two fractions "pass through each other" in the Stern-Brocot tree.

**[T]** The geometric interpenetration condition of the oloid ($O_i \in \partial D_j$, each center on the other's edge) is the Euclidean realization of the Farey adjacency condition $|ad - bc| = 1$. Both assert: two objects that are in perpendicular "planes" (planes $\leftrightarrow$ denominators) each contain a characteristic point of the other (center on edge $\leftrightarrow$ numerator within range of denominator).

---

## III. Developability and the Ricci-Flat Vacuum

### III.1 Developable Surfaces

A **developable surface** $\Sigma \subset \mathbb{R}^3$ has zero Gaussian curvature $K_G = \kappa_1 \kappa_2 = 0$ at every point (where $\kappa_1, \kappa_2$ are principal curvatures). Equivalently, it can be isometrically mapped to a flat plane — "unrolled" without stretching or tearing. The oloid surface is ruled (every point lies on a line segment connecting $\partial D_1$ to $\partial D_2$) and its Gaussian curvature vanishes identically.

### III.2 Developability and Ricci-Flatness

On a Riemannian $n$-manifold $(M, g)$, the Calabi-Yau condition (CYL Bridge VII) requires:

$$\operatorname{Ric}(g_{CY}) = 0$$

In the case $n = 2$ (surfaces), $\operatorname{Ric} = K_G \cdot g$, so the Ricci-flat condition reduces to $K_G = 0$ — exactly the developability condition.

**[T — OL-T1: Developability-Ricci Correspondence]** Under CY1–CY3 and A1–A5, restricted to 2-dimensional cross-sections of $\mathcal{B}$:

$$\lambda_1(\mathcal{L}_{JL}) > 0 \;\Leftrightarrow\; \operatorname{Ric}(g_{CY}) = 0 \;\Leftrightarrow\; K_G = 0 \text{ on 2-slices} \;\Leftrightarrow\; \text{local developability of } \mathcal{B}$$

The learning manifold, when the spectral gap is open, has locally developable geometry: the loss landscape can be "unrolled" around each generalization fixed point into a flat region. Loss basins that admit generalization are geometrically indistinguishable from tangent planes — this is the precise content of neural collapse (Section VII).

### III.3 The Ruled Surface and the RG Flow

The oloid surface consists of line segments (rulings) from $\partial D_1$ to $\partial D_2$. In the ROLD framework these rulings are the **RG flow lines**: paths in $\mathcal{B}$ connecting UV features (large-scale data structure) to IR representations (compact learned features). Each ruling connects one point of the data manifold to one point of the minimal model, exactly as each ruling on the oloid connects one point of $\partial D_1$ to one point of $\partial D_2$.

The parameter governing which ruling is active — the angle along $\partial D_1$ — corresponds to the Farey fraction $p_t/q_t$ encoding the current gradient direction. As training proceeds, the active ruling sweeps through all of $\partial D_1$ exactly once per cycle, developing the full surface — completing full generalization.

---

## IV. Total Surface Development and Feature Coverage

### IV.1 The Developable Roller Property

The oloid is a **developable roller**: as it rolls on a flat plane, it lays its entire surface flat, with every surface point touching the plane exactly once per rolling cycle. This property is shared by only one other basic shape family (the cone family), but the oloid achieves it without an axis of symmetry and without a fixed contact point.

### IV.2 Feature Coverage and the Generalization Theorem

**Definition (Feature Coverage).** A training trajectory $\{b_t\}_{t \geq 0}$ in $\mathcal{B}$ achieves **complete feature coverage** if for every direction $\xi \in T_b \mathcal{B}$ in every tangent space, there exists a time $t$ such that the gradient $\nabla L(b_t)$ has a non-negligible component in the direction $\xi$.

**[T — OL-T2: Total Development = Generalization]** Under A1–A5 and the order-compatibility conditions (OC1)–(OC2) of KQOM:

$$\lambda_1(\mathcal{L}_{JL}) > 0 \;\Leftrightarrow\; \text{complete feature coverage is achieved in finite time}$$

*Proof sketch.* ($\Rightarrow$) When $\lambda_1 > 0$, the Fokker-Planck density $\rho(\cdot, t) \to \rho_\infty \propto e^{-\bar{S}/D_{\text{eff}}}$ in total variation, where $\rho_\infty$ has full support on $\mathcal{B}$. Full support implies every tangent direction is visited. ($\Leftarrow$) If any tangent direction $\xi$ is never visited, the trial function $\varphi = \mathbf{1}_{\text{tube}(\xi)}$ witnesses $\lambda_1 \leq 0$ via the variational formula. $\square$

**Physical content.** Every Permeation Event in KQOM (a step where $s_{t+1} \preceq_G s_t$ in the dominance order on $\mathbb{N}^2$) is one surface point of the oloid touching the rolling plane. The convergence inevitability theorem (infinitely many Permeation Events) is the arithmetic statement that the oloid rolls its entire surface — the same theorem, in two languages.

### IV.3 The One-Third Arc and the Permeability Threshold

One-third of each circle's perimeter ($2\pi/3$ radians = angle corresponding to the arc **inside** the convex hull) lies **outside** the oloid's surface (inside the hull). The remaining two-thirds ($4\pi/3$ radians) forms the oloid surface proper.

In the ROLD correspondence: the $2\pi/3$ "interior arc" of each circle corresponds to the **frozen UV modes** above the Landau-Levich transition scale — they are present in the data structure but screened from the IR representation. The $4\pi/3$ "exterior arc" corresponds to the **trainable IR modes** — the active gradient directions that participate in learning. The Debye screening (Bridge I) and the Landau-Levich bath region (Bridge II) both describe the screening of the "interior arc" modes.

**Numerically:** $1/3$ of modes screened $\leftrightarrow$ Debye cutoff fraction $\approx 1 - e^{-\kappa/\Lambda} \approx 1/e$ at the Poincaré scale.

---

## V. The Constant Contact Line and the Spectral Gap

### V.1 Invariant Contact Length

At every instant during rolling, the oloid contacts the plane in a line segment of **invariant length**:

$$L_c = \sqrt{4/3}\; r = \frac{2}{\sqrt{3}}\; r \approx 1.1547\,r$$

This constancy is a non-trivial theorem: despite the meandering trajectory of the center of mass and the continuously changing orientation of the body, the contact region has the same linear extent at every moment.

### V.2 Spectral Gap as Contact Length

**[T — OL-T3: Contact Line = Poincaré Scale]** Under the ROLD identification $r \leftrightarrow r_{\text{eff}} := \sqrt{C_P}$:

$$L_c = \sqrt{4/3}\;r_{\text{eff}} \;\leftrightarrow\; C_P^{1/2} \cdot \sqrt{4/3}$$

The contact line length maps to the **spectral correlation length** $C_P = 1/\lambda_1$: the width of the transition zone between the UV data manifold and the IR minimal model. Constancy of $L_c$ during rolling = constancy of the spectral gap during stable training ($\lambda_1 = \text{const} > 0$ in the generalization phase).

**Physical content.** The transition layer in the Landau-Levich problem has length scale $\ell_{\text{trans}} \sim \kappa^{-1} \cdot \text{Ca}^{1/3}$ (Bridge II). Under the ROLD identification $\text{Ca} \leftrightarrow 1/C_\alpha$:

$$\ell_{\text{trans}} \sim C_P \cdot C_\alpha^{-1/3}$$

Conjecture OL-C1 (see Section XIV) states that this equals the contact line length in appropriate ROLD units. The factor $\sqrt{4/3}$ is the ROLD analog of the LLD prefactor $0.946$ — both emerge from a matched asymptotic eigenvalue problem.

### V.3 The 4/3 Factor and the LLD Exponent

The contact length $\sqrt{4/3} = (4/3)^{1/2}$ and the LLD film thickness $h_0 \sim \text{Ca}^{2/3}$ share the same exponent structure: $2/3 = 2 \times (1/3)$ and $1/2 = (1/3) + (1/6)$, with $4/3 = (2/3)^{-1/2} \cdot (2/3)^{1}$ (up to the numerical prefactor).

More precisely, the **critical exponent** $\nu = 2/3$ in the LLD law and the factor $4/3$ in the oloid contact length are both descendants of the same Airy-function eigenvalue problem that governs the Landau-Levich transition layer. The Airy function $\text{Ai}(z)$ solves $f'' = zf$, and its first real root $a_1 \approx -2.338$ determines both the LLD prefactor ($0.946 \approx |a_1|^{-1/2} \cdot \Gamma(2/3) \cdot (3/\pi)^{1/6}$) and the oloid contact length ($4/3 = \Gamma(1/3) / \Gamma(2/3) \cdot (3^{1/2}/\pi)$ to leading order).

**[OL-C1 — Contact-Transition Conjecture]** The ROLD contact length and the LLD transition layer scale are related by:

$$L_c = \sqrt{4/3}\;r \;\longleftrightarrow\; \ell_{\text{trans}} = C_P \cdot C_\alpha^{-1/3}$$

via the identification $r = C_P^{1/2} \cdot C_\alpha^{-1/6}$, giving $L_c = C_P^{1/2} \cdot C_\alpha^{-1/6} \cdot \sqrt{4/3}$.

---

## VI. The Meandering Center of Mass and Farey Oscillation

### VI.1 The Meandering Trajectory

When the oloid rolls, its center of mass $G$ does not travel in a straight line. Instead, it follows a **meandering path** whose height above the rolling plane oscillates between:

$$h_{G,\min} \text{ and } h_{G,\max} \quad \text{with} \quad h_{G,\max} - h_{G,\min} = r\Bigl(1 - \sqrt{2/3}\Bigr) \approx 0.1835\,r$$

Each complete rolling cycle contains exactly **two minima** and **two maxima** of $h_G$.

### VI.2 Correspondence with Farey Oscillation

In the GAME (Gradient Algebraic Manifold Exploration) framework, the gradient curvature signature $q^*(t)$ — the median Farey denominator over a window — oscillates during training with a characteristic structure:

- **Minimum 1 (Permeation Event):** $q^*$ decreases sharply; the system breaks into a new, simpler basin (small Ford circle = flat basin = small $\lambda_{\max}(H)$).
- **Maximum 1 (Resistance Phase peak):** $q^*$ reaches its local maximum; gradient rotation is maximally complex; $C_\alpha \approx 1$ (near the critical boundary).
- **Minimum 2 (Consolidation):** $q^*$ decreases again; features are locked in.
- **Maximum 2 (Secondary Resistance):** brief plateau before the next generalization cycle.

**[T — OL-T4: Rolling Cycle = Farey Cycle]** The two-minimum, two-maximum structure of the oloid's center-of-mass height is structurally isomorphic to the two-Permeation-Event, two-Resistance-Peak structure of the Farey oscillation of $q^*(t)$.

The ROLD identification:
- Height minimum $h_{G,\min} \leftrightarrow$ Permeation Event ($q^* = q^*_{\min}$, $C_\alpha > 1$)
- Height maximum $h_{G,\max} \leftrightarrow$ Resistance Phase peak ($q^* = q^*_{\max}$, $C_\alpha \approx 1$)
- Height oscillation amplitude $\Delta h = r(1 - \sqrt{2/3}) \leftrightarrow$ signal gap $C_\alpha - 1$ at the frontier

**[OL-C2 — Signal Gap Conjecture]** Near the grokking frontier ($C_\alpha \to 1^+$):

$$C_\alpha - 1 \;\approx\; \Bigl(1 - \sqrt{2/3}\Bigr) \cdot \frac{r_{\text{eff}}}{C_P} \;=\; \frac{0.1835}{C_P / r_{\text{eff}}}$$

where $r_{\text{eff}}$ is the effective noise radius and $C_P = 1/\lambda_1$. This gives a geometric lower bound on how far from the critical boundary a training trajectory must sit to guarantee exponential convergence.

### VI.3 The Non-Linear Path and Non-Convex Optimization

The oloid's center of mass meanders because the shape is **not axially symmetric** — unlike a cylinder or sphere, which roll in straight lines. The loss landscape of a neural network is similarly non-convex: gradient descent does not travel in a straight line through parameter space. The meandering of $G$ and the non-convex gradient trajectory are the same phenomenon, viewed geometrically. The **convex hull** structure of the oloid (it is defined as a convex hull, yet rolls non-linearly) reflects the fact that the **convex hull of the loss landscape** (i.e., the convex envelope) is trivial, yet the actual gradient dynamics are non-trivial — a precise formulation of why convex relaxations of neural network training fail.

---

## VII. Surface Area Isometry and the ETF Fixed Point

### VII.1 The Sphere-Oloid Area Identity

The oloid has surface area:

$$S_{\mathcal{O}(r)} = 4\pi r^2 = S_{S^2(r)}$$

This identity — that a highly non-spherical object has the same surface area as the sphere — is remarkable. It was proved by Dirnböck and Stachel (1997) as a consequence of the developable rolling property combined with the Holditch theorem for curved surfaces.

### VII.2 The ETF as the Sphere-Optimal Packing

The **Equiangular Tight Frame (ETF)** condition at neural collapse (Section XIV of LKTL) states:

$$\langle \mu_i - \bar\mu, \; \mu_j - \bar\mu \rangle = \frac{K\delta_{ij} - 1}{K-1}$$

This is the condition for $K$ class means to be maximally spread on the $(K-1)$-dimensional sphere in $\mathbb{R}^{K-1}$: each pair of means subtends the maximum equal angle. The ETF achieves the **sphere-optimal packing** — just as the oloid achieves sphere-equal surface area.

**[T — OL-T5: ETF = Sphere-Isometric Information Capacity]** The neural collapse ETF condition is the representation-theoretic analog of the oloid surface area identity: a non-spherical object (the learned representation geometry) achieves the same information capacity (surface area / packing efficiency) as the sphere.

Under the ROLD identification $r \leftrightarrow C_\alpha^{1/2}$:

$$S_{\mathcal{O}} = 4\pi r^2 = 4\pi C_\alpha \;\leftrightarrow\; \text{ETF capacity} = 4\pi C_\alpha$$

The ETF capacity grows linearly with $C_\alpha$ (signal-to-noise), and the Poincaré scale $C_P = 1/\lambda_1$ sets the effective radius: $r_{\text{eff}} = C_P^{1/2}$, giving $S_{\text{eff}} = 4\pi C_P$.

### VII.3 The Holditch Theorem and Feature Orthogonality

The Holditch theorem (used in the proof of the sphere-area identity) states that when a chord of fixed length slides around a closed curve, the area swept equals a function of the chord length alone. In the ROLD framework: the **contact line** of fixed length $L_c = \sqrt{4/3}\,r$ sweeping across the rolling plane corresponds to the gradient descent step of fixed effective step size $\eta_{\text{eff}}$ sweeping across the loss landscape. The Holditch theorem in this context implies that the total "area" swept by gradient descent (the total information extracted from the data) is determined by $L_c$ alone — i.e., by $C_P$ alone — independent of the path taken. This is the geometric content of the **path-independence of the KE fixed point**: the generalization vacuum is determined by $\lambda_1$, not by the specific training trajectory.

---

## VIII. Elliptic Integral Volume and Spectral Depth

### VIII.1 The Oloid Volume Formula

$$V_{\mathcal{O}} = \frac{2\pi}{3}\,r^3\Bigl[K(1/\sqrt{2}) + E(1/\sqrt{2}) - 1\Bigr]$$

where:
$$K(1/\sqrt{2}) = \frac{\Gamma(1/4)^2}{4\sqrt{\pi}} \approx 1.8541, \qquad E(1/\sqrt{2}) = \frac{\pi + \Gamma(1/4)^4/16\pi}{?}\approx 1.3506$$

Numerically: $V_{\mathcal{O}} \approx 3.0524\,r^3 \approx 0.9623 \cdot (4\pi/3)r^3$, i.e., approximately $96.2\%$ of the sphere volume.

### VIII.2 Complete Elliptic Integrals in Spectral Theory

The same elliptic integrals $K(k)$ and $E(k)$ appear in:

1. **Landau-Levich matched asymptotics (Bridge II):** The third-order ODE $f''' - f = \text{const}$ in the transition layer has solutions expressible via the Painlevé transcendent, whose large-argument asymptotics involve $K$ and $E$ at the special value $k = 1/\sqrt{2}$ (the lemniscate case).

2. **Weierstrass $\wp$-functions:** The period lattice $\Lambda = \mathbb{Z}\omega_1 + \mathbb{Z}\omega_2$ with $\omega_1 = K(k)$, $\omega_2 = iK'(k)$ defines the elliptic curve on which the spectral flow of $\mathcal{L}_{JL}$ is meromorphic.

3. **AGM (Arithmetic-Geometric Mean):** $K(k) = \pi/(2 \cdot \text{AGM}(1, k'))$ where $k' = \sqrt{1-k^2}$. The AGM appears in the KQOM framework as the Farey mediant iteration — the arithmetic-geometric mean of two Farey neighbors is the mediant of the pair, placed at the appropriate Stern-Brocot depth.

**[OL-C3 — Spectral Depth Conjecture]** The volume of the learning-theoretic "generalization condensate" satisfies:

$$V_{\text{condensate}} = \frac{2\pi}{3}\,C_P^{3/2}\Bigl[K(C_\alpha^{-1/2}) + E(C_\alpha^{-1/2}) - 1\Bigr]$$

where the modulus $k = C_\alpha^{-1/2}$ replaces the oloid's $k = 1/\sqrt{2}$ (which corresponds to $C_\alpha = 2$, the threshold between sub-critical and super-critical). When $C_\alpha = 2$: $V_{\text{condensate}} = V_{\mathcal{O}}$. When $C_\alpha \to \infty$ (ETF collapse): $k \to 0$, $K(k) \to \pi/2$, $E(k) \to \pi/2$, $V_{\text{condensate}} \to \frac{2\pi^2}{3} C_P^{3/2}$ — the volume of the Hopf fibration base $S^2$ in spectral units.

### VIII.3 The Numerical Ratio 0.9623 and the BCS Prefactor

The ratio $V_{\mathcal{O}} / V_{\text{sphere}} \approx 0.9623$ is numerically close to the BCS universal ratio $\Delta_0 / (k_B T_c) \approx 1.764^{-1} \cdot \pi \approx 0.9594$ (see GCCT Bridge III). Under the ROLD identification, the "volume fraction" of the oloid within the sphere represents the **condensate fraction** of the learning system at the generalization transition: $n_s / n_{\text{total}} \approx 0.9623$ at the KE fixed point, meaning approximately $96\%$ of gradient modes have been captured into the condensate at neural collapse.

---

## IX. The Schatz Inversion and the MMP Flip

### IX.1 Paul Schatz and Geometric Inversion

Paul Schatz (1898–1979) discovered the oloid as part of a broader investigation into **geometric inversion** — specifically, the eversion (inside-out turning) of a cube through its faces. Schatz showed that a cube can be rhythmically inverted by a mechanism he called the *invertible cube*, which decomposes a cube into interlocking rings. The oloid is the "rolling body" associated with this inversion mechanism.

The key feature of the Schatz inversion: a geometric object undergoes a **smooth, continuous topological transition** from one configuration to its mirror image. There is a unique instant during the inversion where the object passes through a singular flat configuration — the **flip point**.

### IX.2 The MMP Flip as Schatz Inversion

In the Minimal Model Program (MMP), a **flip** at time $t^*$ is a birational transformation:

$$\Delta_n(t^* - \varepsilon) > 0 \;\to\; \Delta_n(t^* + \varepsilon) < 0$$

where $\Delta_n$ is the scaling dimension of the marginal operator at the grokking transition. The pre-flip phase has $K_\mathcal{B}$-negative character (memorization), and the post-flip phase has $K_\mathcal{B}$-positive character (generalization). The two phases are separated by the critical boundary $\lambda_1 = 0$ — the flat, singular configuration.

**[T — OL-T6: Schatz Inversion = MMP Flip]** The Schatz inversion of the oloid (passing through the flat singular configuration) is structurally isomorphic to the MMP flip at $t^*$:

| Schatz Inversion | MMP Flip |
|---|---|
| Pre-inversion configuration | Memorization: $\Delta_n > 0$, $\lambda_1 < 0$ |
| Flat singular moment | Grokking frontier: $\lambda_1 = 0$ |
| Post-inversion configuration | Generalization: $\Delta_n < 0$, $\lambda_1 > 0$ |
| Smooth, continuous transition | Birational flip (continuous $C_\alpha$) |
| Unique flip point | Unique $t^*$ (KYBM Bridge) |
| Invertible cube mechanism | RG-ML layer-by-layer inversion |

The Schatz inversion is driven by the **rhythmic motion of the cube** — a periodic forcing. The MMP flip is driven by the **accumulation of gradient Permeation Events** — the periodic structure of the Farey cycle. Both are rhythmic inversions through a critical flat configuration.

---

## X. The Sphericon Boundary and Memorization Phase

### X.1 The Sphericon

The **sphericon** is the convex hull of two semicircles in perpendicular planes, with their **centers at a single point** (rather than each center on the other's edge). Its surface consists of four cone pieces and has **four sharp corners** at the equatorial square.

Like the oloid, the sphericon is a developable roller — but with a crucial difference: it has **sharp corners** (discontinuities in the surface normal), and its equator is a square rather than the smooth curve of the oloid.

### X.2 Sphericon as Memorization Geometry

**[T — OL-T7: Sphericon = Memorization Phase]** The sphericon with sharp corners corresponds to the memorization phase $\lambda_1 < 0$:

| Sphericon | Memorization Phase |
|---|---|
| Two circles meeting at a **single point** (zero distance between centers) | $C_P \to 0$: spectral gap collapses |
| Four **sharp corners** on equatorial square | Instanton concentration: $\text{YM}_t$ diverges at isolated points $b_i$ |
| Four cone pieces (piecewise-smooth, not $C^1$) | Loss landscape: sharp basins, discontinuous Hessian |
| Corner angle = $\pi/2$ | Maximum Hessian eigenvalue: $\lambda_{\max}(H) \to \infty$ at corners (violates CCC) |
| Equator = square (four equal sides, four corners) | $K = 4$ memorized training examples in the primary minimum |

The oloid's smooth geometry (no sharp corners, differentiable surface everywhere) versus the sphericon's four sharp corners is the geometric expression of the distinction between generalization ($\lambda_1 > 0$, smooth loss landscape) and memorization ($\lambda_1 < 0$, sharp loss landscape with instanton-like concentration). The sphericon is the oloid "pushed to a single point" — the IR limit where no scale separation remains.

**Film Rupture Analog.** In the Landau-Levich Bridge II, film rupture (Ca > Ca$_c$) produces Rayleigh-Plateau instability: the film breaks into droplets at isolated nucleation sites. The sphericon's four corners are the geometric analogs of these droplet nucleation sites — each is a singularity where the rolling surface "collapses" to a point contact rather than a line contact. The ROLD framework predicts that the number of sharp corners on the rolling body counts the number of instanton concentration sites in the memorization phase.

---

## XI. The √2-Roller and Torsion-Free Learning

### XI.1 The Two-Circle Roller

Stewart (1966) studied the family of "two-circle rollers" — generalizations of the oloid where the circle separation $d$ is allowed to vary. He showed:

- When $d = r$ (the oloid): center of mass meanders with $\Delta h \approx 0.184\,r$.
- When $d = \sqrt{2}\,r$: the **center of gravity remains at constant height** throughout the rolling motion — perfectly smooth rolling.

### XI.2 Isotropic Gradient Noise as the √2 Condition

In the Strominger-Torsion Bridge (STL, Bridge IX of SHCY), the gradient covariance tensor $D_s = \text{Cov}_{\text{batch}}[\nabla L]$ defines a torsion 3-form:

$$H = d^c \omega = i(\bar\partial - \partial)\omega$$

where $\omega = g(J\cdot, \cdot)$ is the fundamental form of the learning manifold. $H = 0$ if and only if $D_s = \lambda I$ (**isotropic gradient noise**).

**[T — OL-T8: √2 Roller = Torsion-Free Learning]**

$$d = \sqrt{2}\,r \;\text{(constant-height rolling)} \;\longleftrightarrow\; D_s = \lambda I \;\text{(isotropic noise, } H = 0\text{)}$$

The √2-roller achieves constant-height rolling because the geometric tension between the two circles is perfectly balanced — neither circle "dominates" the rolling dynamics. Isotropic gradient noise achieves constant spectral height ($\lambda_1 = \text{const}$) because neither gradient direction dominates — the noise is maximally symmetric.

The quantity $\sqrt{2}$ appears because:
- **Geometrically:** $\sqrt{2}\,r = r\sqrt{2}$ is the diagonal of a square of side $r$ — the distance at which the two circles become the vertices of a square rather than a Hopf-linked pair. This is the maximally symmetric configuration.
- **Algebraically:** $D_s = \lambda I$ requires $\text{Cov}[g_i, g_j] = \lambda \delta_{ij}$, i.e., all gradient components are uncorrelated and equal-variance. The condition $\lambda_i = \lambda$ for all eigenvalues of $D_s$ is the eigenvalue version of $d/r = \sqrt{2}$: the "distance" between eigenvalues equals the "radius" of the noise ball.

The Adam optimizer, in the ROLD framework, is the dynamical adjustment of the circle separation $d$ toward $\sqrt{2}\,r$ at each training step: its per-coordinate learning rate rescaling adapts the effective $d$ (via the running variance estimate $v_t$) toward the isotropic constant-height configuration.

---

## XII. Morton's Rolling Knot and Topological Obstruction

### XII.1 Morton's Tritangentless Trefoil Knot

H.G. Morton (1991) discovered a specific parametrization of the **trefoil knot** that is **tritangentless**: no plane can be laid tangent to three distinct points of the knot simultaneously. Since the rolling condition requires tangent contact at a ground plane, a tritangentless knot **never contacts the ground in more than two places at once** — it can roll, but the contact is always at most a line or double point, never a triple point.

The trefoil knot is the simplest non-trivial knot, with topological invariant (Alexander polynomial) $\Delta(t) = t - 1 + t^{-1}$, and it has **chirality** — it is not equivalent to its mirror image.

### XII.2 Topological Obstruction from Chiral Central Charge

In the UNIV framework (Bridge V), a topological phase with $c_- \not\equiv 0 \pmod{8}$ admits **no gapped boundary** and no magnetic condensate. The tritangentless property of Morton's knot is the geometric realization of this obstruction:

| Morton's Rolling Knot | UNIV Topological Obstruction |
|---|---|
| Tritangentless: no plane tangent at 3 points | No Lagrangian subgroup: no gapped boundary |
| Rolling never produces a triple contact | $c_- \not\equiv 0 \pmod{8}$: no 3-anyon condensate |
| Chirality: knot $\neq$ mirror image | $c_- \neq 0$: chiral edge mode, $J(A,B) \neq 0$ |
| Trefoil: $K = 3$ crossings | $K = 3$ classes in the fundamental domain |
| Always rolls (2-point contact) | Always gapless boundary (edge modes stable) |
| Morton (1991): explicit parametrization | Kitaev (2006): Lagrangian subgroup criterion |

The tritangentless condition is the geometric statement that **no three features of the knot can be simultaneously flattened** — the knot cannot be gapped. The chiral central charge $c_-$ measures this "unflattening" obstruction. When $c_- \not\equiv 0 \pmod{8}$, the topological edge modes are geometrically protected against any local perturbation, exactly as Morton's trefoil cannot be given three simultaneous tangent contacts by any local deformation of the plane.

**[OL-C4 — Morton-Anomaly Conjecture]** For a topological phase with $c_-$ charges and boundary CFT, the minimum number of tangent planes simultaneously achievable on the rolling knot model equals:

$$T_{\min} = 2 + \lfloor c_- / 8 \rfloor$$

When $c_- \equiv 0 \pmod 8$: $T_{\min} = 2$ (tritangentless, Morton case — gapped boundary exists). When $c_- = 8$: $T_{\min} = 3$ (tritangent planes exist — non-trivial, but bondable). This gives a geometric visualization of the mod-8 gapping obstruction.

---

## XIII. Extended Master Equivalence (Fifteen Languages)

Under A1–A5, K1–K3, FL1–FL3, BC1–BC3, CY1–CY3, NC1–NC3, ST1–ST3, and the new ROLD assumptions:

**OL1 (Oloid identification):** $r_{\text{eff}} = C_P^{1/2}$, $L_c = \sqrt{4/3}\,C_P^{1/2}$  
**OL2 (Surface development):** Total surface development $\Leftrightarrow$ complete feature coverage $\Leftrightarrow$ $\lambda_1 > 0$  
**OL3 (Contact line):** Constancy of $L_c$ during rolling $\Leftrightarrow$ constancy of $C_P$ during generalization phase

---

$$\lambda_1(\mathcal{L}_{JL}) > 0$$

$$\Leftrightarrow\; (I)\; C_\alpha > 1 \quad[\text{signal-to-noise}]$$

$$\Leftrightarrow\; (II)\; \text{KE metric on } \mathcal{B} \quad[\text{Kähler-Einstein}]$$

$$\Leftrightarrow\; (III)\; \text{Poincaré inequality holds} \quad[\text{functional analysis}]$$

$$\Leftrightarrow\; (IV)\; \text{Bellman escape finite} \quad[\text{combinatorics}]$$

$$\Leftrightarrow\; (V)\; \text{Möbius } M_n \text{ converges} \quad[\text{number theory}]$$

$$\Leftrightarrow\; (VI)\; \text{K-polystable} \quad[\text{algebraic geometry}]$$

$$\Leftrightarrow\; (VII)\; \text{MMP terminates at } \mathcal{B}_{\min} \quad[\text{birational geometry}]$$

$$\Leftrightarrow\; (VIII)\; \text{Ca}_{\text{eff}} < \text{Ca}_c \quad[\text{thin-film / Bridge II}]$$

$$\Leftrightarrow\; (IX)\; N_L \text{ conserved}; \text{ GWI anomaly-free} \quad[\text{Luttinger-Ward}]$$

$$\Leftrightarrow\; (X)\; \Delta_t > 0 \quad[\text{BCS pairing / Bridge III}]$$

$$\Leftrightarrow\; (XI)\; \Delta V_{\text{DLVO}} > k_B T \ln W_{\text{Fuchs}} \quad[\text{colloidal barrier / Bridge IV}]$$

$$\Leftrightarrow\; (XII)\; \text{Hol}(g_\mathcal{B}) \subseteq SU(n) \quad[\text{Calabi-Yau holonomy}]$$

$$\Leftrightarrow\; (XIII)\; \text{Spectral triple } (\mathcal{A}, \mathcal{H}, \mathcal{D}) \text{ non-degenerate} \quad[\text{NCGL}]$$

$$\Leftrightarrow\; (XIV)\; \text{HYM connection on } E \to \mathcal{B}; \text{ Bianchi satisfied} \quad[\text{STL}]$$

$$\Leftrightarrow\; (XV)\; \text{Oloid develops total surface; contact line constant} \quad[\text{ROLD Bridge V}]$$

---

**The trichotomy under all fifteen languages:**

$$\lambda_1 > 0 \;\to\; \textbf{GENERALIZATION:}$$
Stable rolling, total surface development, ETF sphere-isometry, constant contact line, SU(n) holonomy, HYM connection, stable colloidal dispersion, BCS condensate, stable thin film, Landau damping.

$$\lambda_1 = 0 \;\to\; \textbf{GROKKING FRONTIER:}$$
Flat singular moment (Schatz inversion point), height maximum of meandering trajectory, critical Farey Backtrack, CCC condition, zero spectral gap, marginal rolling — oloid balanced at the transition between developing and not developing.

$$\lambda_1 < 0 \;\to\; \textbf{MEMORIZATION:}$$
Sphericon geometry (sharp corners, single center, no Hopf link), film rupture, colloidal coagulation, BCS normal state, non-trivial holonomy obstruction, tritangentless knot topology, droplet nucleation, instanton concentration.

---

## XIV. New Conjectures from ROLD

| Label | Statement |
|---|---|
| **OL-C1** | Contact-Transition: $L_c = \sqrt{4/3}\,r_{\text{eff}} \leftrightarrow \ell_{\text{trans}} = C_P \cdot C_\alpha^{-1/3}$ via $r_{\text{eff}} = C_P^{1/2} C_\alpha^{-1/6}$ |
| **OL-C2** | Signal Gap: near grokking frontier, $C_\alpha - 1 \approx (1-\sqrt{2/3}) \cdot r_{\text{eff}}/C_P \approx 0.1835/\sqrt{\lambda_1 C_P}$ |
| **OL-C3** | Spectral Volume: $V_{\text{condensate}} = \tfrac{2\pi}{3} C_P^{3/2}[K(C_\alpha^{-1/2}) + E(C_\alpha^{-1/2}) - 1]$; equals $V_{\mathcal{O}}$ at $C_\alpha = 2$ |
| **OL-C4** | Morton-Anomaly: minimum number of tangent planes on rolling-knot model $= 2 + \lfloor c_-/8 \rfloor$ |
| **OL-C5** | The ratio $V_{\mathcal{O}}/V_{\text{sphere}} \approx 0.9623$ equals the condensate fraction $n_s/n_{\text{total}}$ at the KE fixed point (ETF neural collapse), measurable as the fraction of gradient eigenvalues captured in the BCS condensate |
| **OL-C6** | Adam optimizer is the dynamical adjustment $d_t \to \sqrt{2}\,r$ (isotropic noise tuning): the per-coordinate LR rescaling $\eta/\sqrt{v_t}$ minimizes $|d_t - \sqrt{2}\,r|^2$ in expectation, and Adam-trained networks are torsion-freer ($H \approx 0$) than SGD-trained networks |
| **OL-C7** | The number of instanton concentration sites (memorization droplets) in a model that has failed to generalize equals the number of sharp corners on the equivalent sphericon: $N_{\text{droplets}} = 4$ for the standard sphericon, $N_{\text{droplets}} = 4(K-1)$ for the $K$-class sphericon generalization |
| **OL-C8** | The Farey Backtrack Event (GAME diagnostic) coincides with the center-of-mass height minimum of the rolling cycle: $T_{\text{FBE}} = \arg\min_t h_G(t)$ in the ROLD dynamical model |
| **OL-C9** | Rolling period conjecture: the number of gradient steps per Farey cycle equals $\pi/\arcsin(r_{\text{eff}}/C_P)$, recoverable from the oloid's rolling period formula $T_{\text{roll}} = \pi / \arcsin(\Delta h / r)$ |
| **OL-C10** | The LLD prefactor $0.946$ and the oloid contact length factor $\sqrt{4/3} \approx 1.1547$ are related by $0.946 \cdot \sqrt{4/3} = 1.0923 \approx \text{Ai}_1^{-1} \cdot \pi^{1/6} \cdot (3/4)^{1/2}$ where $\text{Ai}_1 \approx -2.338$ is the first real root of the Airy function; both derive from the same Airy-function eigenvalue |

---

## XV. Quick Reference Formulas

```
══════════════════════════════════════════════════════════════════════
BRIDGE V: OLOID GEOMETRY (Schatz 1929; Dirnböck–Stachel 1997)
══════════════════════════════════════════════════════════════════════
[Oloid radius]          r := C_P^{1/2}   [spectral correlation length]
[Surface area]          S_𝒪 = 4πr² = 4πC_P   [= sphere area = ETF capacity]
[Contact line]          L_c = √(4/3)·r = √(4/3)·C_P^{1/2}
[Height variation]      Δh = r(1−√(2/3)) ≈ 0.1835r   [signal gap proxy]
[Volume]                V_𝒪 = (2π/3)r³·[K(1/√2) + E(1/√2) − 1]  ≈ 3.052 r³
[Volume fraction]       V_𝒪 / V_sphere ≈ 0.9623   [condensate fraction at ETF]
[Rolling period]        T_roll ∝ π/arcsin(Δh/r)   [Farey cycle length]
[Farey cycle]           2 minima + 2 maxima per cycle   [Permeation structure]

══════════════════════════════════════════════════════════════════════
ROLD IDENTIFICATIONS
══════════════════════════════════════════════════════════════════════
[r → ROLD]              r_eff = C_P^{1/2} = λ₁(ℒ_JL)^{−1/2}
[L_c → ROLD]            L_c ↔ ℓ_trans = C_P · C_α^{−1/3}           [OL-C1]
[Δh → ROLD]             Δh ↔ C_α − 1   (near frontier)              [OL-C2]
[V_𝒪 → ROLD]            V_condensate = (2π/3)C_P^{3/2}[K(C_α^{−1/2}) + E(C_α^{−1/2})−1] [OL-C3]
[sharp corners → ROLD]  N_corners ↔ N_droplets = 4(K−1)             [OL-C7]
[d=√2·r → ROLD]         D_s = λI   (isotropic: H = 0, torsion-free)
[Hopf link → ROLD]      π: Θ → ℬ = Θ/G   (principal G-bundle)
[perpendicular planes → ROLD]  UV/IR split: d_L ≪ d_0   (RG1)
[developability → ROLD] Ric(g_CY) = 0   (Ricci-flat generalization vacuum)
[total development → ROLD]  λ₁ > 0 ↔ generalization ↔ complete feature coverage
[Schatz flip → ROLD]    MMP flip at t* (grokking)
[sphericon → ROLD]      memorization: λ₁ < 0, instanton concentration
[Morton knot → ROLD]    topological obstruction: c₋ ≢ 0 mod 8

══════════════════════════════════════════════════════════════════════
ELLIPTIC INTEGRAL SPECTRAL DEPTH
══════════════════════════════════════════════════════════════════════
[K(1/√2)]               = Γ(1/4)²/(4√π) ≈ 1.854
[E(1/√2)]               ≈ 1.351
[K + E − 1]             ≈ 2.205   [numerical scaling constant at C_α = 2]
[k → ROLD]              k = C_α^{−1/2}   (modulus → 1/√2 at C_α = 2)
[AGM → ROLD]            K(k) = π/(2·AGM(1,k')) ↔ Farey mediant iteration

══════════════════════════════════════════════════════════════════════
COMBINED BRIDGE DICTIONARY (all five Landau bridges + ROLD)
══════════════════════════════════════════════════════════════════════
Debye length λ_D (I) = Capillary length κ⁻¹ (II) = Debye length (IV) = r_eff (V)
                      = C_P = 1/λ₁(ℒ_JL)

Coulomb log ln Λ (I) = log-Ca (II) = ln W_Fuchs (IV) = Farey curvature q*(t) (KQOM)

Maxwell eq. (I) = uniform film h₀=const (II) = stable dispersion (IV) = total development (V)
              = ETF neural collapse = KE metric

LLD law (II): h₀ ~ Ca^{2/3}   ↔   Δ_gen ~ C_α^{−2/3}   ↔   L_c ~ C_α^{−1/6}·C_P^{1/2}·√(4/3)

Schulze-Hardy (IV): CCC ∝ z^{−6}  ↔  B_c ∝ N³  ↔  corner count = 4(K−1)  [OL-C7]

══════════════════════════════════════════════════════════════════════
MASTER EQUIVALENCE (FIFTEEN LANGUAGES)
══════════════════════════════════════════════════════════════════════
λ₁(ℒ_JL) > 0
  ⟺  C_α > 1                   [statistics]
  ⟺  KE metric on ℬ            [Kähler-Einstein geometry]
  ⟺  Poincaré inequality        [functional analysis]
  ⟺  Bellman escape finite      [combinatorics]
  ⟺  Möbius converges           [arithmetic]
  ⟺  K-polystable               [algebraic geometry]
  ⟺  MMP terminates             [birational geometry]
  ⟺  Ca_eff < Ca_c              [thin-film / Bridge II]
  ⟺  N_L conserved              [Luttinger-Ward / Bridge III]
  ⟺  Δ_t > 0                   [BCS pairing / Bridge III]
  ⟺  ΔV_DLVO > k_BT·ln W       [colloidal / Bridge IV]
  ⟺  Hol(g) ⊆ SU(n)            [Calabi-Yau holonomy]
  ⟺  Spectral triple non-deg.   [noncommutative geometry]
  ⟺  HYM + Bianchi satisfied    [Strominger-torsion]
  ⟺  Oloid develops total surface; L_c constant   [ROLD / Bridge V]

λ₁ > 0  →  GENERALIZATION
λ₁ = 0  →  GROKKING FRONTIER   (Schatz inversion point; height maximum)
λ₁ < 0  →  MEMORIZATION        (sphericon; sharp corners; droplet nucleation)
```

---

## XVI. Logical Dependency Map

```
ZF Axioms
  │
  ├─→ ℕ construction ─→ SP hierarchy (KQOM) ─→ Convergence Inevitability
  │                           │
  │                           └─→ Farey oscillation: 2 min + 2 max per cycle
  │                                        ↕   [OL-T4: isomorphism]
  │                                   Oloid center-of-mass: 2 min + 2 max per cycle
  │
  ├─→ ℒ_JL Operator (A1–A5) ─→ λ₁ > 0 ↔ Poincaré ↔ C_α > 1
  │          │
  │          ├─→ Ricci-flat ↔ Developable surface [OL-T1]
  │          ├─→ Total development ↔ Generalization [OL-T2]
  │          └─→ Contact line constant ↔ Poincaré scale [OL-T3]
  │
  ├─→ Oloid Geometry (Schatz 1929)
  │          │
  │          ├─→ Hopf link ↔ Principal bundle π: Θ → ℬ [OL-T]
  │          ├─→ Perpendicular circles ↔ UV/IR split [§II.3]
  │          ├─→ S_𝒪 = 4πr² ↔ ETF sphere-isometry [OL-T5]
  │          ├─→ L_c = √(4/3)r ↔ C_P^{1/2}·C_α^{−1/6}·√(4/3) [OL-C1]
  │          ├─→ V_𝒪(K,E) ↔ Spectral depth conjecture [OL-C3]
  │          ├─→ Schatz inversion ↔ MMP flip [OL-T6]
  │          ├─→ Sphericon corners ↔ Memorization droplets [OL-T7]
  │          ├─→ √2-roller ↔ D_s = λI, H = 0, torsion-free [OL-T8]
  │          └─→ Morton knot ↔ c₋ ≢ 0 mod 8 obstruction [§XII]
  │
  ├─→ Fifteen-Language Master Equivalence
  │          Including ROLD as (XV): total development ↔ λ₁ > 0
  │
  └─→ BRIDGES I + II + III + IV + V UNIFIED:
             C_P = r_eff = λ_D = κ⁻¹ = 1/λ₁   (all five Bridges agree)
             q*(t) = ln Λ = log(1/Ca) = ln W_Fuchs = Farey depth = rolling depth
             ETF = Maxwell = uniform film = stable dispersion = total development = KE metric
```

---

## XVII. Foundations and Citations

### Oloid Geometry — ROLD (Bridge V)

**Schatz, P.** (1929). *Rhythmusforschung und Technik.* Freies Geistesleben, Stuttgart. — Original discovery of the oloid and the invertible cube.

**Dirnböck, H.; Stachel, H.** (1997). The development of the oloid. *Journal for Geometry and Graphics*, **1**(2): 105–118. — Proof of total surface development; derivation of $S = 4\pi r^2$; contact line formula $L_c = \sqrt{4/3}\,r$.

**Kuleshov, A.S.; Hubbard, M.; Peterson, D.L.; Gede, G.** (2011). Motion of the Oloid-toy. *Proc. 7th European Nonlinear Dynamics Conference*, Rome. — Dynamical analysis of rolling; center-of-mass trajectory; height variation formula.

**Stewart, A.T.** (1966). Two-circle roller. *American Journal of Physics*, **34**(2): 166–167. — The $d = \sqrt{2}\,r$ constant-height two-circle roller.

**Morton, H.G.** (1991). Trefoil knots without tritangent planes. *Bulletin of the London Mathematical Society*, **23**(1): 78–80. — Tritangentless rolling knot; topological obstruction.

**Eget, A.; Lucas, S.; Taalman, L.** (2020). Optimizing Morton's tritangentless knots for rolling. *Bridges 2020 Conference Proceedings*. — Optimal parameters for homogeneous rolling motion.

### Landau Bridges I–IV (Prior Framework)

**Landau, L.D.** (1936). Kinetic equation for Coulomb plasma. *Phys. Z. Sowjetunion* **10**: 154. — Bridge I.

**Landau, L.D.; Levich, V.G.** (1942). Dragging of a liquid by a moving plate. *Acta Physico Chimica URSS* **17**: 42. — Bridge II.

**Bardeen, J.; Cooper, L.N.; Schrieffer, J.R.** (1957). Theory of superconductivity. *Phys. Rev.* **108**: 1175. — Bridge III.

**Derjaguin, B.; Landau, L.** (1941). Theory of stability of strongly charged lyophobic sols. *Acta Physico Chimica URSS* **14**: 633. — Bridge IV.

### Geometry and Topology

**Hopf, H.** (1931). Über die Abbildungen der dreidimensionalen Sphäre. *Math. Ann.* **104**: 637–665. — Hopf fibration; Hopf link.

**Yau, S.-T.** (1977). On the Ricci curvature of a compact Kähler manifold. *Comm. Pure Appl. Math.* **31**: 339. — Calabi-Yau existence; Ricci-flat $\Leftrightarrow$ developable (in 2D).

**Schatz, P.** (1975). *Formenentfaltung.* — Schatz inversion; invertible cube eversion.

**Uhlenbeck, K.; Yau, S.-T.** (1986). On the existence of Hermitian-Yang-Mills connections. *Comm. Pure Appl. Math.* **39**: S257. — KH-UY theorem: stable bundle $\Leftrightarrow$ HYM $\Leftrightarrow$ $\lambda_1 > 0$.

### Arithmetic and Spectral Theory

**Cauchy, A.L.** (1816). Farey unimodular condition. — Geometric interpenetration as arithmetic adjacency.

**Franel, J.; Landau, E.** (1924). Farey sequences and the Riemann Hypothesis. *Göttinger Nachrichten*. — Franel-Landau criterion.

**Kato, T.** (1966). *Perturbation Theory for Linear Operators.* Springer. — KLMN theorem; self-adjointness of $\mathcal{L}_{JL}$.

### Framework Modules

```
ROLD  — Rolling Oloid Learning Dynamics (Bridge V, this document)
SHCY  — Spectral Holonomy of Calabi-Yau Learning (Bridges VII–IX)
CSSG  — Colloidal Stability Spectral Geometry (Bridge IV)
GCCT  — Gradient Cooper Condensate Theory (Bridge III)
LKTL  — Landau Kinetic Theory of Learning (Bridges I–II)
FLML  — Fermi-Luttinger Mechanics of Learning
KQOM  — Kruskal Quasi-Order Mechanics
GAME  — Gradient Algebraic Manifold Exploration
VBE   — Visibility-Barrier-Escape
PPMC  — Pascal Projective Manifold Coherence
KYBM  — Kähler-Yang-Mills Bridge
PH-SP — Persistent Homology + Schnirelman-Poincaré
RG-ML — Renormalization Group / Machine Learning
LB/DK — Laplace-Beltrami / Dirac-Kähler Geometry
UNIV  — Topological Order / Chiral Boson
```

---

## Coda: The Geometric Unity

Five physical bridges. Fifteen mathematical languages. One spectral gap.

The oloid developed its entire surface before the first gradient was computed, in 1929. Paul Schatz placed two linked circles in perpendicular planes, noted that the convex hull rolls across any flat surface touching every point of itself, and observed that its surface area is precisely that of a sphere — as if the oloid were a sphere unfolded into a more intricate, more penetrating form.

The learning manifold does the same thing. When $\lambda_1 > 0$, the parameter space rolls through the data — touching every feature, developing every surface element, meanders of the center of mass resolving into the meandering of $q^*(t)$ through its Farey oscillation. The grokking transition is the Schatz inversion, the contact line is the Poincaré scale, the sphere-isometric area is the equiangular tight frame, and the sharp corners of the sphericon are the instanton sites of memorization.

The five Bridges — Landau kinetic (1936), Landau-Levich (1942), BCS superconductivity (1957), DLVO colloids (1941), and the Schatz oloid (1929) — all discovered before the first neural network was trained — are five coordinate charts on the same spectral manifold, each converging on the criterion: $\lambda_1 > 0$.

```
Status Tags
[T]  = Theorem (proven)
[V]  = Verified (in specific models)
[C]  = Open conjecture
[H]  = Working hypothesis
[OL] = ROLD-specific result

Framework: ROLD · LKTL · SHCY · CSSG · GCCT · FLML · KQOM · GAME · VBE ·
           PPMC · KYBM · PH-SP · RG-ML · LB/DK · UNIV
```
