# FoSE 2026 Replication Package

## Overview
This repository contains the replication package and supporting artifacts for the position paper submitted to the **International Conference on Software Engineering (ICSE 2026) - Future of Software Engineering (FoSE) Track**.

**Title:** "Be a Partner not Bystander in Software Engineering Practice": Bridging the Gaps between Academia and Industry

**Authors:** Mohammad Masudur Rahman and Mehil B. Shah (Dalhousie University)

This study investigates the software engineering (SE) community's concerns regarding research impact and relevance to industry practices. We analyzed 280 survey responses from the FoSE workshop using a mixed-method approach combining manual annotation and Large Language Model (LLM) analysis.

## Repository Structure
The repository consists of the following key components:

* **`AgreementAnalysis.ipynb`** – Inter-rater agreement computation (Cohen-Kappa) for the manual annotation phase.
* **`DataExplorer.ipynb`** – Exploratory data analysis and inspection of survey response metadata.
* **`RQ1.ipynb`** – Detailed analysis for Research Question 1 (Community Concerns).
* **`data/`** – Contains all datasets and qualitative artifacts:
    * **Annotated Responses:** Survey data manually tagged for relevance to "impact and practice".
    * **LLM Prompts:** The specific prompts (Prompt 1a, 1b, 2, 3) used for analysis.
    * **LLM Outputs:** Verbatim responses captured from the AI models for third-party reuse.

## LLM Configuration & Methodology
To ensure robustness and mitigate the stochastic nature of AI-generated text and hallucinations, this study employed a multi-model approach using three frontier Large Language Models.

### Models Used
The following specific model versions were used to summarize key concepts from the survey data:
1.  **Claude (Sonnet 4.5)**
2.  **ChatGPT (GPT 5)**
3.  **Gemini 3 Pro**

### Methodology
* **Prompt Strategy:** We carefully constructed specific prompts for each research question (RQ). To ensure consistency, the exact same prompt was applied across all models.
    * *Prompt 1a & 1b:* Focus on analyzing community concerns vs. contentment regarding research impact.
    * *Prompt 2:* Focus on identifying gaps between academic research and industry practices.
    * *Prompt 3:* Focus on identifying suggested calls to action and bridging strategies.
* **Execution:** The models were instructed to focus strictly on the provided survey data.
* **Access & Replication:**
    * **Raw Outputs:** Because these models are non-deterministic and subject to updates, the exact verbatim outputs generated during our study are preserved in the `data/` directory.
    * **Re-running Analysis:** Researchers wishing to replicate the generation step should access the specific model versions listed above via their respective provider APIs or web interfaces using the prompts found in `data/prompts.txt`.

## Replication Instructions
To reproduce the results reported in the paper:

1.  **Clone this repository** to your local machine.
2.  **Install Dependencies:** Ensure you have Python installed. The analysis relies on the following key libraries:
    * `pandas` (for data manipulation)
    * `openpyxl` (for reading Excel survey data)
3.  **Run Notebooks:** Open and execute the Jupyter notebooks in the following order:
    * `DataExplorer.ipynb` for initial data verification.
    * `AgreementAnalysis.ipynb` to verify the inter-rater agreement (Cohen-Kappa > 0.9).
    * `RQ1.ipynb` to generate the statistical evidence and figures found in Section 3.
4.  **Verify LLM Analysis:** Review the `data/` folder to inspect the raw LLM outputs generated against the summaries presented in the paper.
