---
title: Multiple Choice Question Generation by Fine-Tuning BART in Modular and Unified Approaches
summary: To streamline the generation of high-quality multiple-choice questions (MCQs), two sequential pipelines were created: one with a modular design for question/answer and distractor generation, and another with a single unified model. BART was fine-tuned on the SciQ dataset, and the unified model outperformed the modular model on qualitative measures and cosine similarity of correct answers and distractors. Another pipeline was developed to extend the use of the model\: given a URL and a topic, it generates an MCQ. A fine-tuned BART-large model successfully generated MCQs beyond the science domain of the SciQ dataset.
tags:
  - Data Science
  - Natural Language Processing
  - Machine Learning
  - Large Language Model
date: "2024-04-20T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Image by Freepik
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: github
    url: https://github.com/christian-hobelsberger/NLP_project_quizz_generator
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---
## Overview
To enhance the generation of high-quality multiple-choice questions (MCQs), we developed two distinct pipelines. One utilizes a modular design for separate question/answer and distractor generation, while the other employs a single unified model.

## Methodology
### Model Development
We fine-tuned the BART model on the SciQ dataset to create two pipelines:
1. **Modular Pipeline**: This pipeline separately generates questions/answers and distractors.
2. **Unified Model Pipeline**: This pipeline integrates both tasks into a single model.

### Performance Evaluation
- **Unified Model**: Outperformed the modular design based on qualitative measures and cosine similarity of correct answers and distractors.

## Real-World Application
### Extended Pipeline
A third pipeline was built to adapt the model for practical use. Given a URL and a topic, it generates an MCQ.
- **Generalization**: The fine-tuned BART-large model successfully generated MCQs in various domains beyond the SciQ dataset.

## Future Work
With further fine-tuning on more diverse data, we believe this model can produce high-quality MCQs across a wide range of topics.

## Conclusion
The unified BART model demonstrates significant potential for efficient and versatile MCQ generation, paving the way for broader applications in educational and professional settings.

## Authors

- Rutger Lemein
- Christian Hobelsberger
- M. Rizki Duwinanto
- Bernardus Brouwer