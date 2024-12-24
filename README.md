# Analogical Reasoning in Llama2

## Overview

This project investigates the performance of the **Llama-2** model in the context of analogical reasoning. The main objective is to compare the performance of the model against human reasoning. Using the Llama-2 models (7B and 13B), we performed a series of tests and evaluated their responses based on predefined categories such as "True", "False", "Cross-Domain", and "Within-Domain".

## Dataset

For the analysis, we used a dataset designed to test analogical reasoning across different categories. The dataset contains pairs of instructional sentences and responses, with modifications made to the questions to improve clarity and standardization. The dataset categorizes analogies into:
- **TRUE** or **FALSE**
- **Cross-Domain**, **Within-Domain**, and **False** categories

We transformed the original prompts into explicit forms like **"Choose one among two: TRUE or FALSE"** to improve model accuracy.

The dataset used in this project was derived from an analogy reasoning task, which is part of the broader **Llama-2** model evaluation.

## Methodology

We used the following steps to analyze the analogical reasoning performance of Llama-2 models:

1. **Dataset Construction**: The dataset was created by pairing instructional sentences with corresponding responses, ensuring a diverse range of linguistic scenarios.
2. **Model Interaction**: The Llama-2 models (7B and 13B) were accessed via the Gradient platform, where they were provided with individual prompts from the dataset to generate responses.
3. **Response Categorization**: Each model's response was categorized based on keywords like "Cross-Domain", "Within-Domain", or "FALSE". These categories were stored in a vector for comparison with human responses.
4. **Performance Evaluation**: The model responses were compared with ground truth (correct) responses, and the accuracy was calculated. This also included the calculation of false positives and false negatives to assess the model's performance in more detail.

### Prompts Used

The following prompts were tested across all models to evaluate analogical reasoning:

1. **Prompt 1**: "Which is the analogical reasoning of a is to b as c is to d?"
2. **Prompt 2**: "A a is to b exactly what a c is to d?"
3. **Prompt 3**: "The relationship between a and b is the same that there is between c and d?"

### Experiments

Two distinct experimental setups were used to evaluate the models' performance:
- **Three-category task**: "Cross-Domain", "Within-Domain", "False".
- **Two-category task**: "True" and "False".

### Model Performance

Below are the results for each model (7B and 13B) and prompt combination:

| Model     | Prompt 1: 3 choices | Prompt 2: 3 choices | Prompt 3: 3 choices | Prompt 1: 2 choices | Prompt 2: 2 choices | Prompt 3: 2 choices |
|-----------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|
| **7B**     | 69 FP, 0 FN         | 74 FP, 0 FN         | 73 FP, 4 FN         | 39 FP, 3 FN         | 35 FP, 5 FN         | 9 FP, 39 FN         |
| **13B**    | 64 FP, 8 FN         | 71 FP, 5 FN         | 68 FP, 9 FN         | 38 FP, 0 FN         | 34 FP, 1 FN         | 23 FP, 11 FN        |

**FP** = False Positives, **FN** = False Negatives.

## Key Findings

- **False Positives**: The model tended to classify most responses as **"Cross-Domain"** or **"Within-Domain"** for the three-category tasks, and as **"True"** for the two-category tasks.
- **Accuracy**: There were varying levels of accuracy, and the model's performance was often suboptimal compared to human responses, especially when more diverse categories were involved.
- **Model Behavior**: Despite adjustments to prompts, the Llama-2 models (especially 7B) frequently misclassified answers, particularly when tasked with choosing between **TRUE** and **FALSE**.

## Setup

To replicate the experiments or use the code in this repository:

### Requirements

1. Python 3.x
2. Llama-2 Model (7B or 13B)
3. Gradient Platform Account (for accessing Llama-2 models)

### Authors:
-Bazzan Sofia

-Bianchi Simone


