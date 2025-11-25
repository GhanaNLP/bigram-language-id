# Bigram-Based Language Identification for Multilingual Text
## Adapting BLEU Score Principles for Language Detection

## Problem Statement
Accurate language identification is crucial for multilingual systems, yet traditional methods often struggle with computational efficiency and accuracy trade-offs. This challenge explores using bigram analysis—inspired by machine translation evaluation metrics—to build an efficient and accurate language identifier.

## The Approach: BLEU-Inspired Language ID

Machine translation evaluation relies heavily on **BLEU scores**, which measure translation quality by calculating n-gram overlap between outputs and references. This challenge adapts this precision-focused n-gram matching concept for language identification.

Instead of evaluating translations, we:
1. Extract **word bigrams** from input text
2. Calculate bigram overlap with pre-computed language models
3. Use **log probability scoring** (similar to BLEU's precision calculations) to identify the most likely language

This approach offers high accuracy by capturing linguistic patterns through sequential word pairs, which are highly discriminative across languages.

## Dataset Overview

We provide a pre-processed bigram dataset covering **three major languages**:
- **English (eng)**
- **French (fra)** 
- **Twi (twi)** - a widely spoken language in Ghana

**Dataset Structure:**
| Column | Description |
|--------|-------------|
| `ngram` | The word bigram, e.g., "hello world" |
| `lang` | Three-letter language code (eng, fra, twi) |
| `lang_id` | Numeric identifier (1, 2, 3) |
| `count` | Frequency of this bigram in the language |

**Dataset Links:**
- CSV: [Google Drive Link]
- Training Notebook (Bigram Extraction): [Google Colab Link]

## Reference Implementation

A working language identifier using the BLEU-inspired approach is provided:

**Colab Notebook:** [Insert Your Colab Link Here]

The reference implementation includes:
- Bigram extraction from input text
- Log probability calculation with smoothing for unseen bigrams
- Length-normalized scoring (inspired by BLEU's brevity penalty)
- Language prediction with confidence scores

### Example Usage:
```python
identifier = BigramLanguageIdentifier("bigrams.csv")

text = "This is an example sentence in English."
predicted_lang, scores = identifier.predict(text)

print(f"Predicted language: {predicted_lang}")
# Output: Predicted language: eng
```

## The Challenge

Your task is to:

1. **Improve Accuracy**: Enhance the baseline bigram approach to achieve higher language identification accuracy
   - Consider incorporating character-level features
   - Experiment with different smoothing techniques
   - Optimize probability calculations

2. **Optimize Efficiency**: Scale the solution for production use
   - Process single sentences with minimal latency
   - Enable batch processing of large corpora (target: 100K+ sentences)
   - Minimize memory footprint and computation time

3. **Validation**: Test your approach against a held-out validation set (provided at hackathon start)

## Key Goals & Deliverables

- **Single Sentence ID**: Efficient, accurate language detection for individual inputs
- **Batch Processing**: Scalable solution for processing large text corpora
- **Accuracy Metrics**: Match ground-truth validation language codes with highest possible precision
- **Innovation**: Novel approaches to improving the bigram-based method are encouraged

## Why Bigrams?

Bigrams capture:
- **Word order patterns** specific to each language
- **Common phrase structures** (e.g., "of the" in English, "de la" in French)
- **Efficient computation** compared to longer n-grams
- **Proven effectiveness** in MT evaluation (BLEU) adapted for classification

## Evaluation Criteria

Solutions will be evaluated on:
1. **Accuracy** on validation set (primary metric)
2. **Processing speed** (sentences per second)
3. **Code quality** and documentation
4. **Innovation** in approach and optimizations

---

**Get Started:** Review the reference implementation, explore the bigram dataset, and build your optimized language identifier!
