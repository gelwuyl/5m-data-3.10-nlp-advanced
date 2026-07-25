# Brief

## Preparation

We will be using Google Colaboratory (you can use the same google account created in the previous unit) in this lesson.

## Lesson Overview

This lesson explores the evolution of Natural Language Processing (NLP) from Recurrent Neural Networks (RNNs) to Transformer architectures, highlighting how attention mechanisms and parallel processing overcome RNN limitations.

- **Architecture Evolution**: From RNNs (limited ~30-token context due to vanishing gradients) to Transformers (parallel processing, 1–2 million token context windows)
- **Core Transformer Concepts**:
  - Positional encoding for token order information
  - Multi-head attention (Query, Key, Value) for contextual relationships
  - Dynamic embeddings that adapt to surrounding text context
- **Model Architectures**:
  - BERT (encoder-only, bidirectional) for understanding tasks
  - GPT (decoder-only, autoregressive) for text generation
- **Practical Applications**: Sentiment analysis, Named Entity Recognition (NER), and text generation using Hugging Face pre-trained models
- **Transfer Learning**: Fine-tuning pre-trained models vs. training from scratch

We will be using [this](https://colab.research.google.com/drive/1io-CwOqM7Aw90_VEkvshIaP2DUx_7IpX?usp=sharing) Colab notebook for this section.

> Open the Colab link, then go to File -> Save a copy in Drive. This will create a copy of the notebook in your Google Drive. It will then open the notebook in a new tab.
>
> Follow on with the lesson in the notebook.

---

# Key Concepts

## 1. Evolution of NLP Architectures

**Recurrent Neural Networks (RNNs)** were the first deep learning models designed for sequential data, incorporating internal memory to capture historical context. However, RNNs suffer from the **vanishing gradient problem**, limiting their effective context window to approximately 30 tokens. This makes them impractical for long-range dependencies in text.

**Transformers** introduced the "Attention is All You Need" paradigm, processing tokens in parallel rather than sequentially. This breakthrough allows modern Large Language Models (LLMs) like Gemini to handle context windows of 1–2 million tokens—a dramatic improvement over RNNs.

## 2. Core Transformer Concepts

| Concept | Description |
|---------|-------------|
| **Positional Encoding** | Since Transformers process all tokens simultaneously, positional encodings inject information about token order into the model. |
| **Multi-Head Attention** | Uses Query, Key, and Value vectors (analogous to search engine logic) to compute relevance between tokens. Different attention heads specialize in different linguistic aspects (e.g., syntax, semantics, entity relationships). |
| **Dynamic Embeddings** | Unlike static word embeddings (Word2Vec, GloVe), Transformer embeddings are context-dependent. The representation of "bank" differs in "river bank" vs. "financial bank" based on surrounding context. |

## 3. BERT vs. GPT Architectures

| Model Type | Architecture | Primary Use Case |
|------------|--------------|------------------|
| **BERT** | Encoder-only, bidirectional | Understanding tasks: sentiment analysis, semantic search, NER. The **[CLS] token** aggregates sequence-level representation for classification. |
| **GPT** | Decoder-only, autoregressive | Generative tasks: text completion, dialogue, creative writing. Predicts the next token given previous context. |

**Temperature Sampling** controls generation creativity:
- **Low temperature** (e.g., 0.1–0.3): Deterministic, focused outputs
- **High temperature** (e.g., 0.7–1.0): Diverse, creative outputs

## 4. Practical Implementation & Transfer Learning

- **Hugging Face Hub** serves as the primary repository for pre-trained models (e.g., `bert-base-uncased`, `gpt2`).
- **Fine-tuning** a pre-trained model on domain-specific data (e.g., IMDB reviews, clinical notes) is far more cost-effective and performant than training from scratch.
- **Named Entity Recognition (NER)** can be performed out-of-the-box with pre-trained models and further fine-tuned for industry-specific entities (legal, medical, financial).

---

# Hands-on Activities

1. **Run the Colab Notebook** – Practice training an RNN on the Wall Street Journal dataset and fine-tuning BERT for classification.
2. **Explore BERT Explorer** – Visualize how information flows through Transformer blocks and attention heads.
3. **Review Supplementary Resources** – Two videos and one article on Transformer architecture (linked in course materials).
