# Product Matching Solution 🚀

This repository contains a product matching model designed for a pharmaceutical marketplace. The solution leverages an XGBoost-based approach to accurately match product names against a master file. Here’s everything you need to know about running and understanding the model.

---

## System Requirements & Environment 🖥️💾

- **Hardware:**  
  - **RAM:** At least 3GB for training.  
  - **CPU:** A good CPU is required as the model takes advantage of thread parallelism for faster computations.
  
- **Environment:**  
  - It is **highly recommended** to run this model in a **Conda environment** to ensure all dependencies and configurations are managed seamlessly.  
  - **Linux Operating System** is also preferable ... it supports **High Performance of the Model**

---

## Features & Model Overview 🔍📊

- **Key Features:**  
The model pairs products in two distinct ways. Initially, it generates positive pairs by matching items from the master file with seller listings that share the same SKU, then, it forms negative pairs by associating a product with unrelated items.

For each pair, a comprehensive set of features is extracted:

- **Fuzzy Matching Scores:** Utilizing tools such as `fuzz.ratio` and `fuzz.token_set_ratio`, the model assesses initial similarity, comparable to evaluating different renditions of the same narrative.
- **Token Overlap:** This feature quantifies the number of shared words between the two texts, akin to identifying recurring themes across different stories.
- **TF-IDF Cosine Similarity:** By vectorizing the text and calculating the cosine similarity, this feature captures the deeper semantic meaning, much like understanding the tone and style of a text.
  
- **Model Essentials:**  
  - **Algorithm:** I used two functions as suggestions for the solution **logistic** and **rank:pairwise** and from observations ... I noticed that the **rank:pairwise** achieves better understanding of the problem
  - **Thread Parallelism:** Leverages multi-threading to speed up training and prediction processes.

- **Scoring Pattern:**  
  The model outputs a similarity score that reflects the confidence in a product match:  
  - **Score ≥ 0.9:** Highly confident and correct match. ✅  
  - **Score between 0.7 and 0.9:** Mildly confident; although it generally indicates a correct match, it may require further assurance. ⚠️  
  - **Score < 0.7:** The product is either not present in the master file or represents a weak match. ❌

---

## [NEW] Additional Model: Bayesian Classifier Approach 📊

- **Alternative Solution:**
  - A Bayesian Classifier model has been implemented as an alternative approach, achieving approximately 96% accuracy.
  - The implementation details and evaluation metrics can be found in the `Bayesian_Solution.ipynb` notebook.
  - This probabilistic approach offers a complementary perspective to the XGBoost solution, potentially useful for ensemble methods or comparative analysis.

## Room for Improvement & Future Directions 🔄🧠

- **Neural Network Transformation:**  
  - A potential improvement would be to convert this model into a neural network. According to the paper [Model Compression by Bucila et al.](https://www.researchgate.net/publication/221653840_Model_compression) , such an approach can capture more nuanced patterns in textual data, potentially boosting performance.
  
- **Feature Enhancement with Hamming Distance:**  
  - Another avenue to explore is incorporating **Hamming Distance** as an additional feature to better capture similarities in character-level representations of product names.

---

## How to Run the Code 🏃‍♂️

- **Execution Instructions:**  
  - Simply follow the detailed instructions provided in the `final-xgboost-solution.ipynb` Notebook. The notebook is designed as a **journal-like** guide that walks you through every step of the process from data ingestion to prediction.
  - to test and load models for fast evaluation just read the first of the notebook and then scroll down run the matching function first then the loaded models after initializing everything at the beginning of the notebook
  - Open the notebook in your preferred Jupyter environment and execute the cells sequentially.
