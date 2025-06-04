# Contributing Guidelines

> Thank you for taking the time to improve **Russian Grammar Error Correction (25 k)**! We welcome issues, pull requests, and suggestions.

---

## 📋 Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [How to Contribute](#how-to-contribute)

   * [Bug Reports](#bug-reports)
   * [Feature Requests](#feature-requests)
   * [Adding New Data](#adding-new-data)
   * [Documentation Improvements](#documentation-improvements)
4. [Style Guide](#style-guide)
5. [Pull‑Request Checklist](#pull-request-checklist)
6. [Maintainers](#maintainers)

---

## Code of Conduct

This project adheres to the **[Contributor Covenant](https://www.contributor-covenant.org/version/2/1/code_of_conduct/)**. By participating, you are expected to uphold this code. Please report unacceptable behavior to [your-email@example.com](mailto:your-email@example.com).

---

## Getting Started

1. **Fork** the repository and **clone** it locally:

   ```bash
   git clone https://github.com/<your-username>/russian-gec-dataset.git
   cd russian-gec-dataset
   ```
2. Install development dependencies:

   ```bash
   python -m venv .venv && source .venv/bin/activate
   pip install -r requirements-dev.txt
   ```
3. Install the pre‑commit hooks (formatting & linting):

   ```bash
   pre-commit install
   ```

---

## How to Contribute

### Bug Reports

* Search existing issues first—your problem may already be reported or solved.
* Open a new issue with **clear steps to reproduce**, the expected behavior, and screenshots/logs if relevant.

### Feature Requests

* Explain **why** the feature is useful.
* Outline a minimal implementation plan if you have one.

### Adding New Data

We love fresh sentence pairs! Please follow these rules:

| Rule                                                 | Why                                 |
| ---------------------------------------------------- | ----------------------------------- |
| Provide both **`incorrect`** and **`correct`** text. | Alignment is required for training. |
| Russian only; no mixed languages.                    | Keeps the corpus focused.           |
| Avoid personal data, slurs, or copyrighted material. | Legal & ethical compliance.         |
| Keep sentences ≤ 30 tokens when possible.            | Model‑friendly length.              |
| Use UTF‑8 encoding and **no extra columns**.         | Consistency.                        |

**Workflow:**

1. Append your rows to `russian_gec_dataset.csv` *without altering existing lines*.
2. Run `make validate` to ensure:

   * CSV is well‑formed.
   * No duplicate pairs (exact match).
   * Both columns are non‑empty and differ.
3. Commit with a message like:

   ```
   chore(data): add 250 learner sentences about travel
   ```

### Documentation Improvements

Typos, clarifications, or new examples—feel free to open a PR that edits `README.md`, `CONTRIBUTING.md`, or notebooks.

---

## Style Guide

* **Markdown** files: wrap lines at 120 chars, use descriptive headers (h2, h3).
* **Commit messages**: follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) (`fix:`, `feat:`, `docs:`, `chore:`).
* **Python**: auto‑formatted with **black**; linted with **ruff**.

---

## Pull‑Request Checklist

Before you submit a PR, make sure:

* [ ] The branch is up to date with `main`.
* [ ] `pre-commit run --all-files` passes with no changes.
* [ ] `make validate` passes (for data changes).
* [ ] Added/updated **tests** if you changed tooling.
* [ ] Updated **README** or docs if necessary.
* [ ] PR description clearly summarizes *what* and *why*.

---

## Maintainers

| GitHub                                   | Role            |
| ---------------------------------------- | --------------- |
| [@dreuxx26](https://github.com/dreuxx26) | Lead maintainer |
| *TBD*                                    | Reviewer        |

Feel free to reach out via GitHub issues or discussions. Happy contributing! 🙌

