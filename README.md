# Knowledge Distillation for Efficient Text Generation

## Overview

This project uses **Hybrid Knowledge Distillation** to improve the text generation performance of a smaller GPT-2 model while reducing computational requirements.

**GPT-2 Large** is used as the Teacher model and **GPT-2 Small** as the Student model. The student learns from both ground-truth text and the teacher's soft probability distributions.

The approach combines **Cross-Entropy Loss** and **Kullback-Leibler (KL) Divergence**, with temperature scaling to improve knowledge transfer.

The model is trained using **WikiText-103** and refined using approximately **50,000 OpenWebText samples** to improve generalization, fluency, and contextual understanding.

## Objectives

- Improve GPT-2 Small text generation quality.
- Transfer knowledge from GPT-2 Large to GPT-2 Small.
- Reduce model size and computational requirements.
- Combine ground-truth learning with teacher-guided learning.
- Improve generalization and generation quality.

## Methodology

1. Prepare and tokenize the datasets using the GPT-2 tokenizer.
2. Use GPT-2 Large as a frozen Teacher model.
3. Train GPT-2 Small as the Student model.
4. Generate teacher soft targets using temperature scaling.
5. Combine Cross-Entropy Loss with KL-Divergence.
6. Optimize the student using AdamW, learning-rate scheduling, gradient accumulation, and gradient clipping.
7. Evaluate using loss, perplexity, and generated text quality.

## Datasets

### WikiText-103
Used for the main language-model training process and provides structured, high-quality language data.

### OpenWebText
A subset of approximately 50,000 samples is used for refinement to improve generalization, fluency, and contextual understanding.

## Results

| Model | Parameters | Perplexity |
|---|---:|---:|
| GPT-2 Large (Teacher) | 774M | 33.29 |
| GPT-2 Small (Baseline) | 117M | 52.21 |
| Distilled GPT-2 Small | 117M | **36.20** |

### Key Achievements

- Improved perplexity from **52.21 to 36.20**.
- Closed approximately **84.6%** of the performance gap between the baseline and teacher.
- Achieved approximately **6.6× model compression** compared with GPT-2 Large.
- Produced more coherent and contextually relevant text while maintaining a smaller model size.

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- GPT-2
- Natural Language Processing (NLP)
- Deep Learning
- Knowledge Distillation
- NumPy
- Pandas
- Matplotlib
- Jupyter Notebook

## Text Generation

The project supports text generation using the Teacher, Distilled Student, and Vanilla GPT-2 Small models.

Generation settings used in the project include:

- Temperature: `0.80`
- Top-K: `50`
- Top-P: `0.92`
- Repetition Penalty: `1.3`
- Maximum New Tokens: `120`

## Project Structure

```text
mini_project/
├── README.md
├── kdproject1.ipynb
├── app.py
├── requirements.txt
└── model/
```

## Future Scope

- Use larger teacher models.
- Explore advanced distillation techniques.
- Apply domain-specific fine-tuning.
- Add real-time text-generation applications.
- Combine knowledge distillation with pruning and quantization.
- Explore multilingual text generation.

## Project Team

- G. Keerthana
- S.M.D. Anas
- Ch. Akhila
- U. Niharika

**Institution:** RGUKT Nuzvid
