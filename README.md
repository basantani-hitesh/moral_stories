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
├── Robinson_Basantani_W266.pdf                             # Final paper
├── README.md                                               # This file
├── Layer_Pruning_roberta_base.ipynb                        # Pruning on RoBERTa-base
├── Layer_Pruning_roberta_large.ipynb                       # Pruning on RoBERTa-large
├── Moral_stories_DistilBERT.ipynb                          # Distillation experiments with DistilBERT
├── Moral_stories_Transformer_Action_(ATR)_Partial_Fine_Tuning.ipynb     # Partial fine-tuning on action-only input
├── Moral_stories_Transformer_BL_Action_(ATR).ipynb         # Baseline model on action-only input
├── Moral_stories_Transformer_BL_Action_+_Norm_(ATR).ipynb  # Baseline model with action + norm
├── Moral_stories_Transformer_BL_Action_+_Norm_+_Consequence_(ATR).ipynb  # Baseline model with full input
```

---

## 🚀 Quickstart

Clone the repository and explore the experiments directly through the provided Jupyter Notebooks:

- [Layer_Pruning_roberta_base.ipynb](./Layer_Pruning_roberta_base.ipynb)
- [Layer_Pruning_roberta_large.ipynb](./Layer_Pruning_roberta_large.ipynb)
- [Moral_stories_DistilBERT.ipynb](./Moral_stories_DistilBERT.ipynb)
- [Moral_stories_Transformer_Action_(ATR)_Partial_Fine_Tuning.ipynb](./Moral_stories_Transformer_Action_(ATR)_Partial_Fine_Tuning.ipynb)
- [Moral_stories_Transformer_BL_Action_(ATR).ipynb](./Moral_stories_Transformer_BL_Action_(ATR).ipynb)
- [Moral_stories_Transformer_BL_Action_+_Norm_(ATR).ipynb](./Moral_stories_Transformer_BL_Action_+_Norm_(ATR).ipynb)
- [Moral_stories_Transformer_BL_Action_+_Norm_+_Consequence_(ATR).ipynb](./Moral_stories_Transformer_BL_Action_+_Norm_+_Consequence_(ATR).ipynb)

Each notebook is self-contained and documents the setup, training, and evaluation procedures for the respective models.

---

## 👥 Authors

- **Hitesh Basantani** — [hitesh.basantani@ischool.berkeley.edu](mailto:hitesh.basantani@ischool.berkeley.edu)
- **Alice Robinson** — [alice.robinson@ischool.berkeley.edu](mailto:alice.robinson@ischool.berkeley.edu)

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

## 🔮 License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.

```text
MIT License
...
```

---

## 🔬 Future Work

- Training for multiple epochs for more stable evaluations.
- Careful hyperparameter tuning of distillation (temperature, loss weighting).
- Exploring quantization (e.g., float16 inference) for even lighter models.
- Systematic hybrid compression methods (pruning + LoRA + distillation).
