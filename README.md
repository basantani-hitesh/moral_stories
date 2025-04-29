
# Efficient Moral Judgment: Lightweight Classifier for Ethical Decision-Making

This repository contains all the code, models, and experiments used in the paper:

**"Efficient Moral Judgment: Building a Lightweight Classifier for Ethical Decision-Making"**  
by **Hitesh Basantani** and **Alice Robinson**.

📄 [Link to the paper (PDF)](./Robinson_Basantani_W266.pdf)

---

## 📚 Project Overview

Understanding and classifying moral norms is crucial for creating AI systems that behave in a socially responsible and contextually appropriate manner.  
In this project, we develop resource-efficient models that retain strong moral reasoning capabilities while significantly reducing:

- Training time
- Inference time
- Model size

We leverage the **Moral Stories** dataset and techniques like:

- **Parameter-Efficient Fine-Tuning (PEFT)** using **LoRA**
- **Layer Pruning**
- **Knowledge Distillation**

Our models achieve up to **84% reduction in training time**, **85% reduction in inference time**, and **77% reduction in model size**, with less than **3% accuracy loss** compared to the full fine-tuned baseline.

---

## 🧪 Methods

- **Baseline Fine-Tuning**: Full fine-tuning of RoBERTa-large on the Moral Stories dataset.
- **LoRA PEFT**: Fine-tuning only small injected matrices inside Transformer attention heads.
- **Layer Pruning**: Removing deeper (less impactful) layers to speed up inference without hurting performance.
- **Knowledge Distillation**: Training smaller "student" models to mimic larger "teacher" models.

### Key Models Explored:
- RoBERTa-large
- RoBERTa-base
- DistilBERT

---

## 📈 Results

- **Partial Fine-Tuning**: 50%+ training time reduction with minimal accuracy drop.
- **LoRA**: 44% training time reduction while maintaining 80%+ accuracy.
- **Layer Pruning**: Pruned models achieved 25%+ inference time savings without significant performance loss until heavy pruning.
- **Distillation**: Significant compression possible, but aggressive distillation from already-small models leads to performance loss.

📊 Detailed results and comparison charts are available in the paper ([Appendix Sections](./Robinson_Basantani_W266.pdf)).

---

## 📂 Repo Structure

```bash
TBD
```



---

## 📁 Dataset

- **Moral Stories Dataset**: [HuggingFace Link](https://huggingface.co/datasets/demelin/moral_stories)
- Provides structured narratives with normative and divergent actions tied to societal norms.
- Fine-tuned and evaluated models were trained primarily using the **action-only** setting (i.e., without consequences).

---

## 🚀 Quickstart

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/moral-norm-classifier.git
   cd moral-norm-classifier
   ```

TBD
   ```

---

## 👥 Authors

- **Hitesh Basantani** – [hitesh.basantani@ischool.berkeley.edu](mailto:hitesh.basantani@ischool.berkeley.edu)
- **Alice Robinson** – [alice.robinson@ischool.berkeley.edu](mailto:alice.robinson@ischool.berkeley.edu)

---

## 📝 Citation

If you use this work, please cite it as:

```bibtex
@misc{basantani2025efficientmoral,
  title={Efficient Moral Judgment: Building a Lightweight Classifier for Ethical Decision-Making},
  author={Hitesh Basantani and Alice Robinson},
  year={2025},
  note={Available at GitHub repository}
}
```

---

## 🔒 License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.

```text
MIT License
...
```
