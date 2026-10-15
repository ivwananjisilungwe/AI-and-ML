# ML Engineering Roadmap (Restructured)

## Changes from original

| Original | Restructured | Why |
|---|---|---|
| 12 months | **24 months** | Self-study + work = marathon, not sprint |
| Django DRF for models | **FastAPI** | Industry standard for ML serving |
| Cloud only at MLOps phase | **Cloud from Month 6** | Earlier ≠ harder, looks better on CV |
| Deep NLP specialization | **Breadth: 1 tabular + 1 CV + 1 NLP** | Entry-level flexibility > niche |
| Math as 4-week cram | **30 min daily, spread across all 24 months** | Real retention, not test-passing |

---

## Math Thread (runs alongside everything)

**30 minutes daily. No exceptions.** Do this *before* the main study block.

| Period | Topic | Resource |
|---|---|---|
| Months 0-6 | Linear algebra (vectors, matrices, eigendecomposition, SVD) | 3Blue1Brown + Gilbert Strang |
| Months 6-12 | Calculus (derivatives, gradients, chain rule, backprop) | Khan Academy + matrix calculus |
| Months 12-18 | Statistics (distributions, hypothesis testing, Bayesian thinking) | StatQuest + Think Stats |
| Months 18-24 | Probability + Information theory (entropy, KL divergence) | Cover & Thomas (ch 1-5) |

**Validation**: Month 6 — implement gradient descent from scratch in NumPy.
**Validation**: Month 12 — derive backpropagation for a 3-layer network on paper.
**Validation**: Month 18 — explain p-values and confidence intervals to a non-technical person.

---

## Phase 0: Foundation (Months 0-5)

### Month 0-1: Pandas + Visualization

| Week | Topic | Deliverable |
|---|---|---|
| 1 | Pandas: DataFrames, indexing, groupby, merge | Notebook with join/merge examples |
| 2 | Pandas: pivot tables, multi-index, datetime | Time series aggregation notebook |
| 3 | Matplotlib: line, scatter, bar, hist, subplots | Custom-styled figure gallery |
| 4 | Seaborn: heatmaps, pairplots, box/violin plots | Correlation analysis on a real dataset |

**Validation**: Load Titanic dataset, clean missing values, produce 5 publication-quality visualizations.

### Month 2-3: Scikit-learn Fundamentals

| Week | Topic | Deliverable |
|---|---|---|
| 1 | Regression (linear, ridge, lasso) + train/test split + RMSE | Predict housing prices |
| 2 | Classification (logistic regression, decision tree, RF) + metrics | Classify with 85%+ accuracy |
| 3 | Cross-validation, GridSearchCV, pipelines | Tuned pipeline with CV |
| 4 | Clustering (KMeans, DBSCAN) + silhouette score | Customer segmentation |

**Validation**: Train a model on a real dataset, achieve 85%+ accuracy, log all experiments.

### Month 4: Feature Engineering + Experiment Tracking

| Week | Topic | Deliverable |
|---|---|---|
| 1 | Missing data, categorical encoding, scaling | Feature-engineered dataset |
| 2 | Feature selection (RF importance, mutual info), PCA | Dimensionality reduction notebook |
| 3 | Creating features from dates, text, aggregates | Feature engineering pipeline |
| 4 | MLflow: log params, metrics, models; compare runs | MLflow UI with 5+ experiments |

**Validation**: Feature engineering improves model accuracy by 5%+ over baseline.

### Month 5: FastAPI Model Serving

| Week | Topic | Deliverable |
|---|---|---|
| 1 | FastAPI basics: routes, Pydantic schemas, async | Health-check endpoint |
| 2 | Load sklearn model with joblib, serve predictions | `/predict` endpoint |
| 3 | Input validation, error handling, test with Swagger | Production-ready API |
| 4 | Project: house price prediction API | Full end-to-end: train → save → serve |

**Validation**: API accepts JSON input, returns prediction, works from Swagger UI.

---

## Phase 1: Breadth (Months 6-14)

### Month 6-8: Deep Learning (PyTorch)

| Week | Topic |
|---|---|
| 1 | Tensors, autograd, gradients |
| 2 | Linear regression in PyTorch, training loop |
| 3 | Neural networks from scratch (no frameworks) |
| 4 | PyTorch NN module, optimizers |
| 5 | CNNs: conv layers, pooling, architecture |
| 6 | Training a CNN on a real dataset |
| 7-8 | Project: Image classifier |

**Validation**: Train a CNN on CIFAR-10 or Food-101 subset with 70%+ accuracy. Understand every line.

### Month 9-10: Cloud Deployment

| Week | Topic | Deliverable |
|---|---|---|
| 1 | AWS/GCP basics (IaaS vs PaaS, regions, billing) | Account set up |
| 2 | Docker for ML: Dockerfile for model, best practices | Containerized model |
| 3 | Deploy container to cloud (Cloud Run / ECS / SageMaker) | Live API endpoint with URL |
| 4 | CI/CD for ML: GitHub Actions test → build → deploy | Pipeline that re-deploys on push |

**Validation**: Deploy a model to the cloud. Call it from anywhere. It works.

### Month 11: NLP Fundamentals

| Week | Topic | Deliverable |
|---|---|---|
| 1 | Text preprocessing, tokenization, embeddings | Cleaned text dataset |
| 2 | Bag-of-words, TF-IDF, Word2Vec | Text feature pipeline |
| 3 | HuggingFace transformers (BERT sentiment) | Sentiment classifier |
| 4 | Project: text classification API + deployment | End-to-end NLP service |

**Validation**: Build and deploy a HuggingFace-based text classifier.

### Month 12-14: MLOps (Practical, not theoretical)

| Week | Topic | Deliverable |
|---|---|---|
| 1 | Model versioning (DVC + MLflow model registry) | Versioned model repository |
| 2 | Advanced FastAPI: background tasks, caching, rate limiting | Optimized API |
| 3 | Model monitoring: data drift, prediction drift | Monitoring dashboard |
| 4 | SHAP / LIME for model explainability | Explanations on every prediction |
| 5-8 | Capstone: Full ML pipeline | Notebook → model → API → cloud → monitor |

**Validation**: A deployed model with monitoring, explainability, and CI/CD.

---

## Phase 2: Production Capstone (Months 15-20)

### NovaWallet ML Service

| Month | Component | What it proves |
|---|---|---|
| 15-16 | **Fraud detection model**: transaction features, imbalanced data, threshold tuning | Tabular + deployment |
| 17-18 | **Credit scoring model**: feature engineering from financial data, regulatory considerations | Feature engineering + model interpretability |
| 19 | **Integration**: connect both models to NovaWallet via FastAPI | Full-stack ML |
| 20 | **Monitoring + dashboards**: track prediction distributions, model health in production | MLOps maturity |

**No Django for model serving.** Use FastAPI as a separate service. Django handles the main app; FastAPI handles predictions.

### Kaggle (ongoing, 2-3 hours/week from Month 15)

| Goal | Timeline |
|---|---|
| First competition: finish in top 50% | Month 15-16 |
| Second competition: top 25% | Month 17-18 |
| Third competition: top 25% or medal | Month 19-20 |

---

## Phase 3: Job Ready (Months 20-24)

### Month 20-21: System Design + Theory

| Topic | Must be able to do |
|---|---|
| ML system design | Design a recommendation system / fraud detector / search ranking end-to-end |
| Tradeoffs | Batch vs real-time, accuracy vs latency, cost vs performance |
| Case studies | Design for 1M users vs 100M users |
| Past paper walkthroughs | Explain your NovaWallet ML architecture in 15 minutes |

### Month 22: Interview Prep

| Area | Focus |
|---|---|
| ML theory | Bias-variance, regularization, loss functions, gradient descent variants |
| Coding from scratch | KNN, linear regression, logistic regression, decision tree in NumPy |
| LeetCode medium | Arrays, strings, hash maps (not DP/heaps — ML interviews are lighter on DS&A) |
| Behavioral | "Tell me about a time a model failed in production" |

### Month 23-24: Applications

| Target | Realistic salary |
|---|---|
| Local Zambian tech | ZMW 5,000-10,000 |
| African remote (Africashore, Andela, M-KOPA) | $20,000-35,000 |
| International remote | $35,000-55,000 (not $60k at 0-1 yr) |
| **Kaggle + NovaWallet capstone + 3 deployed projects** | **Target: $25,000-40,000 remote** |

---

## Summary: What changed and why

| # | What changed | Why |
|---|---|---|
| 1 | 12mo → 24mo | You learn better with spaced repetition, not cramming |
| 2 | Django → FastAPI for models | FastAPI is what the industry uses for ML serving |
| 3 | Cloud from Month 6, not 9 | Earlier exposure = more practice time before interviews |
| 4 | NLP depth → breadth (tabular + CV + NLP) | Entry-level roles need flexibility, not a niche |
| 5 | 4-week math → daily 30min across 24mo | Real understanding > "I passed the linear algebra test" |

---

## Quick reference: Your next 12 weeks

| Week | What to do |
|---|---|
| 1-2 | Pandas (DataFrames, groupby, merge, pivot) |
| 3-4 | Matplotlib + Seaborn (5 visualizations on Titanic) |
| 5-6 | scikit-learn regression + classification |
| 7 | Cross-validation, GridSearchCV, pipelines |
| 8 | Feature engineering + MLflow |
| 9 | FastAPI basics |
| 10 | Load model, serve predictions |
| 11-12 | House price prediction API (full end-to-end) |

**And every day**: 30 minutes of linear algebra. No breaks.
