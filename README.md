# Reproducibility of "Facilitating Threat Modeling by Leveraging Large Language Models"

Reproduction of Elsharef, Zeng & Gu, *"Facilitating Threat Modeling by Leveraging Large Language Models,"* AISCC 2024 (NDSS Symposium).
Paper: https://www.ndss-symposium.org/wp-content/uploads/aiscc2024-16-paper.pdf

## Why this repo exists

No original source code was released for this paper — none is linked in the paper itself, its 30-item reference list, or the author's companion Master's thesis. This repo is a from-scratch reproduction of the paper's method, built for an internship assignment.

## What's being reproduced

The paper uses Retrieval-Augmented Generation (RAG) with an open-source LLM (Llama 2) to assist two parts of the threat-modeling process:
- **Task 1** — understanding a system from its design documents (MQ1: "what are we working on?")
- **Task 2** — identifying relevant known vulnerabilities via the NVD (MQ2: "what can go wrong?")

This reproduction builds both pipelines, then compares a **baseline LLM** (no retrieval) against a **RAG-enhanced** version on the same questions, to check whether RAG shows a measurable improvement — the same comparison the paper makes.

## Scope notes

- **Not a literal 1:1 rerun.** The paper never names its exact 12 input documents (only its 3 sources: IEEE Xplore, CISA, Intel TDX docs), so this is a *faithful method reproduction* using comparable substitute documents, not an identical replay.
- **Model**: Llama 2 (`meta-llama/Llama-2-7b-chat-hf`), matching the paper's model choice — not a newer/more capable model, by design.
- **Stack**: built on Hugging Face (`transformers`, `sentence-transformers`), with FAISS as an open, Hugging Face-native alternative to the paper's Pinecone vector database.
- The paper's companion Master's thesis numbers Task 1 and Task 2 in the opposite order from the published paper. This repo follows the **paper's** numbering.

## Status

Work in progress — environment setup (Colab + Llama 2, GPU-verified) complete. Pipeline build in progress.
