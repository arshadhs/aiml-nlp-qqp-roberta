# aiml_nlp_qqp_roberta

Fine-tuning and comparative evaluation of **RoBERTa** and **DistilRoBERTa** for duplicate question detection using the **GLUE QQP dataset**.

## Overview

**QQP (Quora Question Pairs)** → A dataset of labelled question pairs originally released by Quora and included in the **GLUE (General Language Understanding Evaluation)** benchmark.

The task is **binary sequence-pair classification**: given two questions, predict whether they have the same meaning (duplicate) or not.

## Models

Two pretrained Transformer models are fine-tuned and compared:

- **`roberta-base`** → A larger model with greater capacity for understanding language.
- **`distilroberta-base`** → A smaller, distilled version designed to be faster and computationally more efficient.

Both models are fine-tuned rather than trained from scratch, adapting their existing language representations to duplicate question detection.

## Objective

To investigate, compare the models using **Accuracy, Precision, Recall and F1-Score**.

**Does the larger RoBERTa model justify its additional computational cost, or can DistilRoBERTa achieve comparable performance with fewer resources?**

## Technology

Python · Jupyter Notebook · Hugging Face Transformers · Hugging Face Datasets · PyTorch

---

```mermaid
flowchart TD
    A["Setup & Configuration"] --> B["Load GLUE QQP Dataset"]
    B --> C["Explore Train & Validation Data"]
    C --> D["Process Both Models"]

    D --> E["RoBERTa-base"]
    D --> F["DistilRoBERTa-base"]

    E --> G["Tokenization"]
    F --> H["Tokenization"]

    G --> I["Load Model & Fine-tune"]
    H --> J["Load Model & Fine-tune"]

    I --> K["Evaluate on Validation Set"]
    J --> L["Evaluate on Validation Set"]

    K --> M["Compare Model Performance"]
    L --> M

    M --> N["Accuracy, Precision, Recall, F1"]
    N --> O["Predict 5+ Custom Examples"]
    O --> P["Error Analysis: FP & FN"]
    P --> Q["Export Results & Conclusions"]

    style B fill:#dbeafe,color:#1e3a8a,stroke:#2563eb
    style M fill:#dcfce7,color:#166534,stroke:#16a34a
    style Q fill:#fef3c7,color:#92400e,stroke:#d97706
```