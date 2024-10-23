# Ad Content Analyzer: Predictive Evaluation of Video Advertisement Content


## Project Overview

This project focuses on evaluating the content of video advertisements by analyzing their descriptions and answering specific yes/no questions related to the ads. The system compares generated answers against a ground truth dataset provided by human coders and calculates performance metrics to assess the accuracy and reliability of the automated process.

By leveraging techniques such as text embedding, cosine similarity, and batch processing, this project provides a scalable solution for analyzing large datasets of video ad content efficiently. The ultimate goal is to automate content analysis and improve precision in determining whether specific ad elements are present.


## Objective

The primary objective of this project was to:

+ Automate the evaluation of video ad content based on specific yes/no questions.
+ Compare the generated results with a ground truth dataset to compute accuracy, precision, recall, and F1 scores.
+ Identify areas where the model performs well and areas needing improvement.


## Methodology

**1. Data Loading:**
Loaded video advertisement descriptions and ground truth data from Google Drive.

**2. Model Selection:**
Utilized the all-mpnet-base-v2 model from Sentence Transformers for embedding the ad descriptions and questions, chosen for its semantic text understanding capabilities.

**3. Document Preparation:**
Wrapped each ad description in a Document object to facilitate easy indexing.

**4. Indexing and Query Engine Setup:**
Built a VectorStoreIndex from the document embeddings to allow for efficient querying.

**5. Question Embeddings:**
Precomputed embeddings for 21 predefined questions related to ad content.

**6. Cosine Similarity for Yes/No Answers:**
Calculated cosine similarity between the ad description embeddings and question embeddings to generate yes/no answers based on a threshold.

**7. Batch Processing:**
Implemented batch processing to handle large datasets and optimize memory usage.

**8. Output Preparation:**
Generated and saved the yes/no answers for each question in CSV format.

**9. Evaluation Metrics:**
Compared the model's generated answers to the ground truth dataset, calculating precision, recall, F1 score, and agreement percentage for each question.

## Key Results

* **Precision:** High precision was observed for questions like **"Is there an incentive to buy?"** and **"Does the ad mention at least one specific product or service?"** indicating the model's reliability in certain areas. Precision was low for other questions like **"Is online contact information provided?"**, indicating room for improvement.

* **Recall:** While precision was high in some cases, recall was generally lower, showing that the model missed some positive instances.

* **F1 Score:** The F1 score, balancing precision and recall, highlighted the need for improvement in many areas, though it performed reasonably well on questions like **"Does the ad portray a sense of urgency?"**.

* **Agreement Percentage:** Agreement between the model's answers and the ground truth ranged from 19.33% to 90.0%, showing that while the model excelled in certain areas, further tuning is required.

## Future Work

* **Fine-tuning:** Adjust the cosine similarity threshold and experiment with other text embedding models to improve recall and F1 scores.
* **Explore Alternatives:** Test alternative embedding models and similarity metrics to enhance performance.
* **Model Enhancements:** Implement additional techniques like active learning to improve model predictions on difficult questions.


