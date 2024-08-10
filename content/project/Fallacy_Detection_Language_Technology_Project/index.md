---
title: "A Comparative Analysis of Prompting Techniques for Fallacy Detection"
summary: "This study explores the effectiveness of different prompting techniques for fallacy detection, a task requiring complex reasoning, using three State-of-the-Art (SotA) LLMs: Llama3, Gemma 7B, and Mistral 7B. We evaluate five prompting techniques: a handcrafted baseline, Chain-of-Thought (CoT), Thread-of-Thought (ThoT), Knowledge Generation, and Self-Consistency, against the Multi-level Annotated Fallacy Dataset (MAFALDA). The study aims to determine the impact of these techniques on LLM performance in fallacy detection, identifying the best combination of LLM and prompting technique according to the MAFALDA taxonomy. The findings highlight the individual strengths and limitations of each prompting technique and discuss future research directions."
tags:
  - Data Science
  - Deep Learning
  - Large Language Models
  - Statistics
date: "2024-06-09T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: "CNN Architecture used for image classification"
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: github
    url: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---

## Introduction
This blog post delves into the application of Large Language Models (LLMs) to the task of detecting logical fallacies in online discourse. Logical fallacies, which are errors in reasoning that undermine the logic of an argument, are prevalent in discussions ranging from social media debates to political speeches. We explored how different LLMs, leveraging state-of-the-art prompting techniques, could be employed to identify these fallacies with greater accuracy.

## Experimental Setup

### Dataset
The dataset used for this study is MAFALDA, a collection of annotated texts with logical fallacies sourced from Reddit discussions, news outlets, online quizzes, and political debates. This dataset, compiled by Helwe et al. (2023a), includes 200 annotated data points with 23 different types of fallacies. Each data point consists of a text, a list of fallacies identified within the text, and annotator comments justifying the classifications.

### Models
We experimented with three different LLMs:

- **Llama3 (8B parameters)**: Developed by Meta, this model is known for its exceptional contextual understanding and precise text generation capabilities.
- **Gemma 7B**: A lightweight model from Google, designed for efficient text-to-text tasks with high accuracy.
- **Mistral 7B**: A model that uses advanced techniques like Grouped-Query Attention (GQA) and Sliding Window Attention (SWA) to manage longer sequences and outperform larger models in several benchmarks.

### Prompting Techniques
We employed four different prompting techniques to enhance the models' performance in detecting logical fallacies:

1. **Chain-of-Thought (CoT) Prompting**: Encourages the model to break down the task into smaller steps, improving its reasoning abilities.
2. **Thread-of-Thought (ThoT) Prompting**: An advanced version of CoT, designed to segment and analyze context methodically.
3. **Self-Consistency**: A novel decoding strategy where multiple reasoning paths are generated, and the most consistent answer is selected.
4. **Generated Knowledge Prompting (GKP)**: Prompts the model to generate knowledge related to the task before attempting to solve it, improving its commonsense reasoning.

## Results

### Prompting Techniques
The results of our experiments revealed significant differences in the performance of each prompting technique across the three LLMs.

- **CoT Prompting**: Performed well on certain models, but showed varying results depending on the specific model and task.
- **ThoT Prompting**: Improved output quality significantly, especially when used with a double-prompting approach.
- **Self-Consistency**: Showed improvements in multi-label classification tasks, but performed poorly in simpler multi-class classification.
- **GKP**: Consistently performed well across all models, making it the most reliable technique in this study.

### 3.1 Multi-label Classification with Spans

| Model   | Prompting Technique | Precision (%) | Recall (%) | F1-Score (%) |
|---------|----------------------|---------------|------------|--------------|
| Llama3  | Thread-of-Thought    | 30.61         | 28.09      | 28.19        |
| Llama3  | Chain-of-Thought     | 20.50         | 17.24      | 17.94        |
| Llama3  | Generated Knowledge  | 31.25         | 30.35      | 30.58        |
| Llama3  | Self-Consistency     | 19.25         | 18.29      | 18.06        |
| Gemma   | Thread-of-Thought    | 10.16         | 10.09      | 10.12        |
| Gemma   | Chain-of-Thought     | 25.09         | 27.85      | 25.45        |
| Gemma   | Generated Knowledge  | 23.44         | 22.40      | 22.32        |
| Gemma   | Self-Consistency     | 24.88         | 25.62      | 24.51        |
| Mistral | Thread-of-Thought    | 29.12         | 26.27      | 26.87        |
| Mistral | Chain-of-Thought     | 31.55         | 30.58      | 30.01        |
| Mistral | Generated Knowledge  | 34.32         | 29.68      | 30.06        |
| Mistral | Self-Consistency     | 32.75         | 32.85      | 31.71        |

### 3.2 Multi-label Classification without Spans

| Model   | Prompting Technique | Precision (%) | Recall (%) | F1-Score (%) |
|---------|----------------------|---------------|------------|--------------|
| Llama3  | Thread-of-Thought    | 40.04         | 37.87      | 37.92        |
| Llama3  | Chain-of-Thought     | 24.61         | 22.08      | 22.57        |
| Llama3  | Generated Knowledge  | 31.83         | 30.92      | 31.20        |
| Llama3  | Self-Consistency     | 23.42         | 19.43      | 20.18        |
| Gemma   | Thread-of-Thought    | 16.90         | 19.91      | 17.53        |
| Gemma   | Chain-of-Thought     | 25.85         | 31.25      | 26.72        |
| Gemma   | Generated Knowledge  | 27.25         | 25.17      | 25.47        |
| Gemma   | Self-Consistency     | 25.10         | 25.43      | 19.57        |
| Mistral | Thread-of-Thought    | 37.05         | 38.01      | 36.57        |
| Mistral | Chain-of-Thought     | 38.32         | 35.79      | 35.89        |
| Mistral | Generated Knowledge  | 37.08         | 34.50      | 35.02        |
| Mistral | Self-Consistency     | 31.54         | 29.94      | 30.05        |


### Model Performance
- **Llama3**: Demonstrated a primacy bias, performing better with prompts that provided clear instructions at the beginning.
- **Gemma**: Struggled compared to the other models, likely due to being trained on fewer tokens.
- **Mistral**: Outperformed both Llama3 and Gemma across most tasks, particularly excelling in multi-label classification tasks.

## Limitations and Further Research
Despite the promising results, this study had several limitations:

- **Dataset Limitations**: The MAFALDA dataset is small and contains non-standardized labels, which may have impacted the models' performance.
- **Resource Constraints**: The use of 4-bit quantized versions of the models, due to limited computational resources, may have affected the outcomes.
- **Prompting Challenges**: Fine-tuning prompts for different LLMs proved difficult, as each model responded differently to the same prompts.

Future research should focus on overcoming these limitations by exploring larger datasets, employing more powerful computing resources, and developing more tailored prompting strategies for each model.

## Conclusion
Our study highlights the potential of LLMs in the domain of logical fallacy detection, particularly when using advanced prompting techniques like GKP and ThoT. However, the variability in performance across different models and tasks suggests that further optimization and research are needed to fully harness the power of these models in this challenging domain.

## Authors

- Christian Hobelsberger
- Anna Smirnova
- Hemran Akhtari
- Bernardus Brouwer
- Abi Raveenthiran
