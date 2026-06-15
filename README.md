---
license: apache-2.0
base_model: Qwen/Qwen2.5-Coder-3B-Instruct
pipeline_tag: text-generation
library_name: transformers
tags:
- code-generation
- python
- qwen
- unsloth
- transformers
- coding-assistant
language:
- en
---

# VCoder

VCoder is a Python-focused coding assistant fine-tuned from Qwen2.5-Coder-3B-Instruct using LoRA and Unsloth.

The model was trained on 15,000 Python instruction-response examples from the Python Code Instructions 15K dataset and optimized for Python code generation, problem solving, debugging, and algorithm implementation.

## Model Details

| Attribute | Value |
|------------|---------|
| Base Model | Qwen2.5-Coder-3B-Instruct |
| Fine-Tuning Method | LoRA |
| Framework | Unsloth |
| Dataset | Python Code Instructions 15K |
| Training Samples | 15,000 |
| GPU | NVIDIA Tesla T4 |
| Quantized Format | GGUF Q8_0 |
| Primary Language | Python |

---

## Training Pipeline

Training was performed incrementally:

| Stage | Samples |
|---------|---------|
| Stage 1 | 0 - 5,000 |
| Stage 2 | 5,000 - 10,000 |
| Stage 3 | 10,000 - 15,000 |

The model was trained using parameter-efficient fine-tuning (LoRA), allowing adaptation of the base model while keeping computational requirements low.

---

## Benchmark Results

![Output](https://cdn-uploads.huggingface.co/production/uploads/6a297050d3837ea7b12cc42f/BV8FY6fJN7KQ43jcpC6hr.png)

### HumanEval Comparison

The model was evaluated against the original Qwen2.5-Coder-3B-Instruct on HumanEval coding tasks.

| Model | Pass@1 |
|---------|---------|
| Base Qwen2.5-Coder-3B | 61.0% |
| VCoder | 68.0% |

### Improvement

```text
+7.0% Pass@1 improvement
```

This demonstrates that the fine-tuned model performs better on Python coding tasks than the original base model.

---

## Example Usage

### Python

```python
prompt = """
### Instruction:
Write a Python function to reverse a string.

### Input:

### Response:
"""
```

### Example Output

```python
def reverse_string(text):
    return text[::-1]
```

---

## Supported Tasks

- Python Code Generation
- Algorithm Design
- Data Structures
- Debugging
- Code Refactoring
- Coding Interview Questions
- Competitive Programming
- Function Completion

---

## GGUF Usage

Compatible with:

- Ollama
- LM Studio
- llama.cpp

---

## Training Dataset

Dataset used:

Python Code Instructions 15K

The dataset contains instruction-response pairs focused on Python programming tasks including:

- Function generation
- Data manipulation
- Algorithms
- Debugging
- Problem solving

---

## Limitations

- Primarily optimized for Python.
- Benchmark performed on a subset of HumanEval tasks.
- May generate incorrect code for highly specialized domains.
- Should not be used as the sole source of production-critical code.

---

## Acknowledgements

- Qwen Team for Qwen2.5-Coder
- Unsloth for efficient fine-tuning
- Hugging Face
- OpenAI HumanEval Benchmark

---

## Citation

```bibtex
@misc{vcoder2026,
  title={VCoder: Python Code Generation Model},
  author={Varunesh V, Prawin R K, Sarguru N},
  year={2026},
  base_model={Qwen2.5-Coder-3B-Instruct}
}
```
Github : https://github.com/sargurun16
Mail : sarguru1609@gmail.com