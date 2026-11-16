CFPB Agentic AI — Complaint Intelligence & Voice AI

Project Overview

An independent proof-of-concept exploring AI-assisted consumer complaint intelligence, governed Next Best Action (NBA) recommendations, and speech recognition quality recovery using public CFPB complaint data.

Phase 1 — Complaint Intelligence & Next Best Action

GPT-4.1-mini Teacher Model for structured complaint understanding and NBA generation.

Qwen2.5-1.5B Student Model with 4-bit QLoRA fine-tuning.

838 training examples and 93 internal validation examples.

Frozen Teacher–Student evaluation on 200 CFPB complaints.

Three-agent architecture for complaint understanding, historical resolution analysis, and governance review.

Automated governance checks and qualitative analysis of real complaint-specific NBA recommendations.

Phase 2 — Voice Intelligence & STT Quality Recovery

Synthetic complaint audio generated from CFPB narratives.

Speech-to-Text evaluation using Whisper-1 and GPT-4o-mini-transcribe.

Seven machine learning classifiers for severe transcription error detection.

Evaluation using Word Error Rate (WER), Character Error Rate (CER), and Average Precision.

Three experimental recovery methods: model escalation, audio chunking, and audio cleanup.

Downstream Voice-to-NBA integration is planned, not yet implemented.

Selected Experimental Results

Metric

Result

Student QLoRA Training

838 examples

Internal Validation

93 examples

Teacher–Student Benchmark

200 complaints

Student JSON Valid Rate

95%

Student Automated Governance Pass Rate

72.5%

Best Observed STT Risk Model Test AP

0.6164

Exploratory Audio Recovery Evaluation

18 severe-error samples

Lowest Observed Recovery Mean WER

0.3038

These results are from proof-of-concept experiments and should not be interpreted as production-level performance.

Technologies

Python · PyTorch · Hugging Face Transformers · PEFT / QLoRA · Qwen2.5 · OpenAI API · LangGraph · scikit-learn · XGBoost · LightGBM · CatBoost · Google Colab

Project Presentation

The PowerPoint presentation in this repository provides architecture diagrams, experimental results, real complaint NBA examples, and technical appendices.

Data and Responsible AI

The project uses CFPB public complaint data for independent educational research. Generated recommendations are experimental and are not actual financial institution decisions. Automated governance validation does not replace human review or establish regulatory compliance.

Project Status

Phase 1: Model development and evaluation completed for the documented PoC scope.

Phase 2: STT benchmarking and exploratory recovery experiments completed; end-to-end Voice-to-NBA integration remains planned.
