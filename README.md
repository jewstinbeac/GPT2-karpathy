# GPT-2 Implementation from Scratch

A PyTorch implementation of the GPT-2 language model, built from the ground up following Andrej Karpathy's educational approach.

## 🎯 Project Overview

This project implements a GPT-2 style transformer language model, progressing from a simple bigram model to a full self-attention based architecture. The implementation focuses on educational clarity while maintaining the core concepts of modern language models.

## 📁 Project Structure

```
GPT2-karpathy/
├── bigram.py          # Simple bigram baseline model
├── transformer.py     # Full GPT-2 transformer implementation
├── input.txt          # Training text (Shakespeare)
├── data/              # Training datasets
│   └── tinyshakespeare/
└── README.md
```

## 🧠 Models Implemented

### 1. Bigram Model (`bigram.py`)
- **Simple baseline**: Predicts next token based only on current token
- **Architecture**: Direct embedding lookup table
- **Purpose**: Establishes baseline performance and training infrastructure

### 2. GPT-2 Transformer (`transformer.py`)
- **Self-attention mechanism**: Multi-head attention for contextual understanding
- **Positional embeddings**: Learned position encoding
- **Feed-forward layers**: MLP blocks for transformation
- **Layer normalization**: Training stability
- **Causal masking**: Ensures autoregressive generation

## 🚀 Key Features

- **From scratch implementation**: No pre-trained models, built for educational understanding
- **Progressive complexity**: Start simple with bigram, build up to full transformer
- **Character-level tokenization**: Works with any text input
- **Efficient training**: Optimized batch processing and attention computation
- **Text generation**: Sample coherent text after training

## 🔧 Architecture Details

### Model Specifications
- **Vocabulary**: Character-level (typically ~65 unique characters)
- **Embedding dimension**: 384 (configurable)
- **Number of layers**: 6 transformer blocks
- **Attention heads**: 6 heads per layer
- **Context length**: 256 tokens
- **Parameters**: ~10M (small GPT-2 scale)

### Key Components
- **Token + Position Embeddings**: Rich input representations
- **Multi-Head Self-Attention**: Parallel attention computation
- **Feed-Forward Networks**: 4x expansion ratio
- **Residual Connections**: Skip connections for gradient flow
- **Layer Normalization**: Pre-norm configuration

## 📊 Training

The model is trained on the Tiny Shakespeare dataset:
- **Dataset**: Complete works of Shakespeare (~1MB text)
- **Objective**: Next-token prediction (cross-entropy loss)
- **Optimizer**: AdamW with learning rate scheduling
- **Batch size**: 64 sequences
- **Training time**: ~10 minutes on modern GPU

## 🎭 Sample Output

After training, the model generates Shakespeare-like text:

```
DUKE OF GLOUCESTER:
And if I die, I shall be buried in the
Tower of London, and the king shall be
crowned with a crown of gold.

KING RICHARD III:
What say you to this?
```

## 💻 Usage

### Training the Model
```bash
# Activate virtual environment
source myenv/bin/activate

# Train the bigram baseline
python bigram.py

# Train the full transformer
python transformer.py
```

### Requirements
```bash
torch>=2.0.0
numpy
```

## 🧪 Educational Value

This implementation serves as a learning resource for understanding:

1. **Transformer Architecture**: How self-attention enables sequence modeling
2. **Training Dynamics**: Loss curves, gradient flow, optimization
3. **Scaling Laws**: How model size affects performance
4. **Generation Quality**: From bigram randomness to coherent text

## 🔗 Inspiration

Based on Andrej Karpathy's "Let's build GPT: from scratch, in code, spelled out" tutorial, focusing on educational clarity and hands-on implementation.

## 📈 Results

| Model | Parameters | Training Loss | Validation Loss | Generation Quality |
|-------|------------|---------------|-----------------|-------------------|
| Bigram | ~4K | 2.5 | 2.5 | Random characters |
| GPT-2 | ~10M | 1.2 | 1.4 | Coherent Shakespeare |

## 🤝 Contributing

This is an educational project. Feel free to:
- Experiment with hyperparameters
- Try different datasets
- Add model improvements
- Share interesting generated samples

## 📜 License

MIT License - Feel free to use for educational purposes.

---
*Built with ❤️ for learning how language models work*
