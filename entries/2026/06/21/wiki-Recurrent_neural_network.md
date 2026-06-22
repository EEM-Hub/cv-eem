---
source: sources/wiki-Recurrent_neural_network.md
source_url: https://en.wikipedia.org/wiki/Recurrent_neural_network
---

## Recurrent Neural Networks (RNNs): Architecture, Variants, and Training

Recurrent neural networks are a class of artificial neural networks designed for sequential data processing (text, speech, time series). Unlike feedforward networks, RNNs maintain a hidden state that acts as memory, updated at each time step based on current input and previous state. This enables them to capture temporal dependencies. While historically dominant for sequence tasks, RNNs have been largely supplanted by transformers for many applications, though they remain relevant where computational efficiency or real-time processing is required.

## Key Concepts

- **Recurrent unit**: The fundamental building block; maintains a hidden state h_t updated each step: f_θ(x_t, h_t) → (y_t, h_{t+1})
- **Hidden state**: A vector serving as "memory" — a partial record of all previous input-output pairs
- **Vanishing gradient problem**: Traditional RNNs cannot learn long-range dependencies because gradients shrink exponentially during backpropagation through time (BPTT); this motivated LSTM and GRU
- **LSTM (Long Short-Term Memory)**: Invented by Hochreiter & Schmidhuber (1995/1997); uses gates (input, forget, output) and a cell state to preserve gradients over long sequences; became the default RNN variant
- **GRU (Gated Recurrent Unit)**: A computationally cheaper alternative to LSTM with fewer gates (reset and update)
- **Unfolding**: An RNN can be "unrolled" in time into what resembles a deep feedforward network, with one layer per time step — this is how BPTT works
- **Teacher forcing**: Training technique where the ground-truth previous output is fed as input at the next step, rather than the model's own prediction
- **Backpropagation Through Time (BPTT)**: The standard training algorithm; applies backpropagation to the unrolled network. Truncated BPTT limits the number of time steps to reduce cost
- **Seq2seq (encoder-decoder)**: Two RNNs coupled together — the encoder compresses an input sequence into a context vector, the decoder generates an output sequence from it

## Commands and Syntax

**Elman network equations (Simple RNN):**
```
h_t = σ_h(W_h · x_t + U_h · h_{t-1} + b_h)
y_t = σ_y(W_y · h_t + b_y)
```

**Jordan network equations:**
```
h_t = σ_h(W_h · x_t + U_h · s_t + b_h)
y_t = σ_y(W_y · h_t + b_y)
s_t = σ_s(W_{s,s} · s_{t-1} + W_{s,y} · y_{t-1} + b_s)
```
Key difference: Jordan networks feed back from the output layer; Elman networks feed back from the hidden layer.

**Stacked (Deep) RNN**: Multiple RNN layers stacked vertically — layer k's output sequence becomes layer k+1's input sequence. No depth limit in principle.

**Bidirectional RNN**: Two RNNs process the same sequence in opposite directions; outputs are concatenated: ((y_0, y'_0), (y_1, y'_1), ..., (y_N, y'_N))

## Relationships

- **LSTM / GRU**: Specific architectures that solve the vanishing gradient problem inherent in vanilla RNNs; LSTM is the standard, GRU is a lighter alternative
- **Transformers**: Replaced RNNs for most NLP tasks post-2017; use self-attention instead of recurrence, enabling better parallelization and long-range dependency handling
- **CNNs + RNNs**: Combined for tasks like image captioning (CNN extracts features, RNN generates captions)
- **Attention mechanisms**: Developed within the encoder-decoder RNN framework (2014-2017) to address the bottleneck of compressing all information into a fixed-length context vector; this directly led to transformers
- **ELMo**: A stacked bidirectional LSTM producing contextual word embeddings (2018); bridged the gap between static word embeddings and transformer-based models like BERT
- **Hopfield networks**: A special case of fully recurrent networks with symmetric weights; connections to statistical mechanics (Ising model, spin glasses); guarantees convergence but doesn't process sequences
- **Feedforward networks**: RNNs generalize feedforward nets; a fully cross-coupled RNN is equivalent to an infinitely deep feedforward network (Rosenblatt, 1961)

## Exam-Relevant Points

- RNNs process sequential data by maintaining a hidden state that is updated at each time step — this is what distinguishes them from feedforward networks
- The **vanishing gradient problem** is the primary limitation of vanilla RNNs; LSTM solved it with gating mechanisms (1997)
- **LSTM** uses three gates (input, forget, output) plus a cell state; **GRU** uses two gates (reset, update) and is computationally cheaper
- **Bidirectional RNNs** process sequences in both directions and concatenate outputs; they require the full sequence to be available (not suitable for real-time/online processing)
- **Encoder-decoder (seq2seq)** architecture was state of the art for machine translation 2014-2017 and was the precursor to transformers
- **BPTT** is the training algorithm for RNNs; **truncated BPTT** trades long-range gradient accuracy for computational efficiency
- RNNs share parameters across all time steps (weight tying), unlike unrolled feedforward networks
- **Elman networks** feed back from the hidden layer; **Jordan networks** feed back from the output layer — both are called "Simple Recurrent Networks" (SRNs)
- **PixelRNN** extends RNNs to 2D data (images), processing pixels in a defined order (e.g., row-by-row or diagonal)
- Historical lineage: neuroscience (Cajal's recurrent circuits, 1901) → McCulloch-Pitts (1943) → Rosenblatt's cross-coupled perceptrons (1960) → Hopfield (1982) → Elman/Jordan (1986/1990) → LSTM (1995) → Bidirectional LSTM → seq2seq (2014) → attention → transformers (2017)
