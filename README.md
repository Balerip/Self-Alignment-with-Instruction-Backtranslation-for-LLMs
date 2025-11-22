This project explores self-alignment techniques for large language models (LLMs) using the Instruction Backtranslation method. It implements an end-to-end workflow covering parameter-efficient fine-tuning, synthetic data generation, and programmatic data curation—based on recent research in model alignment.

Project Objectives

Build a backward model that generates instructions from responses.

Use it to self-augment a dataset with new instruction–response pairs.

Curate high-quality pairs using programmatic scoring and few-shot evaluation.

Fine-tune Llama-2 7B using LoRA/QLoRA for improved instruction following.

Publish models and datasets to HuggingFace for reproducibility and reuse.

Project Workflow
1. Backward Model Training

Trained a model to generate instructions from outputs using the openassistant-guanaco dataset.

Used LoRA/QLoRA for parameter-efficient fine-tuning.

Published the trained backward model on HuggingFace.

2. Self-Augmentation

Generated new instructions for target completions extracted from the LIMA dataset.

Created large-scale synthetic instruction–response pairs.

3. Self-Curation

Applied a programmatic scoring pipeline using few-shot prompting aligned with research best practices.

Filtered out low-quality or incoherent pairs.

Compiled a high-quality curated dataset, shared on HuggingFace.

4. Instruction Fine-Tuning

Fine-tuned Llama-2 7B using the curated dataset.

Achieved improved instruction-following behavior.

Published the final model to HuggingFace.

Tech Stack

Languages & Libraries: Python, HuggingFace Transformers, Datasets, PEFT (LoRA/QLoRA)

Training: PyTorch Lightning, Google Colab or Kaggle

Hosting: HuggingFace Hub for model & dataset storage

Usage
1. Setup
git clone <repo-url>
cd <repo-folder>
pip install -r requirements.txt

2. Train Backward Model
python train_backward_model.py

3. Generate Synthetic Instructions
python generate_instructions.py

4. Curate Data
python curate_dataset.py

5. Fine-Tune Llama-2 7B
python finetune_llama2.py

6. Publish to HuggingFace
huggingface-cli upload ...


Full implementation can be found in the included Jupyter notebooks.

Artifacts on HuggingFace

Backward Model: Instruction generator (response → instruction)

Curated Dataset: High-quality instruction–response pairs

Final Fine-Tuned Model: Llama-2 7B aligned for instruction following

Key Reference

Self-Alignment with Instruction Backtranslation (ArXiv, 2023)
