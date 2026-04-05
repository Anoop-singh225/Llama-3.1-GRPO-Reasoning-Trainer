# 🚀 NextMatrix-GRPO: Advanced Reasoning Model

[![Framework: Unsloth](https://img.shields.io/badge/Framework-Unsloth-blueviolet)](https://github.com/unslothai/unsloth)
[![Model: Llama-3.1-8B](https://img.shields.io/badge/Model-Llama--3.1--8B-blue)](https://huggingface.co/meta-llama/Llama-3.1-8B)
[![Architecture: AMD-ROCm](https://img.shields.io/badge/Architecture-AMD--ROCm-orange)](https://www.amd.com/en/graphics/servers-solutions-rocm)

This repository contains the fine-tuning pipeline for **Llama-3.1-8B** using **Group Relative Policy Optimization (GRPO)**. Developed under the **NextMatrix Tech** ecosystem, this project focuses on enhancing cognitive reasoning via structured "Chain-of-Thought" processing using `<reasoning>` and `<answer>` tags.

---

### 🛠️ Technical Stack & Environment
* **Core Model:** Meta Llama-3.1 (8B Parameters)
* **Algorithm:** GRPO (Reinforcement Learning via TRL)
* **Optimization:** Unsloth (ROCm Optimized) with 4-bit Quantization
* **Hardware:** AMD AI Cloud (Jupyter Lab Environment)

---

### 📈 Training Milestones
* **Status:** Successfully reached **250/250 Steps** (Full Completion).
* **Configuration:** LoRA Adapters (Rank: 32, Alpha: 32).
* **Objective:** Improving mathematical logic and structured response formatting.

---

### 🎯 Reward Logic Architecture
To enforce logical integrity, we utilized a multi-objective reward system:
1. **XML Structure Reward:** Validates the presence and nesting of reasoning tags.
2. **Format Consistency Reward:** Ensures the output adheres to the predefined structural template.
3. **Logical Correctness Reward:** Mathematically verifies the final output against ground-truth values.

---

### ⚙️ Installation & Setup (AMD ROCm)
To reproduce the environment on AMD hardware, use the following commands:

#### 1. Core Dependency Setup
```bash
# Install ROCm-optimized Unsloth from source
!git clone [https://github.com/billishyahao/unsloth.git](https://github.com/billishyahao/unsloth.git) && cd unsloth && git checkout billhe/rocm && pip install .

# Install Unsloth Zoo utility
!pip install unsloth_zoo==2025.3.17

# Build ROCm Bitsandbytes from source for AMD Backend
!git clone --recurse [https://github.com/ROCm/bitsandbytes](https://github.com/ROCm/bitsandbytes) && cd bitsandbytes && git checkout rocm_enabled_multi_backend && pip install -r requirements-dev.txt && cmake -DCOMPUTE_BACKEND=hip -S . && make -j && pip install .
