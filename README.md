# Lab 09: Understanding Neural Networks

<!-- STAT 486 · Fall 2026 -->

## Objective

Use TensorFlow Playground to explore how network depth, learning rate, activation functions, regularization, and network size affect binary classification. Record observations and explain what they suggest about neural network behavior.

## Before you begin

You need Git, a GitHub account, and [uv](https://docs.astral.sh/uv/getting-started/installation/) installed on your computer.

## Set up your submission repository

### 1. Create your private submission repository

On [`STAT-486-Fall-2026/lab-09`](https://github.com/STAT-486-Fall-2026/lab-09), select **Use this template** and then **Create a new repository**. Set the owner to the `STAT-486-Fall-2026-Labs` organization and name the repository exactly:

```text
lab-09-<netid>
```

For example, a student whose NetID is `jdoe42` must create `lab-09-jdoe42`. Use your institutional NetID even if it differs from your GitHub username. Make the repository **private**, then create it. Do not fork the starter repository.

### 2. Clone your repository

Copy the HTTPS URL for **your repository**, then run these commands. Replace the NetID placeholder.

```bash
git clone https://github.com/STAT-486-Fall-2026-Labs/lab-09-<netid>.git
cd lab-09-<netid>
```

### 3. Create your environment

The starter includes a lab-specific `pyproject.toml` and `.python-version`. From the repository directory, run:

```bash
uv sync
```

This creates your local `.venv`. Keep the supplied `pyproject.toml` unchanged unless the lab directions explicitly say otherwise. This browser-based activity has no Python package dependencies; the environment files keep the repository setup consistent across labs.

### 4. Complete the lab

Open `work.ipynb` in your preferred editor. The notebook contains all prompts and response spaces. Use the linked TensorFlow Playground in a web browser; no dataset or local model training is required. Save your written responses in the provided Markdown cells. Include clear observations for each experiment and label any screenshots or plots you choose to include.

### 5. Commit and push your work

```bash
git add work.ipynb
git commit -m "Complete Lab 09"
git push
```

## Submission

Paste the root URL of your repository into the Canvas Lab 09 submission textbox:

```text
https://github.com/STAT-486-Fall-2026-Labs/lab-09-<netid>
```

Do not open a pull request and do not upload the notebook file to Canvas.
