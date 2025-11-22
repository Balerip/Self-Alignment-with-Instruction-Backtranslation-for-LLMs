This project explores self-alignment in large language models (LLMs) using the “Instruction Backtranslation” technique. The workflow covers efficient fine-tuning, self-augmentation, and data curation, applying state-of-the-art research for improving model instruction-following capabilities.


Project Overview
Implements: Self-alignment with instruction backtranslation, inspired by modern LLM research.

Fine-tunes: Llama-2 7B with LoRA/QLoRA adapters for parameter-efficient adaptation.

Generates & Curates: Instruction-response pairs via a backward model and programmatic scoring.

Deploys & Shares: Models and datasets pushed to HuggingFace for easy sharing and reuse.

Main Steps
1. Backward Model Training
Trained a model to generate instructions given outputs, based on the openassistant-guanaco dataset.

Leveraged LoRA/QLoRA for resource-efficient fine-tuning.

Published the resulting model to HuggingFace Hub.

2. Self-Augmentation
Used the backward model to generate new instructions for single-turn completions drawn from the LIMA dataset.

3. Self-Curation
Filtered and scored generated instructions/responses using few-shot prompting based on research guidelines.

Built a high-quality dataset by selecting top-scoring pairs.

Shared the curated dataset on HuggingFace.

4. Instruction Fine-Tuning
Fine-tuned Llama-2 7B on the curated, high-quality data for improved instruction-following.

Published the newly fine-tuned model.

Tech Stack
Python, HuggingFace Transformers, Datasets, and PEFT (LoRA/QLoRA)

PyTorch Lightning, Colab, and/or Kaggle for compute

HuggingFace Hub for model and data hosting

Usage
Setup: Clone repo & install dependencies.

Train: Run backward model fine-tuning script.

Augment: Use backward model to generate new instructions for target completions.

Curate: Apply programmatic scoring to filter best pairs.

Fine-Tune: Train Llama-2 7B on curated data.

Publish: Push artifacts to HuggingFace Hub.

For full code, see the Jupyter notebook.

Key References
Self-Alignment with Instruction Backtranslation (ArXiv 2023)

Example HuggingFace Model: backward model

Example Curated Dataset: high-quality instruction-response pairs

Fine-Tuned Model: Llama-2 7B fine-tuned for instruction-following

