RAG Proof of Concept (PoC): Final Project Summary
Overview
This project is a standalone Proof of Concept (PoC) exploring the implementation and evaluation of a Retrieval-Augmented Generation (RAG) system using GenAI technologies. The goal was to investigate the capabilities and limitations of RAG in supporting document-based question answering, specifically targeting use cases relevant to both engineering and marketing teams at a mid-sized tech company.

Key resources and constraints were provided at the outset, including:

A partially completed starter notebook

A defined business scenario and user personas

A fixed set of internal documents to be used as the retrieval corpus

75 gold-labeled QA pairs for evaluation

Strict constraints on allowed LLMs, embedding models, and documents

All experimentation and results stayed within the provided infrastructure: specified LLMs (e.g., Mistral, Cohere), embedding models, and a fixed vector store.

Goals
The main goals I pursued were:

Implementing a LangChain-based RAG pipeline using the approved LLMs and tools

Iteratively improving the architecture to mitigate known RAG failure points (see arXiv:2401.05856, p.3)

Defining custom evaluation metrics to quantitatively assess how well generated answers matched the provided gold answers

Experimenting with key hyperparameters such as chunk size, model temperature, and prompt templates (avoiding grid search)

Writing a comprehensive stakeholder-facing report outlining methodology, key findings, and limitations

All design choices prioritized reproducibility, interpretability, and practical relevance to the PoC context.

Business Scenario
The project simulates an internal PoC conducted at a tech company with 300 engineers and 40 marketers. The company is exploring GenAI-based tools to improve its document search and Q&A workflows. My role was to prototype and evaluate a RAG-based search assistant that serves both engineers and marketers, and to assess whether such a system should be scaled to production.

The reference documents included company-related literature and internal knowledge assets. I used these as the retrieval base for answering realistic questions posed by engineers and marketers.

Model Constraints
The following technical and procedural constraints were followed:

LLMs: Only Mistral and Cohere were used as the LLM component of LangChain chains. LLaMA 3.1/3.2, Qwen 2, and Gemma 2 were permitted in auxiliary roles.

Embeddings: Only the specified embedding models were used.

Documents: Only the provided corpus was indexed in the vector store—no external additions.

Evaluation Data: I evaluated my best 3 models/configs on all 75 gold QA pairs. Subset runs (if used) were justified with a documented sampling rationale.

Hyperparameters: Experimentation included prompt design, chunk sizing, temperature, and other tunable parameters. Grid search was deliberately avoided to foster intuition.

Cohere API Access
To run experiments using Cohere’s LLMs, I created a Cohere account and generated a trial API key. The key was stored securely and accessed in the Colab notebook via COHERE_API_KEY, never printed or exposed. Trial limits (e.g., 1,000 requests/month) were carefully monitored throughout development. Refer to Cohere rate limits for more detail.

Deliverables
The final deliverables submitted to the GitHub classroom repo include:

final_report.pdf: Four-page PoC report (see structure below)

notebook.ipynb: Fully executed notebook with code and outputs

answers.json: A file with answers to all validation queries

Additional scripts/configs as needed

Report Structure
The final report follows the provided ReportOutline.md and contains:

Executive Summary – One-paragraph overview of the key findings

Introduction – High-level system and scenario description

Key Findings – Five insights supported by analysis and examples

Methodology – Technical summary of the implementation and evaluation strategy

Results and Limitations – Includes results, risks, and open questions

Results Interpretation
Model Implementation: My RAG system successfully addressed the provided scenario using the allowed tools. I made minor architectural adaptations to address known RAG limitations.

Evaluation Strategy: I defined metrics tailored to the gold answers, including overlap-based and semantic similarity-based metrics.

Experimentation: I varied chunking, prompt structure, and retrieval settings, assessing the impact of each change using my custom metrics.

Specific Queries: I closely evaluated how my best models answered three hand-picked benchmark questions.

Additional Questions: I created five domain-relevant questions to further probe system performance.

Final Report: The report clearly communicates findings, risks, and recommendations for stakeholders considering a broader deployment.

Reflection
This was a challenging but rewarding project. I gained practical experience designing a usable, evaluatable RAG pipeline, and I developed a strong intuition for the trade-offs and failure modes that arise in production-like environments. I also learned to communicate results clearly to technical and non-technical stakeholders.

⚠️ Note: Open source LLMs used in this project are not fine-tuned for safety. Responses may reflect that.