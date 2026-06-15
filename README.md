# VCoder-Python-3B

# VCoder - Python Code Generation Model

VCoder is a Python-focused coding assistant created by fine-tuning Qwen2.5-Coder-3B-Instruct using LoRA and Unsloth.

The goal of this project was to improve Python code generation capabilities while keeping training efficient enough to run on a single NVIDIA Tesla T4 GPU.

---

## Project Overview

VCoder was trained on 15,000 Python instruction-response pairs from the Python Code Instructions dataset.

The model was fine-tuned incrementally in multiple stages and evaluated against the original Qwen2.5-Coder-3B-Instruct model using HumanEval coding benchmarks.

### Objectives

- Improve Python code generation
- Enhance algorithm implementation
- Improve coding interview problem solving
- Maintain lightweight deployment through LoRA
- Support local inference using Ollama and GGUF

---

## Tech Stack

| Component | Technology |
|------------|------------|
| Base Model | Qwen2.5-Coder-3B-Instruct |
| Fine-Tuning Framework | Unsloth |
| Training Method | LoRA |
| Dataset | Python Code Instructions 15K |
| Training Environment | Google Colab T4 |
| Evaluation | HumanEval |
| Deployment | Ollama |
| Quantization | GGUF Q8_0 |

---

## Dataset

Dataset contains:

- Python coding tasks
- Function generation
- Algorithm implementations
- Debugging exercises
- Code explanations
- Programming problem solving

Training Samples Used:

```text
15,000
```

---

## Training Process

Training was performed in three stages.

### Stage 1

```text
Rows 0 - 5,000
```

### Stage 2

```text
Rows 5,000 - 10,000
```

### Stage 3

```text
Rows 10,000 - 15,000
```

This incremental approach reduced memory pressure and allowed training on limited GPU resources.

---

## HumanEval Benchmark

VCoder was compared against the original base model using a 100-task HumanEval subset.

| Model | Pass@1 |
|---------|---------|
| Qwen2.5-Coder-3B-Instruct | 61% |
| VCoder | 68% |

### Improvement

```text
+7 Pass@1 Points
+11.5% Relative Improvement
```

### Benchmark Visualization

<img width="1470" height="956" alt="Output" src="https://github.com/user-attachments/assets/af976b28-d564-4d28-b87d-f245e0017857" />

---

## Example Usage

### Ollama

```text
FROM ./VCoder.Q8_0.gguf
```

Build:

```bash
ollama create vcoder -f Modelfile
```

Run:

```bash
ollama run vcoder
```

---

## Sample Prompt

```python
Write a Python function that returns the Fibonacci sequence up to n terms.
```

### Sample Output

```python
def fibonacci(n):
    sequence = []

    a, b = 0, 1

    for _ in range(n):
        sequence.append(a)
        a, b = b, a + b

    return sequence
```

---

## Challenges Faced

During development several challenges were encountered:

- CUDA out-of-memory issues on T4 GPUs
- LoRA checkpoint management
- Sequence length optimization
- HumanEval benchmarking setup
- GGUF model conversion
- Ollama deployment

These issues were resolved through iterative experimentation and optimization.

---

## Key Learnings

- Parameter-efficient fine-tuning using LoRA
- Efficient training with Unsloth
- Benchmarking LLMs using HumanEval
- Model quantization with GGUF
- Local LLM deployment using Ollama
- Hugging Face model publishing

---

## Future Improvements

- Train on the bigger dataset
- Evaluate on complete HumanEval benchmark
- Add MBPP benchmark evaluation
- Expand support beyond Python
- Experiment with larger models
- Build a web-based coding assistant

---

## Hugging Face

Model Repository:

https://huggingface.co/sargurun16/VCoder

---

## Authors

Varunesh V, Prawin R K, Sarguru N

---

## Acknowledgements

- Qwen Team
- Unsloth
- Hugging Face
- Ollama
- OpenAI HumanEval Benchmark

---

Mail : sarguru1609@gmail.com
