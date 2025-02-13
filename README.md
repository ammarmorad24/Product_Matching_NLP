# Product_Matching_NLP

Welcome to the Product Matching solution for the pharmaceutical marketplace! This repository contains the code, insights, and evaluation report for our machine learning approach that leverages XGBoost to accurately match product names even in the presence of naming variations, OCR errors, and minor spelling mistakes. 🥳

## Overview 📖

This project addresses the challenge of matching products from different sources by extracting key features like the product name, dosage form, concentration, and price. The primary goal is to assign a unique SKU to each product, ensuring seamless integration with seller inventories and enhancing the overall user experience.

### Competition Requirements

- Generate a similarity score between 0 and 1 (or 0% to 100%) for each pair of product names.
- Be robust against minor errors and variations in product names.
- Achieve at least 90% accuracy when tested against the master file.
- Execute the matching process on a CPU within 500ms per pair.
- Provide a confidence level along with the similarity score.

## Approach & Methodology 🛠️

### Data Ingestion & Preprocessing

- Imported product data from various sources.
- Cleaned and normalized product names to reduce noise (e.g., handling OCR errors like "Ibuprofn" vs. "Ibuprofen").
- Extracted key features such as product name, dosage form, concentration, and price.

### Feature Engineering

- Transformed raw text data into a structured format.
- Applied text normalization techniques and vectorized textual features for the XGBoost model.
- Incorporated domain-specific knowledge (e.g., typical dosage forms) to enhance feature quality.

### Model Training with XGBoost

- Utilized the XGBoost algorithm for its efficiency and performance on structured data.
- Tuned hyperparameters to balance accuracy and speed, ensuring inference within the 500ms requirement.
- Calculated a similarity score between product name pairs, along with a confidence level.

### Evaluation & Reporting

- Evaluated the model against a master file, achieving over 90% accuracy.
- Analyzed performance metrics and iterated on feature engineering to refine results.
- Prepared detailed experimental reports and visualizations to track model performance and error cases.

## Insights & Key Findings 🌟

- **Robustness**: The XGBoost model demonstrated strong resilience against minor spelling and OCR errors, making it an excellent choice for noisy product data.
- **Feature Importance**: Feature engineering was critical—accurate extraction and representation of product attributes greatly influenced the model’s performance.
- **CPU Efficiency**: The solution is optimized for CPU-based execution, ensuring low latency (<500ms) per prediction.
- **Scalability**: The approach can be extended to incorporate additional product features and even multi-language support in future iterations.

## Improvements & Future Work 🔄

- **Enhanced Text Similarity**: Incorporate deep learning models such as Siamese networks for more nuanced text comparison.
- **Automated Feature Extraction**: Use natural language processing (NLP) techniques to automatically extract and weigh product attributes.
- **Hyperparameter Optimization**: Further fine-tune XGBoost parameters or explore ensemble methods for even better performance.
- **User Feedback Integration**: Use real-world feedback to continuously improve the matching accuracy and update the model accordingly.

## How to Run the Code 🏃‍♂️


### Data Preparation

Place your input data files in the `/data` directory. Ensure that the master file and product sheets are correctly formatted as per the submission instructions.

### Running the Notebook

Open the `final-xgboost-solution.ipynb` in Jupyter Notebook or any compatible environment and execute the cells sequentially to reproduce the results.


