# Bigram-Based Language Identification

## Overview

Accurate language identification is crucial for multilingual systems. This project demonstrates how bigram analysis can be used to build an efficient and accurate language identifier.

The method is inspired by n-gram approaches in machine translation evaluation, such as BLEU scores, which measure overlap between sequences. Here, bigram analysis is adapted for language identification.

## Approach: BLEU-Inspired Language Identification

Instead of evaluating translations, this approach:

- Extracts word bigrams from input text
- Calculates bigram overlap with pre-computed language models
- Uses log probability scoring (similar to BLEU’s precision calculations) to identify the most likely language

This method captures linguistic patterns through sequential word pairs, which are highly discriminative across languages, offering high accuracy.

## Why Bigrams?

Bigrams are effective because they capture:

- Word order patterns specific to each language
- Common phrase structures (e.g., “of the” in English, “de la” in French)
- Efficient computation compared to longer n-grams
- Proven effectiveness in n-gram-based evaluations adapted for classification

## Dataset Overview

A pre-processed bigram dataset is provided, covering three major languages:

- English (`eng`)
- French (`fra`)
- Twi (`twi`) – a widely spoken language in Ghana

### Dataset Structure

| Column    | Description                                      |
| --------- | ------------------------------------------------ |
| `ngram`   | The word bigram, e.g., `"hello world"`           |
| `lang`    | Three-letter language code (`eng`, `fra`, `twi`) |
| `lang_id` | Numeric identifier (`1`, `2`, `3`)               |
| `count`   | Frequency of this bigram in the language         |

### Dataset Links

- CSV: [[Google Drive Link](https://drive.google.com/file/d/1fhbS5x0lbLMLJzy0-_YfNB6dtIEFBRfM/view?usp=sharing)]
- Demo Notebook for Language ID: [[Google Colab Link](https://colab.research.google.com/drive/1A9d6oO1tu8osWp6lrzCEp9fL3HYay34Q?usp=sharing)]

## Using the Dataset and Code

This dataset and reference implementation allow you to:

- Build a bigram-based language identifier
- Test language detection on individual sentences or larger text corpora
- Experiment with modifications such as character-level features, smoothing techniques, or probability optimizations
- Scale processing for efficiency with large datasets

## Key Features

- Accurate single and multiple sentence language identification
- Fast processing and low memory usage
- Flexible for experimentation and improvement

Get started by exploring the dataset and the reference implementation to build and test your own bigram-based language identifier.
