# Handoff — Linear Algebra for ML Notebooks

## Structure
```
Linear Algebra/
├── Week_1/         # Vector Operations (5 notebooks, done)
└── Week_2/         # Dot Products & Norms (5 notebooks, done)
```

## Notebook Format (follow this exactly)

Each notebook is a 30-min session split into:

| Section | Duration | Content |
|---------|----------|---------|
| Review | 5 min | 3 review questions from previous day |
| Intuition | ~15 min | Intuition first → math → visual diagrams |
| NumPy | ~10 min | Code cells with `np.*` — "think before you run" prompts |
| ML Connection | inline | How this maps to ML (attention, embeddings, regularization, etc.) |
| Exercises | end | 1-2 exercises with code cells |
| Summary table | end | Table of concepts, ✅, next day preview |
| YouTube ref | end | Relevant 3B1B / Strang chapter |

### Style Rules
- Conversational, ChatGPT-style teaching — intuition before formulas
- MCQ quick checks with answer hidden behind `> *(...)*`
- ASCII diagrams for geometric intuition
- Abuse `np.random.seed()` for reproducibility
- `np.clip(..., -1.0, 1.0)` for numerical safety on cos
- Progress tracker at end of each notebook
- Filename pattern: `Day<N>_<Topic>.ipynb`

### Reference Notebooks (canonical format)
- `Week_1/Day1_Vectors.ipynb` through `Day5_Review_MiniExercise.ipynb`
- `Week_2/Day1_DotProduct.ipynb` through `Day5_CosineSimilarity.ipynb`

## What's Done

### Week 1 — Vectors (5/5)
| Day | File | Topic |
|-----|------|-------|
| 1 | `Day1_Vectors.ipynb` | Vectors, coordinates, NumPy arrays |
| 2 | `Day2_ScalarMultiplication.ipynb` | Scaling vectors, effect on direction |
| 3 | `Day3_VectorAddition.ipynb` | Parallelogram rule, component-wise |
| 4 | `Day4_LinearCombinations.ipynb` | Span, linear combinations |
| 5 | `Day5_Review_MiniExercise.ipynb` | Mini project: polygon transform |

### Week 2 — Dot Products & Norms (5/5)
| Day | File | Topic |
|-----|------|-------|
| 1 | `Day1_DotProduct.ipynb` | Algebraic & geometric definition |
| 2 | `Day2_Projection.ipynb` | Projection, residual, orthogonality |
| 3 | `Day3_Norm_UnitVectors.ipynb` | Length, normalization, scaling pattern |
| 4 | `Day4_CauchySchwarz.ipynb` | Cauchy-Schwarz inequality, cos(θ) |
| 5 | `Day5_CosineSimilarity.ipynb` | Cosine similarity, word embeddings, search |

## Removed
- `Week_3` through `Week_24` — all deleted (were empty folders)
- `Month_2_Matrices` through `Month_6_ML_Applications` — deleted
- All renamed to plain `Week_1` / `Week_2`

## Roadmap Reference (24-week plan)

The full roadmap lives at the course root. Remaining weeks if continuing:
- **Week 3**: Linear Transformations
- **Week 4**: Matrix Multiplication
- **Week 5**: Systems of Equations
- **Week 6**: Inverse & Elimination
- **Week 7+**: Determinants, Eigen, Decompositions, SVD, PCA, etc.

## Other Project Context
- Spring Boot DTO project: `/media/ivwananji-silungwe/DEVELOPMENT/PROGRAMMING/BACKEND/SPRINGBOOT/Week-1/07-data-transfer-object/notes-api`
  - `NoteResponse` now only exposes `title` and `content` (no `id`)

## Known Issues
- Background agents for batch-creating notebooks failed (model routing). All notebooks created via direct `write`.
- No LSP for Java — verify Spring Boot changes with `mvn compile`.
