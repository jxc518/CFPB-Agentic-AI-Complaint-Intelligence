# CFPB Agentic AI

### Complaint Intelligence · Next Best Action · Voice AI

**An Independent Proof of Concept for AI-Assisted Consumer Complaint Intelligence**

An Agentic AI project exploring how financial institutions can transform unstructured consumer complaints into structured customer journey insights, generate governed **Next Best Action (NBA)** recommendations, and improve speech recognition quality through risk-based error detection and recovery.

> **Project scope:** Phase 1 covers complaint intelligence and experimental NBA generation. Phase 2 covers STT quality benchmarking and recovery. End-to-end Voice-to-NBA integration is **planned**, not implemented.


## Project Presentation

📄 **[View Full Project Presentation — CFPB Phase 1 & Phase 2](https://github.com/jxc518/CFPB-Agentic-AI-Complaint-Intelligence/blob/main/CFPB_Phase1_Phase2_Voice_Integrated_Process_Discovery_20261115.pdf)**

The accompanying PowerPoint presentation documents:

- Phase 1 and Phase 2 architecture diagrams
- Teacher–Student knowledge distillation and QLoRA training results
- Real complaint narratives and generated NBA comparisons
- STT benchmarking and recovery experiments
- Seven-model ML comparison and technical evidence

The presentation includes Teacher–Student Distillation, Multi-Agent NBA architecture, QLoRA training results, real complaint examples, STT quality evaluation, and recovery experiments.

---

## Project Overview

| Phase | Focus | Key Capabilities |
|:--|:--|:--|
| **Phase 1** | Complaint Intelligence & NBA | Teacher–Student Distillation, QLoRA, Multi-Agent Workflows, Governance |
| **Phase 2** | Voice Intelligence & STT Recovery | Speech Recognition, ML Risk Scoring, Error Recovery |

**Business objective:** Support consistent complaint understanding, identify customer journey failures, and produce evidence-grounded candidate actions for complaint resolution.

## Phase 1 — Complaint Intelligence & Next Best Action

### Architecture & Methodology

- **Teacher Model:** GPT-4.1-mini for structured complaint understanding and NBA generation.
- **Student Model:** Qwen2.5-1.5B fine-tuned with 4-bit QLoRA.
- **Knowledge Distillation:** Teacher-generated structured labels used to prepare student training data.
- **Training Dataset:** 838 training examples and 93 internal validation examples.
- **Evaluation:** Frozen Teacher–Student comparison on 200 CFPB complaints.
- **Agentic Workflow:** Three distinct responsibilities:
  - Complaint Understanding Agent
  - Historical Resolution Agent
  - Governance Review Agent
- **Governance:** Structured-output validation, automated guardrails, and complaint-specific qualitative NBA review.

### Phase 1 — Experimental Results

| Metric | Result |
|:--|--:|
| Training Examples | **838** |
| Internal Validation Examples | **93** |
| QLoRA Training Steps | **210** |
| Trainable Parameters | **1.18%** |
| Teacher–Student Benchmark | **200 complaints** |
| Student JSON Valid Rate | **95.0%** |
| Student Automated Governance Pass Rate | **72.5%** |

**Engineering finding:** Automated governance compliance and business recommendation quality are different evaluation dimensions. Passing structural checks does not guarantee the best resolution for a complaint.

## Phase 2 — Voice Intelligence & STT Quality Recovery

### Architecture & Methodology

- Generated synthetic complaint audio from CFPB narratives.
- Compared **Whisper-1** and **GPT-4o-mini-transcribe**.
- Evaluated transcription quality using **Word Error Rate (WER)** and **Character Error Rate (CER)**.
- Compared seven classifiers for severe transcription error detection:
  - Logistic Regression, Linear SVC, AdaBoost, Gradient Boosting
  - XGBoost, LightGBM, CatBoost
- Tested three recovery approaches:
  1. GPT-4o transcription escalation
  2. Voice Activity Detection (VAD) / audio chunking
  3. Audio cleanup and noise reduction

### Phase 2 — Experimental Results

| Metric | Result |
|:--|--:|
| ML Classifiers Compared | **7** |
| Best Observed Test Average Precision | **0.6164** |
| Exploratory Severe-Error Recovery Sample | **18 audio files** |
| GPT-4o Escalation — Mean WER | 1.3052 |
| VAD / Chunking — Mean WER | 1.0488 |
| Audio Cleanup — Mean WER | **0.3038** |

**Engineering finding:** Audio cleanup had the lowest observed mean WER among the three recovery methods in this exploratory 18-sample experiment. These results do not establish general production performance.

**Integration status:** Downstream Voice-to-NBA integration is **planned**, not yet implemented end-to-end.

## Technology Stack

| Category | Technologies |
|:--|:--|
| Programming | Python, Pandas |
| LLMs | GPT-4.1-mini, Qwen2.5-1.5B |
| Model Training | PyTorch, Hugging Face Transformers, PEFT, QLoRA |
| Agentic AI | LangGraph, Multi-Agent Workflows |
| Speech AI | Whisper-1, GPT-4o-mini-transcribe |
| Machine Learning | scikit-learn, XGBoost, LightGBM, CatBoost |
| Evaluation | WER, CER, Precision, Recall, F1, Average Precision |
| Development | Google Colab, Jupyter Notebook |

## Responsible AI & Governance

This independent educational proof of concept uses public CFPB complaint data.

- Model-generated recommendations are experimental, **not** actual financial institution decisions.
- Automated governance checks do not establish regulatory compliance or guarantee business correctness.
- Human review is needed to assess evidence grounding, actionability, and business relevance.
- Public repository materials should exclude secrets, credentials, and sensitive or insufficiently redacted complaint information.

## Project Status

| Component | Status |
|:--|:--|
| Teacher–Student Distillation | Completed for documented PoC |
| QLoRA Student Training | Completed |
| Validation200 Benchmark | Completed |
| Complaint NBA Evaluation | Automated evaluation completed; qualitative case review performed |
| STT Benchmarking | Completed for documented experiments |
| Seven-Model ML Comparison | Completed |
| Audio Recovery Experiment | Completed — exploratory sample |
| End-to-End Voice-to-NBA Integration | **Planned** |

---

**Project purpose:** Demonstrate practical integration of Generative AI, Agentic AI, model distillation, machine learning evaluation, and speech intelligence for financial-services complaint management.

*Independent educational project. Not affiliated with or endorsed by the Consumer Financial Protection Bureau (CFPB).*
