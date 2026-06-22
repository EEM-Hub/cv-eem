---
source: sources/wiki-Attention_machine_learning.md
source_url: https://en.wikipedia.org/wiki/Attention_(machine_learning)
---

## Attention Mechanisms in Machine Learning

Attention is a method that determines the relative importance of each component in a sequence by assigning learned "soft" weights. Originally developed to address limitations of recurrent neural networks (which favor recent tokens and attenuate earlier information), attention allows any token to directly access any other token in a sequence. The mechanism encodes vectors called token embeddings across a fixed-width context window. The breakthrough self-attention variant, central to the Transformer architecture (2017), replaced sequential recurrence with parallel computation and became the foundation for BERT, GPT, T5, and vision transformers.

## Key Concepts

- **Soft vs. hard weights**: "Hard" weights are learned during backpropagation and are fixed at inference; "soft" attention weights are computed dynamically during the forward pass and change with every input.
- **Alignment**: The process of matching source tokens to target tokens; visualized as an alignment matrix where off-diagonal dominance indicates non-trivial reordering (e.g., "I love you" -> "je t'aime").
- **Context vector**: A weighted linear combination of encoder hidden states, c = H * w, where w is the attention weight vector.
- **Query, Key, Value (QKV)**: Three learned projections of input embeddings. Queries ask "what am I looking for?", keys answer "what do I contain?", values provide "what information do I carry?".
- **Scaled dot-product attention**: `Attention(Q,K,V) = softmax(QK^T / sqrt(d_k)) * V` — the scaling by sqrt(d_k) prevents dot products from growing large and collapsing softmax into a hard max on a single token.
- **Self-attention**: Each element attends to all others in the same sequence, capturing global intra-sequence dependencies — unlike cross-attention where queries come from the decoder and keys/values from the encoder.
- **Permutation equivariance**: QKV attention is equivariant to permutation of queries and invariant to permutation of key-value pairs — meaning order of keys/values doesn't matter, which is why positional encodings are needed.
- **Attention matrix size**: Quadratic in sequence length (O(n^2)), which is the primary computational bottleneck for long sequences.

## Commands and Syntax

**Core attention formula (scaled dot-product):**
```
Attention(Q, K, V) = softmax(Q K^T / sqrt(d_k)) V
```
Where Q is m x d_k, K is n x d_k, V is n x d_v, output is m x d_v.

**Attention variants by computation method:**
| Variant | Formula Basis | Notes |
|---------|--------------|-------|
| Bahdanau (additive) | score(s, h) = v^T tanh(W[s;h]) | Concatenates decoder state s and encoder hidden h |
| Luong (multiplicative) | score(s, h) = s^T W h | Dot product with learned weight matrix |
| Scaled dot-product (Transformer) | softmax(QK^T / sqrt(d_k)) V | Standard in all modern transformers |

**Encoder-decoder architecture dimensions (typical):**
- Embedding dimension: 300
- Hidden vector length: 500
- Max sentence length: 100
- Dictionary sizes: 9k-10k
- Context vector: 500-long, computed as H * w

## Relationships

- **RNNs / LSTMs**: Attention was originally grafted onto encoder-decoder RNNs to solve the vanishing gradient / long-range dependency problem; Transformers later removed the RNN entirely.
- **Transformers**: Self-attention is the core mechanism; multi-head attention runs multiple parallel attention functions with different learned projections.
- **Vision Transformers (ViT)**: Apply self-attention to image patches rather than words; attention maps serve as saliency/interpretability visualizations.
- **Flash Attention**: An implementation optimization that partitions attention computation into blocks fitting GPU SRAM, reducing memory from O(n^2) to O(n) without approximation.
- **Efficient Transformers**: Reformer, Linformer, Performer approximate full attention for long sequences (reducing quadratic cost).
- **Graph Attention Networks (GAT)**: Extend attention to graph-structured data (2018).
- **Non-local Neural Networks**: Extend attention to capture long-range spatial and temporal dependencies in video/images.
- **CNN attention dimensions**: Spatial attention (where to look), channel attention (which feature maps matter), or both combined (e.g., CBAM).
- **Interpretability**: Attention maps used as explanations (saliency maps, attention rollout, GradCAM for ViTs), though correlation between high attention weight and model impact is debated.

## Exam-Relevant Points

- The scaling factor is **sqrt(d_k)** (square root of key dimension), not d_k — this prevents softmax saturation where one element dominates.
- Self-attention is **permutation equivariant** w.r.t. queries and **permutation invariant** w.r.t. key-value pairs — this is why positional encoding is required.
- Output rows are confined to the **convex hull** of value vectors — attention produces weighted averages, never values outside the span of V.
- The "Attention Is All You Need" paper (Vaswani et al., 2017) introduced the Transformer; multi-head attention was part of this original design.
- **Bahdanau attention** (2014) = additive; **Luong attention** (2015) = multiplicative/dot-product. Know the distinction.
- Attention matrix memory is **O(n^2)** in sequence length — Flash Attention solves this via tiling/block-wise computation on GPU SRAM without approximation.
- **Attention rollout**: recursive dot product of attention maps across all layers to produce a single combined visualization.
- Soft attention uses a weighted sum of all hidden states; hard attention selects one state (non-differentiable, requires reinforcement learning to train).
- The fast weight controller (Schmidhuber, 1992) anticipated key-value attention via outer products — later renamed "linearized self-attention."
- Non-local means (2005) in image denoising and bilateral filters (1998) are precursors to attention in computer vision, using affinity matrices for relevance propagation.
