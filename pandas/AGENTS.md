# AGENTS.md

## What this repo is

A **Pandas learning repository** — a 7-day roadmap of Jupyter notebooks teaching pandas.
Not a production codebase. No build, test, or lint pipeline.

## Structure

```
Day-1: Pandas Foundations-series,DataFrame & Data Loading/
  Day 1 : Pandas Foundations - Series,DataFrames & Data Loading.ipynb
  students.csv
  sample_data.csv
Day-2: Data Selection, Filtering, Indexing & Sorting/
  Day 2 : Data Selection, Filtering, Indexing & Sorting.ipynb
  employees_report.csv
Day-3: Data Cleaning/
  Day 3 : Data Cleaning - Missing Values, Duplicates, Type Conversion & String Operations.ipynb
.opencode/     # OpenCode plugin config (do not edit)
.omo/          # OpenCode orchestration sessions
.ipynb_checkpoints/  # Jupyter checkpoints (auto-generated)
```

Each day folder is named `Day-N: Topic/` and contains one notebook named `Day N : Topic.ipynb` plus any CSV data files used in examples.

## Notebook format

Notebooks follow a strict educational format:

1. **Roadmap progress tracker** — a table showing all 7 days with status (✅ complete, 🚀 in progress, ⏳ pending)
2. **Learning objectives** — bulleted list of what the day covers
3. **Worked examples** — markdown cells describe what each example does; expected output is shown as a markdown code block below it (never as an executed cell)
4. **Knowledge check** — short questions (leave blank spaces for answers; do not fill them in)
5. **Code challenge** — hands-on exercise at the end
6. **Summary** — a closing markdown recap of the day's concepts

When creating a new day notebook, match this format exactly. Copy the structure from the most recent day (e.g., Day 5) and adapt the content.

## CSV data files

CSV files live alongside the notebook they support. They are loaded in code cells with:

```python
df = pd.read_csv("filename.csv")
```

File paths are relative to the notebook's directory.

## Environment

- Python: anaconda3, Python 3.13
- Pandas is installed via anaconda3
- Jupyter is available at `/home/ivwananji-silungwe/anaconda3/bin/jupyter-notebook`

### Critical: `jupyter notebook` command is broken

Running `jupyter notebook` opens **Bruno** (an API client) instead of Jupyter. This is a PATH conflict.
To open Jupyter correctly, use the full path:

```bash
/home/ivwananji-silungwe/anaconda3/bin/jupyter-notebook
```

## Creating new day notebooks

When asked to create a notebook for a new day:

1. Create folder `Day-N: Topic/`
2. Create notebook `Day N : Topic.ipynb` inside it
3. Start with the roadmap progress tracker (copy from Day 5, update statuses)
4. Write learning objectives, then worked examples with expected outputs shown as markdown code blocks
5. End with a knowledge check (blank answer spaces), a code challenge, and a summary
6. Include CSV data files if the examples need them

### Code cells stay blank — the learner writes the code

Day 5 established a **learn-by-typing** workflow. All lesson content lives in **markdown cells**; every Python code cell is left **empty except for the comment** `# Write your Python code here`. The learner types the code themselves.

Guidelines:

- **Python cells**: contain only `# Write your Python code here` — never the actual code.
- **Expected outputs**: shown as markdown code blocks (```text) in the markdown cell that follows the example — this lets the learner verify their own result.
- **Dataset definitions**: the data values are also left for the learner to type (the markdown section header shows the dataset's columns/values when needed).
- **Knowledge check**: questions with blank answer spaces — never pre-filled.
- **Code challenge & mini project**: markdown cells list the tasks; the following Python cells are blank with the comment.

## What NOT to do

- Do not fill in answers to knowledge check questions — leave blank spaces
- Do not write Python code inside code cells — leave only the `# Write your Python code here` comment (the learner types it)
- Do not include executed cell outputs — show expected output as markdown code blocks instead
- Do not commit or modify `.opencode/`, `.omo/`, or `.ipynb_checkpoints/` — these are tool/runtime artifacts
- Do not create a README or other prose docs unless explicitly asked
