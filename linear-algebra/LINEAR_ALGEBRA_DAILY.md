# Linear Algebra — Daily 30-Minute Roadmap

**Duration**: 24 weeks (Months 0-6 of the main roadmap)  
**Daily time**: 30 minutes, no exceptions  
**Resources**: 3Blue1Brown (Essence of Linear Algebra series) + Gilbert Strang (MIT OCW) + NumPy experiments  
**Principle**: Understand *why*, not just *what*. Every concept connects to ML.

---

## How to use this

Each week has 5 daily slots (take weekends off or catch up). A day looks like:

| Minutes | Activity |
|---|---|
| 5 | Review previous day's key insight (write it from memory) |
| 15 | New material: watch video / read / derive |
| 10 | **Implement in NumPy** — always. Code the concept. |

The NumPy step is non-negotiable. Linear algebra without coding it is memorization, not understanding.

---

## Month 1: Vectors & Vector Spaces

### Week 1 — Vector Fundamentals

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | What is a vector? | 3B1B: "Vectors" (ch 1) | `np.array([1,2,3])` — create, index, slice vectors |
| 2 | Scaling & addition | 3B1B: "Linear combinations" (ch 2) | `2*a + 3*b` — linear combination of 2 vectors |
| 3 | The span of vectors | 3B1B: "Span" (ch 2 cont) | Generate random combos, visualize span as scatter |
| 4 | Parametric lines | Strang 1.1 | `p + t*v` — trace a line through 2 points |
| 5 | Quick review + mini-exercise | Derive linear combo that reaches a target | Solve visually with `np.linalg.solve` if 2D |

**Week 1 validation**: Given a target vector, find coefficients that combine two basis vectors to reach it.

### Week 2 — Dot Products & Norms

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Dot product definition | 3B1B: "Dot product" (ch 5) | `np.dot(a, b)` — compute manually then verify |
| 2 | Geometric meaning (projection) | 3B1B: "Dot product geometry" | Project `a` onto `b`: `(a·b)/(b·b) * b` |
| 3 | Norm (length) & unit vectors | Strang 1.2 | `np.linalg.norm(v)` — normalize a vector |
| 4 | Cauchy-Schwarz inequality | Proof sketch | Verify: `\|a·b\| ≤ \|a\|\|b\|` on random vectors |
| 5 | Cosine similarity | Intuition: angle between vectors | Implement `cos_sim(a,b)` — test on similar vs orthogonal |

**Week 2 validation**: Write a function that computes cosine similarity between 5 document vectors. Explain which are most similar.

### Week 3 — Orthogonality

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Orthogonal vectors | 3B1B: when dot = 0 | Find a vector orthogonal to `[1,2,3]` |
| 2 | Orthogonal projections onto lines | 3B1B: "Projections" (ch 9) | Project `v` onto line through `u` |
| 3 | Gram-Schmidt intuition | 3B1B visual approach | Orthogonalize 2 vectors step by step |
| 4 | Gram-Schmidt in NumPy | Strang 3.4 | Implement GS for 3 vectors |
| 5 | Review: orthogonal decomposition | Break a vector into parallel + perpendicular | `v_parallel + v_perp` — verify they're orthogonal |

**Week 3 validation**: Take 3 random 5D vectors, orthogonalize them, verify all pairs have dot product ~ 0.

### Week 4 — Basis & Dimension

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Linear independence | 3B1B: "Basis" (ch 4) | Check independence of 3 vectors using `np.linalg.matrix_rank` |
| 2 | Basis of a vector space | Strang 2.3 | Find a basis for the column space of a 4×3 matrix |
| 3 | Dimension | Strang 2.3 | Rank = dimension of column space — verify on random matrices |
| 4 | Coordinate systems | 3B1B: "Change of basis" (ch 11) | Convert `v` from standard basis to custom basis |
| 5 | ML connection: feature vectors | Each data point is a vector in feature space | Take 3 rows from Titanic, treat as vectors, compute pairwise distances |

**Month 1 validation**: Take the Iris dataset (4 features). Treat each row as a vector. Compute pairwise cosine similarity matrix. Explain what the values mean.

---

## Month 2: Matrices & Linear Transformations

### Week 5 — Matrix Operations

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Matrix creation & indexing | Refresher | `np.array`, reshape, slicing rows/columns |
| 2 | Matrix addition & scaling | Strang 1.3 | `A+B`, `2*A` — verify dimensions |
| 3 | Matrix multiplication (concept) | 3B1B: "Matrix multiplication" (ch 7) | Compute 2×2 × 2×2 by hand, verify with `A @ B` |
| 4 | Matrix multiplication (why rows × cols) | Strang 1.4 | Derive: (m×n)(n×p) = m×p. Try mismatched shapes, catch error |
| 5 | Transpose | 3B1B: "Transpose" (ch 12) | `A.T`, `np.transpose(A, axes=(1,0,2))` for 3D |

### Week 6 — Linear Transformations

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Transformations as functions | 3B1B: "Linear transformations" (ch 3) | Apply `A @ v` to visualize how a vector moves |
| 2 | Rotation matrix | Derive 2D rotation by θ | Implement `rotate(theta)` — apply to grid points |
| 3 | Shear & scaling matrices | 3B1B: visual intuition | Build scale(2,3), shear(1) — apply to unit square |
| 4 | Composition of transformations | 3B1B: "Composition" (ch 8) | `R @ S @ v` — rotate then shear vs shear then rotate (order matters!) |
| 5 | ML connection: weight matrices | A neural network layer = transformation | Random 4×3 matrix transforms 3D input to 4D hidden state |

**Week 6 validation**: Take the unit square vertices `[[0,0],[1,0],[1,1],[0,1]]`. Apply rotation by 45° then shear. Plot both original and transformed shapes.

### Week 7 — Inverse & Identity

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Identity matrix | `I` as the "do nothing" transformation | `np.eye(5)` — verify `I @ A = A` |
| 2 | Inverse — undoing a transformation | 3B1B: "Inverse" (ch 6) | `np.linalg.inv(A)` — verify `A @ A⁻¹ = I` |
| 3 | When inverse doesn't exist | Determinant = 0, rank deficient | Try `np.linalg.inv([[1,2],[2,4]])` — catch error |
| 4 | Solving Ax = b | 3B1B: "Solving systems" | `x = np.linalg.solve(A, b)` — verify `A@x = b` |
| 5 | ML connection: normal equation | Linear regression closed form: `θ = (XᵀX)⁻¹Xᵀy` | Implement linear regression with normal equation on synthetic data |

**Week 7 validation**: Generate 50 points `y = 2x + 1 + noise`. Solve for slope and intercept using the normal equation. Compare to sklearn's LinearRegression.

### Week 8 — Change of Basis

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | What change of basis means | 3B1B: "Change of basis" (ch 11) rewatch | Express a point in two different bases |
| 2 | Computing change-of-basis matrix | Strang 2.6 | Build `C` = matrix whose columns are new basis vectors |
| 3 | Converting between bases | `v_new = C⁻¹ @ v_old` | Convert coordinates, verify roundtrip |
| 4 | Similarity transformations | `A' = C⁻¹ @ A @ C` | Transform a matrix to a new basis |
| 5 | ML connection: PCA intuition | PCA = finding the "best" basis for your data | Plot data in original vs PCA-rotated coordinates |

**Month 2 validation**: Create 100 2D data points correlated along `y=x`. Find the covariance matrix. Show that its eigenvectors form the "natural" basis for the data (PCA preview).

---

## Month 3: Solving Linear Systems

### Week 9 — Gaussian Elimination

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Row operations (swap, scale, add) | Strang 2.1 | Implement each as matrix multiplication |
| 2 | Forward elimination (REF) | Strang 2.2 | Write a simple elimination on 3×3 system (no pivoting) |
| 3 | Back substitution | Strang 2.2 | Solve upper triangular system bottom-to-top |
| 4 | Row echelon vs reduced row echelon | Strang 2.2 | Compute RREF for a 4×3 matrix |
| 5 | Pivoting (stability) | Why you should swap rows | Try eliminating without pivot on a near-singular matrix |

### Week 10 — LU Decomposition

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | LU intuition (elimination = L @ U) | 3B1B: "LU decomposition" | `P, L, U = scipy.linalg.lu(A)` |
| 2 | Solving with LU (2 steps) | Forward then backward substitution | Use L and U to solve Ax = b in 2 steps |
| 3 | Computational complexity | O(n³) vs alternatives | Time `np.linalg.solve` for n=10, 100, 1000 |
| 4 | Cholesky decomposition (for symmetric PD) | Strang 2.7 | `L = np.linalg.cholesky(A)` — verify A = L @ L.T |
| 5 | ML connection: Cholesky for sampling | Multivariate normal sampling | Generate correlated random samples using Cholesky |

### Week 11 — The Four Fundamental Subspaces

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Column space (range) | Strang 3.1 | Find basis of column space via SVD |
| 2 | Nullspace (kernel) | Strang 3.2 | `scipy.linalg.null_space(A)` — verify A @ n = 0 |
| 3 | Row space | Strang 3.3 | Row space = column space of A.T |
| 4 | Left nullspace | Strang 3.3 | The "other" nullspace |
| 5 | Rank-nullity theorem | dim(col) + dim(null) = n | Verify on random 4×6 matrix |

**Week 11 validation**: For a random 3×5 matrix, compute all four subspaces. Verify the dimension relationships.

### Week 12 — Least Squares

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Overdetermined systems (more equations than unknowns) | Strang 4.1 | Try solving 10 equations, 3 unknowns |
| 2 | Least squares solution via normal equations | `x = (AᵀA)⁻¹Aᵀb` | Implement on noisy linear data |
| 3 | Orthogonal projections again | Projection matrix `P = A(AᵀA)⁻¹Aᵀ` | Show Pb is in col(A), (I-P)b is orthogonal |
| 4 | Least squares via QR (better numerically) | Strang 4.2 | `Q, R = np.linalg.qr(A)` — solve `R x = Qᵀ b` |
| 5 | ML connection: linear regression = least squares | This IS the math behind linear regression | Compare normal equation vs QR vs sklearn |

**Month 3 validation**: Generate `y = 3x₁ - 2x₂ + 1.5 + noise` (20 samples). Solve via normal equations. Report coefficients. Compare to sklearn.

---

## Month 4: Determinants & Eigenvalues

### Week 13 — Determinants

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | What determinant means (area scaling) | 3B1B: "Determinant" (ch 4) | Compute det of 2×2, verify area scaling on unit square |
| 2 | Computing determinants | Strang 5.1 | `np.linalg.det(A)` for 3×3, 4×4 |
| 3 | Properties (product, transpose, inverse) | Strang 5.1 | Verify: det(AB) = det(A)·det(B), det(A⁻¹) = 1/det(A) |
| 4 | Cramer's rule (for small systems) | Strang 5.3 | Solve 2×2 system with Cramer's rule, compare to `solve` |
| 5 | Determinant as volume in n-dim | Intuition | Compute det of a 5D matrix — what would this "volume" mean? |

### Week 14 — Eigenvalues & Eigenvectors

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | What are eigenvalues? (Av = λv) | 3B1B: "Eigenvectors" (ch 10) | `values, vectors = np.linalg.eig(A)` — verify Av = λv |
| 2 | Characteristic polynomial | det(A - λI) = 0 | Compute characteristic polynomial for 2×2 (symbolic if possible) |
| 3 | Eigenspaces & multiplicity | Strang 6.1 | For a repeated eigenvalue, find the full eigenspace |
| 4 | Complex eigenvalues | What they mean geometrically | `np.linalg.eig(rotation_matrix)` — notice complex pairs |
| 5 | ML connection: covariance eigenvectors | PCA = eigenvectors of covariance matrix | Compute eigenvectors of `np.cov(data.T)` — plot them on data |

### Week 15 — Diagonalization

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Diagonalization: A = PDP⁻¹ | Strang 6.2 | Factor a matrix: `P @ D @ np.linalg.inv(P)` |
| 2 | When is a matrix diagonalizable? | Strang 6.2 | Test a defective matrix `[[1,1],[0,1]]` |
| 3 | Computing powers with diagonalization | Aᵏ = PDᵏP⁻¹ | Compute A⁵ via diagonalization vs direct multiplication |
| 4 | Matrix exponential | exp(A) = P·exp(D)·P⁻¹ | `scipy.linalg.expm(A)` — verify definition for small matrix |
| 5 | ML connection: Markov chains & PageRank | Stationary distribution = eigenvector | Simulate a simple Markov chain, find steady state via eig |

### Week 16 — PCA & Applications

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | PCA: the full algorithm | Step-by-step: center → cov → eig → sort → project | Implement PCA from scratch on Iris |
| 2 | Explained variance ratio | `λᵢ / Σλⱼ` | Plot cumulative explained variance, choose k |
| 3 | PCA for visualization | Project 4D Iris to 2D | Plot Iris in 2D PCA space — can you see clusters? |
| 4 | PCA for dimensionality reduction | Keep 95% variance | Reconstruct from 2 components, measure error |
| 5 | PCA vs t-SNE vs UMAP (intuition) | When to use each | Compare PCA (linear) to t-SNE (nonlinear) on same data |

**Month 4 validation**: Implement PCA from scratch on the Wine dataset (13 features). Reduce to 2D. Plot. Compare to sklearn.decomposition.PCA. Match exactly.

---

## Month 5: Matrix Decompositions

### Week 17 — QR Decomposition

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Gram-Schmidt → QR | Review Gram-Schmidt, see it produces Q and R | `Q, R = np.linalg.qr(A)` |
| 2 | Orthogonal matrices (QᵀQ = I) | 3B1B: why orthonormal is special | Verify Q is orthogonal: `Q.T @ Q ≈ I` |
| 3 | QR for least squares | Numerically stable alternative to normal eq | Compare QR-solve vs normal eq vs sklearn |
| 4 | QR for eigenvalues (QR algorithm intuition) | Strang 6.6 | Iterate: `A = R @ Q` (reassemble from QR) — watch it become diagonal |
| 5 | ML connection: QR in linear regression | Production regression uses QR, not normal eq | Benchmark QR vs normal eq for n=100, 1000, 10000 |

### Week 18 — Singular Value Decomposition (SVD)

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | What is SVD? (A = UΣVᵀ) | 3B1B: "SVD" (ch 16) — best video in the series | `U, S, Vt = np.linalg.svd(A)` |
| 2 | U, Σ, Vᵀ — what each part means | U = left singular vectors, V = right, Σ = singular values | Verify: `U @ np.diag(S) @ Vt ≈ A` |
| 3 | SVD = change of basis × scaling × change of basis | Geometric interpretation | Apply SVD step by step to a 2×2 matrix, visualize |
| 4 | Low-rank approximation (truncated SVD) | Keep top k singular values | Approximate A using 1, 2, ..., k components |
| 5 | Image compression with SVD | Keep k components, reconstruct image | Apply to grayscale image — show quality vs k (1, 5, 20, 100) |

### Week 19 — SVD in Machine Learning

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | SVD for PCA | PCA = SVD on centered data | Show: SVD of centered data gives PCA eigenvectors |
| 2 | SVD for collaborative filtering (matrix completion) | Netflix prize, recommendation systems | Build a simple recommender with truncated SVD on a user-item matrix |
| 3 | Pseudoinverse via SVD | A⁺ = VΣ⁺Uᵀ | `np.linalg.pinv(A)` — verify A⁺A ≈ I |
| 4 | Condition number & numerical stability | `κ = σ_max / σ_min` | `np.linalg.cond(A)` — test on well-conditioned vs ill-conditioned |
| 5 | ML connection: SVD everywhere | LSA (NLP), collaborative filtering, PCA | Implement LSA on a small document-term matrix |

**Week 19 validation**: Build a movie recommender: user-item rating matrix → truncated SVD → predict missing ratings. RMSE < 1.0 on test.

### Week 20 — Quadratic Forms & Positive Definiteness

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Quadratic forms (xᵀAx) | Strang 7.1 | Compute xᵀAx for various x, see sign |
| 2 | Positive definite matrices | All eigenvalues > 0 | Check: `np.all(np.linalg.eigvals(A) > 0)` |
| 3 | Testing positive definiteness | Leading principal minors | Write a check using determinants of submatrices |
| 4 | Covariance matrices are PSD | Any covariance matrix is positive semidefinite | Generate data, compute cov, check eigenvalues ≥ 0 |
| 5 | ML connection: loss landscapes | The Hessian in optimization | For a simple quadratic loss, compute Hessian, check definiteness |

**Month 5 validation**: Given 3 covariance matrices (one valid, two not), determine which is PSD using eigenvalues. Explain why covariance matrices must be PSD.

---

## Month 6: ML Applications & Review

### Week 21 — Matrix Calculus

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Derivative of a vector function | ∂y/∂x when y = f(x) | Numerical vs analytical gradient for simple functions |
| 2 | Gradient of xᵀAx | ∇(xᵀAx) = 2Ax (if A symmetric) | Verify numerically with finite differences |
| 3 | Derivative of Ax + b | ∇(Ax + b) = Aᵀ | Verify on random matrices |
| 4 | Chain rule for matrices | ∂L/∂W = (∂L/∂y)(∂y/∂W) | Manual backprop for a single linear layer |
| 5 | Jacobian & Hessian | First & second derivative matrices | `scipy.optimize.approx_fprime` vs analytical |

### Week 22 — Linear Algebra in Neural Networks

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Forward pass = matrix multiply + activation | Layer: h = σ(Wx + b) | Implement forward pass for 3-layer network |
| 2 | Backprop = chain rule on matrices | Each layer applies chain rule | Manual gradients for 2-layer network |
| 3 | Weight matrices as transformations | Each layer re-represents the data | Visualize hidden layer activations as transformed input |
| 4 | Embeddings as linear algebra | Word embeddings ≈ vector space | Analogy: king - man + woman ≈ queen using GloVe vectors |
| 5 | Attention mechanism (intuition) | Query × Key = relevance weights | Scaled dot-product attention: `softmax(Q @ Kᵀ / √d) @ V` |

### Week 23 — Linear Algebra in NLP & Graphs

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Document-term matrix | Bag of words as a matrix | Create DT matrix from 10 documents |
| 2 | TF-IDF = weighting the DT matrix | `tf * log(N/df)` | Implement TF-IDF from scratch |
| 3 | LSA (SVD on DT matrix) | SVD on TF-IDF → latent concepts | Reduce to 10 topics, interpret dimensions |
| 4 | Graph as adjacency matrix | Graph = sparse matrix | Build adjacency matrix, compute degree matrix |
| 5 | Spectral clustering (intuition) | Eigenvectors of Laplacian reveal clusters | Apply spectral clustering to toy data (two moons) |

### Week 24 — Grand Review & Gradient Descent Validation

| Day | Topic | 15-min Material | 10-min NumPy |
|---|---|---|---|
| 1 | Linear algebra mind map | Draw connections between all topics | Write a one-page summary from memory |
| 2 | Gradient descent — full implementation | Implement from scratch | `gd(X, y, lr=0.01, epochs=1000)` — linear regression via GD |
| 3 | Compare GD to normal equation | GD = iterative, NE = closed form | Both produce same θ (approximately). Compare time. |
| 4 | Mini-batch GD | SGD vs mini-batch vs batch | Implement all three, compare convergence paths |
| 5 | **FINAL VALIDATION** | Implement gradient descent from scratch in NumPy | See below |

---

## Final Validation (Month 6, Week 24, Day 5)

Implement gradient descent for linear regression from scratch:

```python
import numpy as np

# Generate synthetic data
np.random.seed(42)
X = 2 * np.random.rand(100, 1)
y = 4 + 3 * X + np.random.randn(100, 1)

# Add bias term
X_b = np.c_[np.ones((100, 1)), X]

# Gradient descent
def gradient_descent(X, y, lr=0.1, epochs=1000):
    theta = np.random.randn(X.shape[1], 1)
    for i in range(epochs):
        # Predict
        y_pred = X @ theta
        # Compute gradient (you should know why this formula)
        gradient = (2 / len(X)) * X.T @ (y_pred - y)
        # Update
        theta -= lr * gradient
    return theta

theta = gradient_descent(X_b, y)
print(f"Intercept: {theta[0][0]:.2f}, Slope: {theta[1][0]:.2f}")
# Should be approximately: Intercept: 4.0, Slope: 3.0
```

**If you can explain every line of `gradient = (2/m) * X.T @ (y_pred - y)`** — why the transpose, why the `@`, why `2/m`, why that formula at all — you have mastered the linear algebra you need for ML.

---

## Summary: Your daily habit

| Time | Activity |
|---|---|
| 08:00-08:05 | Write yesterday's key insight from memory |
| 08:05-08:20 | New topic (3B1B video / Strang reading / derive) |
| 08:20-08:30 | Implement it in NumPy |

**Stick to 30 minutes. Don't go over. Consistency beats intensity.**

---

## Resource Links by Week

### Primary Resources (used throughout)

| Resource | Link |
|---|---|
| **3Blue1Brown — Essence of Linear Algebra** (full playlist, 16 videos) | https://youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab |
| **3Blue1Brown — Essence of Calculus** (for cross-reference when needed) | https://youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr |
| **3Blue1Brown — Neural Networks** (for motivation, Week 22) | https://youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi |
| **MIT OCW 18.06 — Gilbert Strang** (full course) | https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/ |
| **Strang's textbook — Introduction to Linear Algebra** (companion to MIT course) | https://math.mit.edu/~gs/linearalgebra/ |
| **Jon Krohn — Linear Algebra for ML** (ML-focused alternative to Strang) | https://youtube.com/playlist?list=PLRDl2inPrWQW1QSWhBU0ki-jq_uElkh2a |

### Week-by-Week 3B1B Chapters

| Week | 3B1B Chapter(s) | Link |
|---|---|---|
| 1 | Ch 1-4: Vectors, Linear combinations, Span, Basis | https://youtu.be/fNk_zzaMoSs (ch 1-2) / https://youtu.be/k7RM-ot2NWY (ch 3-4) |
| 2 | Ch 5: Dot products | https://youtu.be/LyGKycYT3v0 |
| 3 | Ch 9: Projections | https://youtu.be/dgko31HcVnQ (Gram-Schmidt follow-up) |
| 4 | Ch 4, 11: Basis, Change of basis | https://youtu.be/k7RM-ot2NWY / https://youtu.be/P2LTAUO1TdA |
| 5 | Ch 7: Matrix multiplication | https://youtu.be/XkY2DOUCWMU |
| 6 | Ch 3, 8: Linear transformations, Composition | https://youtu.be/kYB8IZa5AuE / https://youtu.be/OAh573i_lfI |
| 7 | Ch 6: Inverse, Determinant intro | https://youtu.be/uQhTuRlWMxw |
| 8 | Ch 11: Change of basis (rewatch) | Same as Week 4 |
| 9-10 | No 3B1B (use Strang MIT lectures) | See Strang links below |
| 11-12 | No 3B1B (use Strang) | See below |
| 13 | Ch 4: Determinant | https://youtu.be/Ip3X9LOh2dk |
| 14 | Ch 10: Eigenvectors | https://youtu.be/PFDu9oVAE-g |
| 15-16 | Review previous chapters | — |
| 17-18 | Ch 16: SVD | https://youtu.be/gXbThCXjZFM |
| 19-20 | No 3B1B (use Strang) | See below |
| 21-22 | Neural Networks playlist | https://youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi |
| 23 | No 3B1B (use Strang) | — |
| 24 | Review entire series | Re-watch any unclear chapters |

### Key MIT Strang Lectures by Topic

| Topic | Lecture | Link |
|---|---|---|
| Elimination & LU | Lec 4-5 | https://youtu.be/FX4C-JpTFgY / https://youtu.be/qhOjf5JdSI4 |
| Four subspaces | Lec 10 | https://youtu.be/nHlE7EgJFds |
| Least squares & projections | Lec 14-16 | https://youtu.be/osh80YCg_GM |
| Gram-Schmidt & QR | Lec 17 | https://youtu.be/0MtwqhIwdrI |
| Determinants | Lec 18-20 | https://youtu.be/srxexLishgY |
| Eigenvalues | Lec 21-24 | https://youtu.be/cdZnhQjJu4I |
| SVD | Lec 29-30 | https://youtu.be/Nx0lRBaXoz4 |
| Linear transformations | Lec 30 | https://youtu.be/hSRIMJDh0oQ |

### NumPy Reference Docs

| Topic | Link |
|---|---|
| NumPy quickstart (official) | https://numpy.org/doc/stable/user/quickstart.html |
| Linear algebra in NumPy | https://numpy.org/doc/stable/reference/routines.linalg.html |
| Random sampling | https://numpy.org/doc/stable/reference/random/index.html |

### Books (if you prefer reading over video)

| Book | Why |
|---|---|
| **Strang — Introduction to Linear Algebra** (5th ed) | The textbook that matches the MIT course. Used by MIT, Berkeley, Stanford. |
| **Huber — Linear Algebra for Data Science** (free PDF) | Short, focused on ML applications. Less theory, more code. |
| **Mathematics for Machine Learning** (Deisenroth, Faisal, Ong) | Covers linear algebra + calculus + probability in one book. Half the book is linear algebra with ML examples. Free PDF available. |

### Cheat Sheets & Quick References

| Resource | Link |
|---|---|
| Linear algebra cheat sheet (6 pages) | https://stanford.io/3EAjGpZ (CS229 LA review) |
| NumPy cheat sheet | https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Numpy_Python_Cheat_Sheet.pdf |
| Matrix calculus cheat sheet | https://gist.github.com/Revilossor/9682b8998e6275be9099c79eb5e3d52b |

### YouTube Channels for When You're Stuck

| Channel | When to use |
|---|---|
| **3Blue1Brown** | Need visual intuition |
| **StatQuest** | Need stats/ML connection |
| **MIT OpenCourseWare** | Need rigorous depth |
| **The Organic Chemistry Tutor** (yes, really) | Need basic step-by-step algebra/trig review — surprisingly good for linear algebra fundamentals |
| **Welch Labs** | Need ML-focused linear algebra examples
