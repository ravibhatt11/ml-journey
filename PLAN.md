# 12 Months: Odoo → AI Engineer

A 52-week, resource-sequenced training plan taking me from ERP/backend engineering
(1.5 years of production Odoo — Python, PostgreSQL, deployment) to employable as an
applied AI / ML engineer. Every resource listed here is genuinely free.

---

## How to use this file

Two tracks, same phase sequence, different depth. Pick one based on what the calendar can
actually hold — not what it wishes it could.

| | Track A — Lean | Track B — Full |
|---|---|---|
| Weekly hours | 5–10 | 15–25 |
| Total | ~390 h | ~1,040 h |
| Applications start | Week 43 | Week 30 |
| Portfolio pieces | 4 | 5 |
| Month-12 target | AI/LLM application engineer; strong for internal transition and "Python engineer who does AI" roles | AI Engineer and applied ML Engineer roles externally, with two deep capstones |

GitHub renders the checkboxes below but does not make them clickable in a committed file —
edit the line to `- [x]` when a task is done.

## The rules this plan is built on

1. **Every phase ends with something shipped, public and written up.** Eleven weeks are
   marked **SHIP**. Those are the ones that get me hired; everything else earns the right
   to do them well.
2. **Baseline first, always.** A dumb baseline before any model. Every result is reported
   against it.
3. **Measure, don't assert.** Retrieval metrics, per-class metrics, cost and latency. Eval
   literacy is the clearest signal of someone who has actually shipped with LLMs.
4. **No client data.** Anything derived from real Odoo work is anonymised, and the
   anonymisation approach is stated in the project README.
5. **If I fall behind:** drop optional depth (Kaggle competition, CS224n, the second
   capstone) and protect the SHIP weeks. Move the start date rather than pretending.

## Why this order

Data fluency before modelling, because you cannot model what you cannot interrogate.
Classical ML before deep learning, because that is where the judgment lives — baselines,
leakage, picking a metric that is not a lie. Deep learning before LLM work, so the API
being called is not a black box. Production last, because that layer already exists from
shipping Odoo.

## Market context driving the sequence (2026)

- "AI Engineer" has overtaken "ML Engineer" as the dominant title; the work is
  orchestration-first, not training-first.
- RAG, agents, evals, MLOps, Python and SQL lead employer demand.
- Roughly 6% of ML postings are explicitly entry-level, but over two-thirds state no hard
  experience requirement — the gate is demonstrated capability, not years.
- What is scarce is not algorithm knowledge but problem framing, evaluation judgment and
  production thinking.

This is why Phase 4 (LLM/AI engineering) is the widest phase in both tracks, and why
Phase 5 exists at all.

---

## Track A — Lean (5–10 h/week)

**Budget:** ~390 h over 52 weeks. **Applications start:** week 43.

> Finished beats abandoned. Combined with ERP domain depth this is a genuinely employable position — it just points at a narrower set of doors than Track B.

### Phase 1 · Foundations — weeks 1–8

*Stop being blind inside a dataset. Array and dataframe thinking, plus only the maths that earns its place: enough linear algebra to see what a matrix does, enough calculus to understand optimisation, enough statistics to avoid fooling yourself.*

#### Week 01 — Set the machine up so it runs without willpower  `7–8 h`

- [ ] Block fixed recurring calendar slots — named, defended, non-negotiable
- [ ] Create a public `ml-journey` GitHub repo; commit this plan as PLAN.md
- [ ] [Kaggle Learn](https://www.kaggle.com/learn): Python micro-course (skim what you know)
- [ ] [3Blue1Brown](https://www.3blue1brown.com/topics/linear-algebra) Essence of Linear Algebra, chapters 1–4
- [ ] Pull Odoo sales orders into a Colab dataframe and plot monthly revenue — ship something in week one

#### Week 02 — Pandas until it stops being a fight  `7–8 h`

- [ ] Kaggle Learn: Pandas — indexing, grouping, combining
- [ ] [Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/): Pandas chapter, groupby and merge sections
- [ ] Rewrite one Odoo SQL report as a Pandas pipeline and diff the results
- [ ] Drill: resample a time series by month, quarter and rolling 7-day

#### Week 03 — Visualisation as interrogation, not decoration  `7–8 h`

- [ ] Kaggle Learn: Data Visualization
- [ ] Seaborn: distributions, correlation heatmaps, categorical comparisons
- [ ] Write the five questions your Sales EDA will answer — in the README, before any analysis code
- [ ] Decide and document your anonymisation approach for client data

#### Week 04 — Linear algebra and NumPy, together  `7–8 h`

- [ ] 3Blue1Brown Essence of Linear Algebra, chapters 5–10
- [ ] PDSH NumPy chapter: broadcasting, axis semantics, vectorisation
- [ ] Implement cosine similarity by hand in NumPy, then check against scikit-learn
- [ ] Replace one Python loop over a dataframe with a vectorised expression and time both

#### Week 05 — Calculus, only as far as gradient descent  `7–8 h`

- [ ] 3Blue1Brown Essence of Calculus, chapters 1–4
- [ ] [StatQuest](https://www.youtube.com/@statquest): gradient descent
- [ ] Code a one-dimensional gradient descent loop in NumPy and plot the path
- [ ] Write down in your own words why the chain rule is what makes backprop possible

#### Week 06 — Statistics for not fooling yourself  `7–8 h`

- [ ] StatQuest statistics fundamentals playlist
- [ ] Sampling bias, correlation vs causation, and what a p-value does not tell you
- [ ] Add distribution and outlier analysis to the Sales EDA
- [ ] Find one real sampling bias in your own Odoo data and write it up

#### Week 07 — SQL past what the ORM gives you  `7–8 h`

- [ ] [PG Exercises](https://pgexercises.com/): window functions and CTEs
- [ ] Write three analytical queries over Odoo: revenue rank per category, running totals, year-over-year lag
- [ ] Compare a window-function query against the Pandas equivalent for speed and clarity

#### Week 08 — Ship Project 1 — Odoo Sales EDA · **SHIP**  `7–8 h`

- [ ] Finish the analysis: trend, seasonality, margin vs volume, delivery-lag tail, RFM churn risk
- [ ] Anonymise everything; state the approach explicitly in the README
- [ ] Push public with findings and caveats up front, tech stack last
- [ ] Post a short write-up. First portfolio piece done.

### Phase 2 · Classical ML — weeks 9–22

*Where the judgment comes from. Baselines, leakage, validation, and choosing a metric that does not lie. Everything later — including designing evals for an LLM system — is this instinct applied to a new surface. Also where your ERP domain knowledge is worth the most money.*

#### Week 09 — Framing a business question as a learning problem  `7–8 h`

- [ ] [ML Zoomcamp](https://github.com/DataTalksClub/machine-learning-zoomcamp) module 1 — ML vs rules, the CRISP-DM loop
- [ ] StatQuest: Machine Learning Fundamentals; supervised vs unsupervised
- [ ] Write three real Odoo problems as supervised learning problems — and one that is not one
- [ ] [ISLP](https://www.statlearning.com/) chapter 2

#### Week 10 — Linear regression, built by hand first  `7–8 h`

- [ ] Implement linear regression in NumPy with your own gradient descent loop
- [ ] ML Zoomcamp module 2 — car price regression end to end
- [ ] RMSE vs MAE vs MAPE: when each one misleads
- [ ] ISLP chapter 3

#### Week 11 — Regularisation and the bias–variance tradeoff  `7–8 h`

- [ ] Ridge and lasso: what each does to the coefficients, and why
- [ ] StatQuest: bias and variance, regularisation
- [ ] ISLP chapter 6
- [ ] Apply to a real dataset and compare every result against a dumb baseline

#### Week 12 — Classification from first principles  `7–8 h`

- [ ] Implement logistic regression from scratch — sigmoid, log loss, gradient
- [ ] ML Zoomcamp module 3 — customer churn
- [ ] ISLP chapter 4
- [ ] Explain to yourself why log loss, not accuracy, is what you optimise

#### Week 13 — Evaluation — the week that pays for itself  `7–8 h`

- [ ] Precision, recall, F1; ROC-AUC vs PR-AUC and exactly when each one lies
- [ ] StatQuest: ROC and AUC; confusion matrices
- [ ] ML Zoomcamp module 4 — evaluation
- [ ] Pick the correct metric for three imbalanced scenarios and justify each in writing

#### Week 14 — Validation and leakage  `7–8 h`

- [ ] Stratified k-fold; time-based splits for anything temporal
- [ ] scikit-learn `Pipeline` and `ColumnTransformer` so preprocessing fits only on training folds
- [ ] Deliberately build a leak, measure the inflated score, fix it, write it up — this becomes a portfolio note
- [ ] ISLP chapter 5

#### Week 15 — Trees and forests  `7–8 h`

- [ ] Decision trees, then random forests; why they dominate tabular data
- [ ] ML Zoomcamp module 6; ISLP chapter 8
- [ ] Feature importance — and why impurity importance can mislead

#### Week 16 — Gradient boosting  `7–8 h`

- [ ] XGBoost and LightGBM; the tuning knobs that actually matter
- [ ] StatQuest: gradient boost, XGBoost
- [ ] Head-to-head against your random forest on the same split, with the difference tested not eyeballed

#### Week 17 — Feature engineering  `7–8 h`

- [ ] Categorical encodings: one-hot, ordinal, target encoding and its leakage trap
- [ ] Datetime features and lag features for time series
- [ ] Missing-value strategies, and when missingness is itself signal
- [ ] Write custom scikit-learn transformers so it all lives inside the pipeline

#### Week 18 — Project 2 begins — and so does the conversation at work  `7–8 h`

- [ ] [Olist e-commerce dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce): load, join orders/items/sellers/reviews
- [ ] Define the target (late delivery) and build a time-based split — a random split leaks the future
- [ ] Ship a dumb baseline first: historical late rate. Every later number is measured against it.
- [ ] Draft the internal AI-project pitch for your employer — you now know enough to scope it credibly

#### Week 19 — Project 2 — modelling  `7–8 h`

- [ ] Full pipeline: preprocessing, random forest, gradient boosting
- [ ] Report PR-AUC, not accuracy — late orders are the minority class
- [ ] Check calibration: are the predicted probabilities actually probabilities?

#### Week 20 — Project 2 — explainability  `7–8 h`

- [ ] SHAP values for the top drivers of late delivery
- [ ] Partial dependence for the two most important features
- [ ] Write the findings in business language a logistics manager would act on

#### Week 21 — Unsupervised learning  `7–8 h`

- [ ] k-means and hierarchical clustering; choosing k honestly
- [ ] PCA for dimensionality reduction; ISLP chapter 12
- [ ] RFM customer segmentation on your Odoo data, with the segments named and described

#### Week 22 — Ship Project 2 — Late Delivery Risk · **SHIP**  `7–8 h`

- [ ] README: problem and outcome first, metrics against the stated baseline, tech stack last
- [ ] A real limitations section — what would break this in production
- [ ] Publish plus a blog post on the leakage experiment from week 14
- [ ] Second portfolio piece done.

### Phase 3 · Deep learning — weeks 23–32

*Working understanding, not research depth. You need to fine-tune a small model, read a model card, and reason about embeddings, tokenisation and attention — so that the thing you call over an API stops being a black box.*

#### Week 23 — Deep learning, top-down  `7–8 h`

- [ ] [fast.ai](https://course.fast.ai/) lessons 1–2 — train a working model in the first session
- [ ] Deploy that model to [Hugging Face Spaces](https://huggingface.co/spaces) — your first live URL, in month six not month ten
- [ ] Set up Colab or Kaggle notebooks for free GPU; do not buy hardware this year

#### Week 24 — What is actually happening in there  `7–8 h`

- [ ] fast.ai lesson 3 — SGD, loss functions, the learning rate as the hyperparameter that matters
- [ ] [Karpathy](https://karpathy.ai/zero-to-hero.html): The spelled-out intro to neural networks, part 1
- [ ] Neurons, layers, activations — forward pass by hand on paper for a two-layer net

#### Week 25 — Backprop, built from nothing  `7–8 h`

- [ ] Finish Karpathy's micrograd — type it, do not watch it
- [ ] Derive one backward pass by hand and check it against your code
- [ ] Dropout, batch norm, early stopping: what each one is actually preventing

#### Week 26 — PyTorch by hand  `7–8 h`

- [ ] Tensors, `autograd`, `nn.Module`, `DataLoader`
- [ ] Write a training loop yourself — no trainer abstraction
- [ ] Train a small net on the tabular data from Project 2 and compare it against gradient boosting (it will probably lose; that is the lesson)

#### Week 27 — Text, tokens and transfer  `7–8 h`

- [ ] fast.ai lesson 4 — NLP
- [ ] [Hugging Face NLP course](https://huggingface.co/learn) chapters 1–2: transformers and tokenisers
- [ ] Tokenise the same sentence three ways and explain the differences

#### Week 28 — Fine-tuning — the highest-value practical skill here  `7–8 h`

- [ ] HF NLP course chapter 3 — fine-tuning a pretrained model
- [ ] Fine-tune DistilBERT on a public text-classification dataset
- [ ] Read three model cards properly and learn to pick a model for a task and a budget

#### Week 29 — Embeddings — the bridge to everything next  `7–8 h`

- [ ] What a vector representation is; cosine similarity in practice
- [ ] sentence-transformers: embed a corpus and run nearest-neighbour search
- [ ] Visualise the embedding space with PCA and see the clusters your data already has

#### Week 30 — Attention, and what a GPT actually is  `7–8 h`

- [ ] Karpathy: Let's build GPT — code along, do not skip
- [ ] Self-attention, positional encoding, encoder vs decoder
- [ ] Write a one-page explanation of attention for a non-technical colleague

#### Week 31 — Project 3 — baseline before transformer  `7–8 h`

- [ ] Support ticket triage: category and urgency, on synthetic or anonymised data
- [ ] TF-IDF plus logistic regression baseline first — report it whatever it says
- [ ] Then fine-tune the transformer and measure the actual gain

#### Week 32 — Ship Project 3 — Support Ticket Triage · **SHIP**  `7–8 h`

- [ ] Per-class metrics, not overall accuracy — the rare urgent class is the one that matters
- [ ] Confusion matrix plus a written error analysis: which classes confuse, and why
- [ ] Measure inference latency and model size; state the cost at production volume
- [ ] Deploy to HF Spaces. Third portfolio piece done.

### Phase 4 · LLM / AI engineering — weeks 33–42

*The phase that gets you hired. RAG is the most in-demand AI engineering skill of 2026, agentic postings grew ~280% this year, and eval literacy is the clearest separator between people who have shipped and people who have watched. Everything before this was earning the right to do it well.*

#### Week 33 — First RAG, end to end  `8–10 h`

- [ ] [LLM Zoomcamp](https://github.com/DataTalksClub/llm-zoomcamp) module 1 — LLMs and retrieval
- [ ] Build a naive RAG over a small document set and notice exactly where it is bad
- [ ] Pick your corpus for the headline project — Odoo docs work because you can tell when an answer is wrong

#### Week 34 — Prompt and context engineering as a discipline  `8–10 h`

- [ ] [Anthropic docs](https://docs.claude.com) prompt engineering guide; [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook)
- [ ] System prompts, few-shot selection, decomposition, structured output
- [ ] Build a versioned prompt library — prompts in files, under git, not pasted in code
- [ ] Token economics: context windows, caching, cost per thousand calls

#### Week 35 — Tool calling and structured output  `8–10 h`

- [ ] Function/tool calling with schema validation and retry on malformed output
- [ ] [OpenAI Cookbook](https://github.com/openai/openai-cookbook) patterns for structured extraction
- [ ] Map this back to the AI tools you already built in Odoo — write down what you would do differently now

#### Week 36 — Vector search, in a database you already know  `8–10 h`

- [ ] LLM Zoomcamp module 2 — vector search and embeddings
- [ ] [pgvector](https://github.com/pgvector/pgvector) in Postgres — adding vector search to an existing database is a very employable sentence
- [ ] Three chunking strategies implemented and compared: fixed, overlapping, semantic

#### Week 37 — Build the eval set — your single biggest differentiator  `8–10 h`

- [ ] Hand-write 80 question/answer pairs with known-correct source documents. By hand. This is the work.
- [ ] [Hamel Husain](https://hamel.dev/) on evals — read the error-analysis pieces twice
- [ ] Measure recall@5 and MRR on your naive pipeline and record the numbers

#### Week 38 — LLM-as-judge, and its failure modes  `8–10 h`

- [ ] Rubric grading with an LLM judge; [Ragas](https://docs.ragas.io/) for RAG-specific metrics
- [ ] Position bias, self-preference, verbosity bias — know them by name
- [ ] Validate your judge against your own human labels; report the agreement rate

#### Week 39 — Hybrid search and reranking  `8–10 h`

- [ ] BM25 plus dense retrieval; add a reranker on top
- [ ] Produce the ablation table: naive / hybrid / hybrid+rerank, each with recall, cost and latency
- [ ] Decide what you would actually ship, and justify it on the numbers

#### Week 40 — Agents, guardrails and the public record  `8–10 h`

- [ ] [HF Agents course](https://huggingface.co/learn) — tool loops, planning, state, error handling
- [ ] Observability: trace every step; debugging a non-deterministic system
- [ ] Build one agent without a framework, then one with LangGraph, and know the tradeoff
- [ ] Rewrite LinkedIn now: *Python/ERP engineer building AI applications.* Start one short post a week.

#### Week 41 — Error analysis as a process  `8–10 h`

- [ ] Pull 50 real failures from your RAG system and categorise them
- [ ] Fix the single biggest bucket and re-measure — this loop is the actual job
- [ ] Document what you chose not to fix, and why

#### Week 42 — Ship Project 4 — the headline piece · **SHIP**  `8–10 h`

- [ ] Grounded Q&A over a real corpus with citations and an explicit I-don't-know path
- [ ] Blog post, not just a README: chunking decisions with numbers, the ablation table, the error analysis
- [ ] This is the artefact that does more for you than three more courses. Give it a weekend of polish.
- [ ] Fourth portfolio piece done.

### Phase 5 · Production & MLOps — weeks 43–46

*The gap between a notebook and an offer. Docker appears in roughly 15% of ML postings, Kubernetes in 18% — but what is actually scarce is production thinking: error handling, observability, cost per thousand calls. You already deploy software for a living, so this phase is short.*

#### Week 43 — From notebook to service  `7–8 h`

- [ ] Wrap the RAG system in [FastAPI](https://fastapi.tiangolo.com/) with request validation and real error handling
- [ ] Containerise with Docker; watch the image size and the cold start
- [ ] Applications begin now: 3 roles a week, every week, from here to the end

#### Week 44 — Deploy and watch it  `7–8 h`

- [ ] Live on HF Spaces or a free tier — a link a recruiter can click
- [ ] Structured logging; track latency, cost and error rate per request
- [ ] [Made With ML](https://madewithml.com/) — the monitoring and systems-design sections
- [ ] 3 applications

#### Week 45 — Evals in CI  `7–8 h`

- [ ] GitHub Actions running your eval suite on every push, with a regression threshold
- [ ] Break a prompt deliberately and watch the pipeline catch it
- [ ] Evals in CI is a senior signal; say so explicitly in the README
- [ ] 3 applications

#### Week 46 — Tracking, drift and cost  `7–8 h`

- [ ] MLflow basics: runs, params, metrics, artefacts
- [ ] Write the monitoring plan: what drifts, how you would detect it, what you would do
- [ ] Find the cheapest configuration that still passes your evals — and prove it
- [ ] 3 applications

### Phase 6 · Capstone — weeks 47–50

*Proof. One or two projects that solve a real problem for a real user, end to end, in a domain you understand better than your interviewer will. Three to five strong projects beat fifteen tutorials, so this is also where you prune.*

#### Week 47 — Capstone — scope before code  `7–8 h`

- [ ] Pick one: ERP demand forecasting, or vendor-invoice field extraction
- [ ] Write the problem statement and the success metric first, in the README
- [ ] Assemble and document the data; decide the evaluation protocol before modelling
- [ ] 3 applications

#### Week 48 — Capstone — baseline, then the real thing  `7–8 h`

- [ ] Naive baseline first: seasonal average for forecasting, regex for extraction
- [ ] Build the real pipeline and measure the lift honestly
- [ ] Backtest properly — no future information anywhere near the training window
- [ ] 3 applications

#### Week 49 — Capstone — make it real  `7–8 h`

- [ ] API plus a live demo; a human-review path for low-confidence outputs
- [ ] Per-field or per-horizon accuracy, not one headline number
- [ ] Record a 90-second demo video
- [ ] 3 applications

#### Week 50 — Ship the capstone, then prune · **SHIP**  `7–8 h`

- [ ] Full write-up with limitations and a what-I-would-do-next section
- [ ] Prune the portfolio to four excellent pinned repos; unpin the practice work
- [ ] Every project has a live link, a stated baseline and a metric. Check all four.
- [ ] 3 applications

### Phase 7 · Job preparation — weeks 51–52

*Conversion. The most common failure is a candidate who cannot defend their own portfolio cold. Applications start well before this phase — week 43 on the lean track, week 30 on the full track — because waiting until you feel ready costs people six months.*

#### Week 51 — Narrative and defence  `7–8 h`

- [ ] Rewrite the CV around projects and metrics, not responsibilities
- [ ] [Machine Learning Interviews Book](https://huyenchip.com/ml-interviews-book/) — skim the whole thing, drill the weak parts
- [ ] For each project, a 90-second answer: problem, baseline, metric, what went wrong, what you would change
- [ ] Rehearse the transition story out loud until it stops sounding rehearsed

#### Week 52 — Cadence, not a finish line  `7–8 h`

- [ ] 10 applications out; 5 warm outreach messages to people doing the work you want
- [ ] Two mock interviews — one technical, one behavioural
- [ ] ML system design practice out loud: design a RAG system for legal documents
- [ ] Write the 12-month retro. Then set the next quarter's plan.

---

## Track B — Full (15–25 h/week)

**Budget:** ~1,040 h over 52 weeks. **Applications start:** week 30.

> Competitive against bootcamp graduates and many CS new-grads by month 12. Main risk is burnout around month 5–6 while working full-time.

### Phase 1 · Foundations — weeks 1–4

*Stop being blind inside a dataset. Array and dataframe thinking, plus only the maths that earns its place: enough linear algebra to see what a matrix does, enough calculus to understand optimisation, enough statistics to avoid fooling yourself.*

#### Week 01 — Set up, then move fast  `~20 h`

- [ ] Block fixed recurring calendar slots — named, defended, non-negotiable
- [ ] Create a public `ml-journey` repo; commit this plan as PLAN.md
- [ ] [Kaggle Learn](https://www.kaggle.com/learn): Python and Pandas micro-courses
- [ ] [3Blue1Brown](https://www.3blue1brown.com/topics/linear-algebra) Essence of Linear Algebra, chapters 1–6
- [ ] [PDSH](https://jakevdp.github.io/PythonDataScienceHandbook/) NumPy chapter — work every example
- [ ] Pull Odoo sales orders into Colab and plot monthly revenue

#### Week 02 — Pandas mastery and the EDA brief  `~20 h`

- [ ] Kaggle Learn: Data Visualization; seaborn distributions and heatmaps
- [ ] PDSH Pandas chapter in full: groupby, merge, pivot, resample
- [ ] Drills: rewrite three Odoo SQL reports as Pandas pipelines and diff them
- [ ] Write the five questions your Sales EDA will answer, in the README, before any analysis
- [ ] Decide and document your anonymisation approach

#### Week 03 — Maths and SQL in one push  `~20 h`

- [ ] 3Blue1Brown Linear Algebra 7–15; Essence of Calculus 1–6
- [ ] [StatQuest](https://www.youtube.com/@statquest) statistics fundamentals playlist
- [ ] Code gradient descent in NumPy by hand and plot the descent path
- [ ] [PG Exercises](https://pgexercises.com/): window functions and CTEs
- [ ] Implement cosine similarity by hand; check against scikit-learn

#### Week 04 — Ship Project 1 — Odoo Sales EDA · **SHIP**  `~20 h`

- [ ] Trend, seasonality, margin vs volume, delivery-lag tail, RFM churn risk
- [ ] Anonymise everything and state the approach in the README
- [ ] Push public: findings and caveats first, tech stack last
- [ ] Write it up as a post. First portfolio piece done.

### Phase 2 · Classical ML — weeks 5–13

*Where the judgment comes from. Baselines, leakage, validation, and choosing a metric that does not lie. Everything later — including designing evals for an LLM system — is this instinct applied to a new surface. Also where your ERP domain knowledge is worth the most money.*

#### Week 05 — Framing, and regression from scratch  `~20 h`

- [ ] [ML Zoomcamp](https://github.com/DataTalksClub/machine-learning-zoomcamp) modules 1–2
- [ ] Implement linear regression in NumPy with your own gradient descent
- [ ] [ISLP](https://www.statlearning.com/) chapters 2–3
- [ ] Write three real Odoo problems as supervised learning problems — and one that is not one

#### Week 06 — Regularisation and the tradeoff  `~20 h`

- [ ] Ridge and lasso: what each does to the coefficients, and why
- [ ] StatQuest: bias and variance; ISLP chapter 6
- [ ] RMSE vs MAE vs MAPE and when each misleads
- [ ] Pick a [Kaggle Playground](https://www.kaggle.com/competitions) competition and make your first submission

#### Week 07 — Classification from first principles  `~20 h`

- [ ] Implement logistic regression from scratch — sigmoid, log loss, gradient
- [ ] ML Zoomcamp module 3 — customer churn; ISLP chapter 4
- [ ] Explain to yourself why log loss, not accuracy, is what you optimise

#### Week 08 — Evaluation — the week that pays for itself  `~20 h`

- [ ] Precision, recall, F1; ROC-AUC vs PR-AUC and exactly when each lies
- [ ] StatQuest: ROC and AUC; ML Zoomcamp module 4
- [ ] Calibration: are your predicted probabilities actually probabilities?
- [ ] Pick the correct metric for three imbalanced scenarios and justify each in writing

#### Week 09 — Validation and leakage  `~20 h`

- [ ] Stratified k-fold and time-based splits; ISLP chapter 5
- [ ] scikit-learn `Pipeline` and `ColumnTransformer` so preprocessing fits only on training folds
- [ ] Build a leak deliberately, measure the inflated score, fix it, write it up
- [ ] Kaggle Playground: second submission with proper CV

#### Week 10 — Trees, forests and explanation  `~20 h`

- [ ] Decision trees then random forests; ISLP chapter 8; ML Zoomcamp module 6
- [ ] Feature importance, and why impurity importance misleads
- [ ] SHAP values: local and global explanations

#### Week 11 — Boosting, and a public leaderboard  `~20 h`

- [ ] XGBoost and LightGBM; the tuning knobs that actually matter
- [ ] Head-to-head against random forest on the same split
- [ ] Kaggle Playground: aim for top 40% and publish your notebook with the reasoning. Then stop — Kaggle is a good teacher and a bad career.

#### Week 12 — Feature engineering and unsupervised methods  `~20 h`

- [ ] Categorical encodings including target encoding and its leakage trap
- [ ] Datetime and lag features; missingness as signal
- [ ] k-means, hierarchical clustering, PCA; ISLP chapter 12
- [ ] RFM segmentation on your Odoo data with the segments named

#### Week 13 — Ship Project 2 — and pitch AI at work · **SHIP**  `~20 h`

- [ ] [Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) late-delivery prediction: baseline, time-based split, full pipeline, PR-AUC
- [ ] SHAP-driven business write-up a logistics manager would act on
- [ ] Deploy the model behind a simple endpoint — do not wait for the MLOps phase
- [ ] Make the internal AI-project pitch to your employer. Paid production experience beats any portfolio project.

### Phase 3 · Deep learning — weeks 14–22

*Working understanding, not research depth. You need to fine-tune a small model, read a model card, and reason about embeddings, tokenisation and attention — so that the thing you call over an API stops being a black box.*

#### Week 14 — Deep learning, top-down  `~20 h`

- [ ] [fast.ai](https://course.fast.ai/) lessons 1–2
- [ ] Deploy a trained model to [Hugging Face Spaces](https://huggingface.co/spaces) — first live URL, month four
- [ ] Set up Colab and Kaggle free GPU; do not buy hardware this year

#### Week 15 — Optimisation, then backprop from nothing  `~20 h`

- [ ] fast.ai lessons 3–4 — SGD, loss, learning rate
- [ ] [Karpathy](https://karpathy.ai/zero-to-hero.html): micrograd, part 1 — type it, do not watch it
- [ ] Derive one backward pass by hand and check it against your code

#### Week 16 — Micrograd finished, PyTorch begun  `~20 h`

- [ ] Complete micrograd; then PyTorch tensors and `autograd`
- [ ] [Dive into Deep Learning](https://d2l.ai/) as your reference text
- [ ] Dropout, batch norm, early stopping: what each one prevents

#### Week 17 — Training loops you wrote yourself  `~20 h`

- [ ] `nn.Module`, `DataLoader`, a hand-written training loop — no trainer abstraction
- [ ] Train on the Project 2 tabular data and compare against gradient boosting
- [ ] Learning-rate schedules and why the LR finder works

#### Week 18 — Text, tokens and vectors  `~20 h`

- [ ] [HF NLP course](https://huggingface.co/learn) chapters 1–3: transformers, tokenisers, datasets
- [ ] Embeddings and cosine similarity; sentence-transformers over a real corpus
- [ ] Visualise the embedding space with PCA and find the clusters already in your data

#### Week 19 — Fine-tuning properly  `~20 h`

- [ ] HF NLP course chapters 3–5 — fine-tune and share a model
- [ ] Fine-tune DistilBERT on a public classification set; per-class metrics
- [ ] Read five model cards and learn to pick for a task and a budget

#### Week 20 — Build a transformer from scratch  `~20 h`

- [ ] Karpathy: Let's build GPT — line by line, no shortcuts
- [ ] Self-attention, multi-head attention, positional encoding, causal masking
- [ ] Write a one-page explanation of attention for a non-technical colleague

#### Week 21 — Project 3 — baseline before transformer  `~20 h`

- [ ] Support ticket triage: category and urgency, synthetic or anonymised data
- [ ] TF-IDF plus logistic regression baseline first — report it whatever it says
- [ ] Fine-tune the transformer; measure the real gain and the real cost

#### Week 22 — Ship Project 3 — Support Ticket Triage · **SHIP**  `~20 h`

- [ ] Per-class metrics, confusion matrix, written error analysis
- [ ] Inference latency and model size measured; cost stated at production volume
- [ ] Deployed to HF Spaces with a live link
- [ ] Optional depth: [CS224n](https://web.stanford.edu/class/cs224n/) attention lectures. Third piece done.

### Phase 4 · LLM / AI engineering — weeks 23–32

*The phase that gets you hired. RAG is the most in-demand AI engineering skill of 2026, agentic postings grew ~280% this year, and eval literacy is the clearest separator between people who have shipped and people who have watched. Everything before this was earning the right to do it well.*

#### Week 23 — First RAG, end to end  `~22 h`

- [ ] [LLM Zoomcamp](https://github.com/DataTalksClub/llm-zoomcamp) module 1
- [ ] Build a naive RAG over a real corpus and find exactly where it breaks
- [ ] [Anthropic](https://github.com/anthropics/anthropic-cookbook) and [OpenAI](https://github.com/openai/openai-cookbook) cookbook patterns
- [ ] Choose the corpus for the headline project — one where you can tell when an answer is wrong

#### Week 24 — Prompt and context engineering as a discipline  `~22 h`

- [ ] [Anthropic](https://docs.claude.com) prompt engineering guide; structured output and decomposition
- [ ] Versioned prompt library — prompts in files, under git
- [ ] Token economics: context windows, caching, cost per thousand calls
- [ ] Model selection: prove empirically when a small fast model beats a frontier one

#### Week 25 — Tool calling and system integration  `~22 h`

- [ ] Function calling with schema validation, retries on malformed output, partial failure handling
- [ ] MCP — connecting models to real systems; increasingly on hiring checklists
- [ ] Revisit the AI tools you built in Odoo and write down what you would do differently now

#### Week 26 — Retrieval, measured  `~22 h`

- [ ] LLM Zoomcamp module 2; [pgvector](https://github.com/pgvector/pgvector) in Postgres
- [ ] Three chunking strategies implemented and compared with numbers
- [ ] Metadata filtering and why it beats a bigger k

#### Week 27 — Build the eval set — your single biggest differentiator  `~22 h`

- [ ] Hand-write 100 question/answer pairs with known-correct sources. By hand. This is the work.
- [ ] [Hamel Husain](https://hamel.dev/) on evals — read the error-analysis pieces twice
- [ ] recall@k, MRR and nDCG computed on your current pipeline and recorded

#### Week 28 — Judges and regression tests  `~22 h`

- [ ] LLM-as-judge with rubrics; [Ragas](https://docs.ragas.io/) for RAG metrics
- [ ] Position bias, self-preference, verbosity bias — know them by name
- [ ] Validate the judge against your human labels; report agreement
- [ ] Prompt regression suite: catch the change that fixes one case and breaks six

#### Week 29 — Hybrid search and reranking  `~22 h`

- [ ] BM25 plus dense retrieval; add a cross-encoder reranker
- [ ] The ablation table: naive / hybrid / hybrid+rerank with recall, cost and latency
- [ ] Decide what you would ship and justify it on the numbers alone

#### Week 30 — Error analysis at scale — and applications open  `~22 h`

- [ ] Categorise 50 real failures; fix the biggest bucket; re-measure
- [ ] Document what you chose not to fix, and why
- [ ] Applications start now: 5 roles a week, every week, to the end
- [ ] [NeetCode](https://neetcode.io/): 3–4 problems a week from here on

#### Week 31 — Agents that survive contact  `~22 h`

- [ ] [HF Agents course](https://huggingface.co/learn) — tool loops, planning, state management
- [ ] Guardrails and permission boundaries — you already hit this with role-aware AI tools in Odoo
- [ ] Observability: trace every step; debug a non-deterministic system
- [ ] Build one agent without a framework and one with LangGraph; know the tradeoff

#### Week 32 — Ship Project 4 — the headline piece · **SHIP**  `~22 h`

- [ ] Grounded Q&A over a real corpus with citations and an explicit I-don't-know path
- [ ] Blog post: chunking decisions with numbers, the ablation table, the error analysis
- [ ] This artefact outperforms three more courses. Give it real polish.
- [ ] Fourth portfolio piece done. 5 applications.

### Phase 5 · Production & MLOps — weeks 33–38

*The gap between a notebook and an offer. Docker appears in roughly 15% of ML postings, Kubernetes in 18% — but what is actually scarce is production thinking: error handling, observability, cost per thousand calls. You already deploy software for a living, so this phase is short.*

#### Week 33 — From notebook to service  `~20 h`

- [ ] [FastAPI](https://fastapi.tiangolo.com/) with request validation and real error handling
- [ ] Docker: containerise, watch image size and cold start
- [ ] Streamlit or Gradio for the demo layer — demos only, never production
- [ ] 5 applications

#### Week 34 — Deploy and instrument  `~20 h`

- [ ] Live deployment with structured logging
- [ ] Track latency, cost and error rate per request; build a small cost dashboard
- [ ] [Made With ML](https://madewithml.com/) — systems design and monitoring sections
- [ ] 5 applications

#### Week 35 — Evals in CI  `~20 h`

- [ ] GitHub Actions running the eval suite on every push with a regression threshold
- [ ] Break a prompt deliberately and watch the pipeline catch it
- [ ] Say it explicitly in the README — this is a senior signal
- [ ] 5 applications

#### Week 36 — Tracking and reproducibility  `~20 h`

- [ ] MLflow: runs, params, metrics, artefacts; model versioning
- [ ] [MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp) — orchestration and reproducible pipelines
- [ ] Make one training run reproducible from a clean checkout
- [ ] 5 applications

#### Week 37 — Drift, monitoring and cost  `~20 h`

- [ ] Data drift and performance decay: what you would detect and how
- [ ] Write the monitoring plan for the RAG service
- [ ] Find the cheapest configuration that still passes your evals — and prove it
- [ ] 5 applications

#### Week 38 — Design it before you build it  `~20 h`

- [ ] [Full Stack Deep Learning](https://fullstackdeeplearning.com/) — ML product design
- [ ] Write a one-page system design doc for each capstone: interfaces, failure modes, metrics
- [ ] [ML system design case studies](https://www.evidentlyai.com/ml-system-design) — read five
- [ ] 5 applications

### Phase 6 · Capstone — weeks 39–46

*Proof. One or two projects that solve a real problem for a real user, end to end, in a domain you understand better than your interviewer will. Three to five strong projects beat fifteen tutorials, so this is also where you prune.*

#### Week 39 — Capstone A — scope before code  `~20 h`

- [ ] ERP demand forecasting: problem statement and success metric first
- [ ] Assemble and document the data; define the evaluation protocol before modelling
- [ ] Decide what a useful result looks like to a planner, not to a data scientist
- [ ] 5 applications

#### Week 40 — Capstone A — baseline and backtest  `~20 h`

- [ ] Naive seasonal baseline; every later number measured against it
- [ ] Build a proper backtesting harness — no future information near the training window
- [ ] Choose the horizon and the error metric deliberately, and say why
- [ ] 5 applications

#### Week 41 — Capstone A — model and evaluate  `~20 h`

- [ ] Real model; measure the lift honestly, including where it loses to the baseline
- [ ] Per-SKU and per-horizon breakdown, not one headline number
- [ ] Prediction intervals, because a point forecast is not actionable
- [ ] 5 applications

#### Week 42 — Ship Capstone A · **SHIP**  `~20 h`

- [ ] Deployed service with a live demo and a 90-second video
- [ ] Write-up with limitations and a what-I-would-do-next section
- [ ] Fifth portfolio piece done. 5 applications.

#### Week 43 — Capstone B — the natural-language ERP agent  `~20 h`

- [ ] Natural language to ERP query: planner, read-only tools, structured answer
- [ ] Guardrails: read-only, company scoping, row limits, never raw SQL from model output
- [ ] Return the query it ran alongside the answer — trust is a feature
- [ ] 5 applications

#### Week 44 — Capstone B — evaluate the agent  `~20 h`

- [ ] 60 questions with known-correct answers; measure end-to-end accuracy and tool-choice accuracy
- [ ] Trace every step; make failures diagnosable from the logs alone
- [ ] Adversarial cases: ambiguous questions, out-of-scope requests, injection attempts
- [ ] 5 applications

#### Week 45 — Capstone B — harden and deploy  `~20 h`

- [ ] Auth, multi-tenancy, rate limiting, cost caps per user
- [ ] Deploy live; record the demo video
- [ ] Document the failure modes you did not solve — honesty reads as senior
- [ ] 5 applications

#### Week 46 — Ship Capstone B, then prune · **SHIP**  `~20 h`

- [ ] Full write-up and live link
- [ ] Prune the portfolio to four or five excellent pinned repos; unpin everything else
- [ ] Every project: live link, stated baseline, real metric, honest limitations. Verify all five.
- [ ] 5 applications

### Phase 7 · Job preparation — weeks 47–52

*Conversion. The most common failure is a candidate who cannot defend their own portfolio cold. Applications start well before this phase — week 43 on the lean track, week 30 on the full track — because waiting until you feel ready costs people six months.*

#### Week 47 — Narrative, CV, and the story  `~18 h`

- [ ] Rewrite the CV around projects and metrics, not responsibilities
- [ ] [Machine Learning Interviews Book](https://huyenchip.com/ml-interviews-book/) — work the whole thing
- [ ] Rehearse the transition story until it stops sounding rehearsed
- [ ] 5 applications

#### Week 48 — ML system design out loud  `~18 h`

- [ ] Four mock designs spoken aloud: recommender, RAG over legal docs, fraud detection, ticket triage at scale
- [ ] Practise the evaluation question specifically — it is where most candidates fall apart
- [ ] Record yourself once; watch it once; fix the worst habit
- [ ] 5 applications

#### Week 49 — Coding, and defending your own work  `~18 h`

- [ ] NeetCode patterns — arrays, hashing, two pointers, trees, graphs
- [ ] For every project, a 90-second answer: problem, baseline, metric, what went wrong, what you would change
- [ ] Have someone technical interrogate one project without warning
- [ ] 5 applications

#### Week 50 — Mocks and behavioural  `~18 h`

- [ ] Three mock interviews: technical, system design, behavioural
- [ ] STAR stories from Odoo work — incidents, migrations, stakeholder conflict
- [ ] Prepare your own questions; interviews are two-directional
- [ ] 5 applications

#### Week 51 — Offers and leverage  `~18 h`

- [ ] Compensation research for your market and level; know your number before the call
- [ ] Practise the negotiation conversation out loud
- [ ] Line up references; warm up your network deliberately
- [ ] 5 applications

#### Week 52 — Cadence, not a finish line  `~18 h`

- [ ] Sustained pipeline: applications, outreach, and one post a week continue after the first offer
- [ ] Write the 12-month retro — what worked, what you would cut
- [ ] Set the next quarter's plan: depth in one domain, or breadth into MLOps
- [ ] You are not finished. You are employable. Those are different things, and this is the good one.
---

## Portfolio — the actual deliverable

Quality over quantity: 4–5 end-to-end projects, each with a live link, a stated baseline,
a real metric and an honest limitations section.

| # | Project | Phase | Lean wk | Full wk |
|---|---|---|---|---|
| 1 | Odoo Sales EDA (anonymised) | 1 | 8 | 4 |
| 2 | Late Delivery Risk (Olist, tabular) | 2 | 22 | 13 |
| 3 | Support Ticket Triage (fine-tuned transformer) | 3 | 32 | 22 |
| 4 | Grounded Q&A + eval harness — **headline piece** | 4 | 42 | 32 |
| 5 | Capstone: demand forecasting / NL→ERP agent | 6 | 50 | 42, 46 |

Non-negotiables for every entry: live clickable demo; README opening with the problem and
the outcome, not the tech stack; metrics against a stated baseline; a "limitations and what
I'd do next" section; a written post on one non-obvious decision.

## Resource index

**Foundations** · [Kaggle Learn](https://www.kaggle.com/learn) ·
[Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/) ·
[3Blue1Brown](https://www.3blue1brown.com/topics/linear-algebra) ·
[StatQuest](https://www.youtube.com/@statquest) · [PG Exercises](https://pgexercises.com/)

**Classical ML** · [ML Zoomcamp](https://github.com/DataTalksClub/machine-learning-zoomcamp) ·
[ISLP (free PDF)](https://www.statlearning.com/) ·
[scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html) ·
[Hands-On ML notebooks](https://github.com/ageron/handson-ml3)

**Deep learning** · [fast.ai](https://course.fast.ai/) ·
[Karpathy: Zero to Hero](https://karpathy.ai/zero-to-hero.html) ·
[Hugging Face courses](https://huggingface.co/learn) · [d2l.ai](https://d2l.ai/) ·
[CS224n](https://web.stanford.edu/class/cs224n/)

**LLM / AI engineering** · [LLM Zoomcamp](https://github.com/DataTalksClub/llm-zoomcamp) ·
[Anthropic docs](https://docs.claude.com) ·
[Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook) ·
[OpenAI Cookbook](https://github.com/openai/openai-cookbook) ·
[Hamel Husain on evals](https://hamel.dev/) · [Ragas](https://docs.ragas.io/) ·
[pgvector](https://github.com/pgvector/pgvector) ·
[DeepLearning.AI short courses](https://www.deeplearning.ai/short-courses/)

**Production / MLOps** · [Made With ML](https://madewithml.com/) ·
[MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp) ·
[Full Stack Deep Learning](https://fullstackdeeplearning.com/) ·
[FastAPI](https://fastapi.tiangolo.com/) · [Hugging Face Spaces](https://huggingface.co/spaces)

**Job prep** · [ML Interviews Book](https://huyenchip.com/ml-interviews-book/) ·
[NeetCode](https://neetcode.io/) ·
[ML system design case studies](https://www.evidentlyai.com/ml-system-design)

**Compute** · [Google Colab](https://colab.research.google.com) free tier ·
Kaggle Notebooks (~30 GPU h/week). No hardware purchase this year.

## Log

Weekly: one commit and two sentences — what I learned, what confused me. At month 12 that
log is the interview prep, the blog backlog and the proof of consistency.
