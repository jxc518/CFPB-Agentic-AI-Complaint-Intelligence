CFPB Agentic AI

Complaint Intelligence · Next Best Action · Voice AI

An End-to-End Proof-of-Concept for AI-Assisted Consumer Complaint Intelligence

An independent Agentic AI project exploring how financial institutions can transform unstructured consumer complaints into structured customer journey insights, generate governed Next Best Action (NBA) recommendations, and improve speech recognition quality through risk-based error detection and recovery.

Project Overview

This project consists of two complementary phases:

Phase

Focus

Key Capabilities

Phase 1

Complaint Intelligence & NBA

Teacher–Student Distillation, QLoRA, Multi-Agent Workflows, Governance

Phase 2

Voice Intelligence & STT Recovery

Speech Recognition, ML Risk Scoring, Error Recovery

Business Objective: Support more consistent complaint understanding, identify potential customer journey failures, and generate evidence-grounded candidate actions for complaint resolution.

Phase 1 — Complaint Intelligence & Next Best Action

Architecture & Methodology

Teacher Model: GPT-4.1-mini for structured complaint understanding and NBA generation.

Student Model: Qwen2.5-1.5B fine-tuned using 4-bit QLoRA.

Knowledge Distillation: Teacher-generated structured labels used to prepare student training data.

Training Dataset: 838 examples for training and 93 for internal validation.

Evaluation: Frozen Teacher–Student comparison on 200 CFPB complaints.

Agentic Workflow: Three agents with distinct responsibilities:

Complaint Understanding Agent

Historical Resolution Agent

Governance Review Agent

Governance: Structured-output validation, automated guardrails, and complaint-specific NBA review.

Phase 1 — Key Experimental Results

Metric

Result

Training Examples

838

Internal Validation Examples

93

QLoRA Training Steps

210

Trainable Parameters

1.18%

Teacher–Student Benchmark

200 complaints

Student JSON Valid Rate

95.0%

Student Automated Governance Pass Rate

72.5%

Key Finding: Automated governance compliance and business recommendation quality are different evaluation dimensions. A recommendation can pass structural checks without necessarily being the best resolution for the complaint.

Phase 2 — Voice Intelligence & STT Quality Recovery

Architecture & Methodology

Generated synthetic complaint audio from CFPB narratives.

Compared Whisper-1 and GPT-4o-mini-transcribe.

Evaluated transcription quality using Word Error Rate (WER) and Character Error Rate (CER).

Trained and compared seven machine learning classifiers for severe transcription error detection:

Logistic Regression

Linear SVC

AdaBoost

Gradient Boosting

XGBoost

LightGBM

CatBoost

Evaluated three recovery approaches:

GPT-4o transcription escalation

Voice Activity Detection / audio chunking

Audio cleanup and noise reduction

Phase 2 — Key Experimental Results

Metric

Result

ML Classifiers Compared

7

Best Observed Test Average Precision

0.6164

Severe-Error Recovery Sample

18 audio files

GPT-4o Escalation — Mean WER

1.3052

VAD / Chunking — Mean WER

1.0488

Audio Cleanup — Mean WER

0.3038

Key Finding: Audio cleanup achieved the lowest observed mean WER among the three recovery methods in this exploratory 18-sample experiment.

Integration Status: Downstream Voice-to-NBA integration is planned and has not yet been implemented end-to-end.

Technology Stack

Category

Technologies

Programming

Python, Pandas

LLMs

GPT-4.1-mini, Qwen2.5-1.5B

Model Training

PyTorch, Hugging Face Transformers, PEFT, QLoRA

Agentic AI

LangGraph, Multi-Agent Workflows

Speech AI

Whisper-1, GPT-4o-mini-transcribe

Machine Learning

scikit-learn, XGBoost, LightGBM, CatBoost

Evaluation

WER, CER, Precision, Recall, F1, Average Precision

Development

Google Colab, Jupyter Notebook

Project Presentation

The project PowerPoint presentation includes:

Phase 1 and Phase 2 architecture diagrams

Teacher–Student knowledge distillation methodology

QLoRA training results and loss curves

Real CFPB complaint narratives and NBA recommendations

Speech recognition benchmarking and recovery experiments

Seven-model machine learning comparison

Technical implementation evidence

The presentation is available in this repository.

Responsible AI & Governance

This independent educational proof-of-concept uses public CFPB complaint data.

Model-generated NBA recommendations are experimental and are not actual financial institution decisions.

Automated governance checks do not establish regulatory compliance or guarantee business correctness.

Human evaluation is needed to assess evidence grounding, actionability, and business relevance.

Experimental metrics should not be interpreted as production-level performance.

Project Status

Component

Status

Teacher–Student Distillation

Completed for documented PoC

QLoRA Student Training

Completed

Validation200 Benchmark

Completed

Complaint NBA Evaluation

Automated evaluation completed; qualitative case review performed

STT Benchmarking

Completed for documented experiments

Seven-Model ML Comparison

Completed

Audio Recovery Experiment

Completed — exploratory sample

End-to-End Voice-to-NBA Integration

Planned

Project Purpose

Demonstrate practical integration of Generative AI, Agentic AI, model distillation, machine learning evaluation, and speech intelligence for financial-services complaint management.

Independent educational project. Not affiliated with or endorsed by the Consumer Financial Protection Bureau (CFPB).
