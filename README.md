# 🚀 Llama-3.1 GRPO Reasoning Model

This project focuses on fine-tuning the **Llama-3.1** model using the **GRPO (Group Relative Policy Optimization)** algorithm. The goal is to move beyond simple pattern matching and teach the model to 'think' using reasoning tags (`<math>` and `<answer>`).

### 🛠️ Tech Stack
- **Base Model:** Llama-3.1 (8B)
- **Framework:** Unsloth / Hugging Face TRL
- **Algorithm:** GRPO (Reinforcement Learning)
- **Environment:** AMD AI Cloud (Jupyter Lab)

### 📈 Current Progress
- **Status:** Training Interrupted at **Step 250/250**
- **LoRA Config:** Rank 32, Alpha 32
- **Reasoning Accuracy:** Successfully generating multi-step logic for mathematical queries (e.g., Calculating Pi).

### 🎯 Reward Functions Used
To guide the model's reasoning, we implemented:
1. **XML Count Reward:** Ensures proper tag usage.
2. **Format Reward:** Checks for structural integrity.
3. **Correctness Reward:** Validates the final mathematical answer.

### ⚠️ Note on Checkpoints
The full GGUF conversion was interrupted due to kernel limitations. This repo currently serves as a backup for the **LoRA Adapters** and the **Training Logic**.
