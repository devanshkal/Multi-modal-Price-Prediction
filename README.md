# Amazon ML Challenge: Price Prediction

This project focuses on the **Amazon Machine Learning Challenge** where the primary goal is to predict the price of product samples using their **catalog data** (textual features) and **associated images**.

We explored and implemented two distinct **multi-modal machine learning** approaches, combining advanced Computer Vision (CV) models for image analysis and state-of-the-art Natural Language Processing (NLP) models for catalog data.

---

## Approaches Implemented

| Approach | Image Model (CV) | Text Model (NLP) | Model Fusion / Strategy | Key Features |
| :--- | :--- | :--- | :--- | :--- |
| **Approach 1** | **ResNet-18** | **DistilBERT** | Feature concatenation after individual model outputs and fed into a final Dense Layer Regressor. | Faster training and inference due to smaller backbone models. |
| **Approach 2** | **EfficientNet-B0** | **RoBERTa** | Feature concatenation after individual model outputs and fed into a final Dense Layer Regressor. | Higher potential accuracy due to more powerful backbone models. |

### Model Architecture Overview

Both approaches follow a similar structure:
1.  **Image Processing:** Images are fed into the CV model (ResNet-18 or EfficientNet-B0) to extract a fixed-size feature vector.
2.  **Text Processing:** Catalog data is tokenized and fed into the NLP model (DistilBERT or RoBERTa) to generate a fixed-size feature vector (typically the pooled output).
3.  **Fusion:** The resulting image and text feature vectors are concatenated.
4.  **Prediction:** The concatenated vector is passed through a final Regression Head (e.g., a few Dense layers) to output the predicted price. [Image of multi-modal machine learning architecture]
