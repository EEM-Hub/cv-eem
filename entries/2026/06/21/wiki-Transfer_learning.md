---
source: sources/wiki-Transfer_learning.md
source_url: https://en.wikipedia.org/wiki/Transfer_learning
---

## Transfer Learning in Machine Learning

Transfer learning (TL) is a machine learning technique where knowledge learned from one task (the **source**) is reused to improve performance on a different but related task (the **target**). For example, a model trained to recognize cars can transfer learned features to help recognize trucks. The technique addresses the practical problem that training data for a target task may be scarce, while abundant data exists for a related source task. Transfer learning is related to cost-sensitive machine learning and multi-objective optimization due to its use of multiple objective functions.

## Key Concepts

- **Domain (D)**: Consists of a feature space X and a marginal probability distribution P(X) over the data.
- **Task (T)**: Consists of a label space Y and a predictive function f: X → Y, learned from training pairs {x_i, y_i}.
- **Source domain/task (D_S, T_S)**: The domain and task where knowledge originates (typically data-rich).
- **Target domain/task (D_T, T_T)**: The domain and task where knowledge is applied (typically data-scarce).
- Transfer learning applies when either D_S ≠ D_T (different domains) or T_S ≠ T_T (different tasks), and the goal is to improve the target predictive function f_T using source knowledge.
- **Positive transfer**: When source knowledge improves target performance.
- **Negative transfer**: When source knowledge hurts target performance (demonstrated as early as 1981).
- Pre-training can sometimes hurt accuracy; self-training may be preferable in certain settings (Zoph et al., 2020).
- Transfer learning improves both initial performance (vs. random weight initialization) and final asymptotic performance after training.
- End-users of pre-trained models can modify fully-connected layer structure to improve performance on their specific task.

## Commands and Syntax

No CLI commands or configuration syntax — this is a conceptual/theoretical topic. The primary "procedure" is:

1. Train a model on a source task with abundant labeled data.
2. Transfer learned representations (weights, features, or knowledge) to a target task.
3. Fine-tune or adapt the transferred model on target task data.

## Relationships

- **Domain Adaptation**: A subfield/sibling of transfer learning focused specifically on bridging domain differences while the task stays the same.
- **Multi-task Learning**: Closely related; learns multiple tasks simultaneously rather than sequentially transferring. Co-evolved with transfer learning since the late 1990s.
- **Zero-shot Learning**: An extreme case where no target task training data is available; relies entirely on transferred knowledge.
- **Feature Learning / Representation Learning**: Transfer learning often works by reusing learned feature representations (e.g., convolutional filters from ImageNet models).
- **Fine-tuning**: The most common mechanism for applying transfer learning with deep neural networks — initialize with pre-trained weights, then continue training on target data.
- **Pre-training / Self-supervised Learning**: Often the source of transferred knowledge in modern deep learning (e.g., BERT, GPT, ImageNet-pretrained CNNs).
- **Curriculum Learning**: Related strategy of ordering training examples; transfer learning can be viewed as a form of curriculum where the source task precedes the target.

## Exam-Relevant Points

- Transfer learning requires that either the source and target **domains** differ or the source and target **tasks** differ (or both).
- First paper on transfer learning in neural networks: **Bozinovski and Fulgosi, 1976**.
- Andrew Ng (NIPS 2016) predicted transfer learning would be the next major driver of ML commercial success after supervised learning.
- Transfer learning has been applied across diverse domains: image classification, text classification, medical imaging, spam filtering, digit recognition, game playing, cancer subtype discovery, EMG/EEG signal classification.
- Cross-domain transfer between EMG (muscle) and EEG (brain) signals is possible due to similar physical natures — works bidirectionally.
- **Negative transfer** is a real risk — transferring from a poorly matched source can degrade target performance.
- Zoph et al. (2020) showed pre-training can hurt accuracy in some settings, suggesting self-training as an alternative.
- Key reference works: Pan & Yang survey (2009/2010), Zhuang et al. comprehensive survey (2019), Thrun & Pratt "Learning to Learn" book (1998).
- Transfer learning algorithms exist for Markov logic networks and Bayesian networks, not just neural networks.
- Modifying the structure of fully-connected layers in a pre-trained model can improve transfer performance for end-users.
