# 🏨 AI Hotel Review Generator (LLM Project)

## Problem
Manually writing realistic hotel reviews for testing, analysis, or demo purposes is time-consuming and inconsistent.  
The goal of this project is to **automatically generate high-quality, human-like hotel reviews** using a fine-tuned Large Language Model trained on real hotel review data.

This system is useful for:
- NLP experimentation
- Product demos
- Text generation research
- Synthetic data generation

---

## Architecture (LLM + Generation Pipeline)

1. **Data Ingestion**
   - Hotel review data loaded from Excel (`offerings.xlsx`)
   - Converted into HuggingFace `Dataset`
   - Split into training and test sets

2. **Tokenization**
   - GPT-2 tokenizer
   - Padding handled using EOS token
   - Truncation applied to max sequence length

3. **LLM Fine-Tuning**
   - Base model: `GPT-2`
   - Fine-tuned using causal language modeling
   - Optimized with:
     - Learning rate scheduling
     - Weight decay
     - Mixed precision (FP16)

4. **Text Generation**
   - Controlled generation using:
     - Temperature
     - Top-k and Top-p sampling
     - N-gram repetition control

5. **User Interface**
   - Gradio web app
   - Users provide a prompt and generation parameters
   - Model generates realistic hotel reviews in real time

---

## Tech Stack
Python | PyTorch | HuggingFace Transformers | GPT-2 | Datasets | Gradio | Pandas | NumPy | AWS-ready | NLP | LLMs

---

## Key Features
- Fine-tuned GPT-2 on domain-specific hotel review data
- Adjustable creativity and output length
- Real-time text generation via Gradio UI
- End-to-end pipeline from data → model → deployment

---

## How to Run
1. Install dependencies
   ```bash
   pip install transformers torch datasets gradio pandas numpy
