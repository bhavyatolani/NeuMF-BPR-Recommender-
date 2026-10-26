# 📚 NeuMF-BPR Recommender System

*A deep learning project for personalized recommendations using user–item interactions.*

## 🌟 About the Project

I built this project to explore how deep learning can help recommend relevant items to users based on their past interactions.

The project uses a **NeuMF-style model trained with Bayesian Personalized Ranking (BPR) loss**. I experimented with two datasets—Gowalla and Amazon-Book—and evaluated the model using ranking metrics.

My goal was to understand how user and item embeddings, neural networks, and pairwise ranking work together in a recommendation system.

## 🎯 Project Objectives

- Build a neural collaborative filtering recommendation model.
- Combine Generalized Matrix Factorization (GMF) and a Multilayer Perceptron (MLP).
- Learn user–item interaction patterns through embeddings.
- Train the model using BPR pairwise-ranking loss.
- Evaluate recommendations using HR@10, NDCG@10, and Recall@10.

## 🧠 How the Model Works

The model combines two learning approaches:

**1. Generalized Matrix Factorization (GMF)**

- Learns interactions between user and item embeddings.
- Uses element-wise multiplication to capture their matching patterns.

**2. Multilayer Perceptron (MLP)**

- Learns nonlinear relationships between user and item embeddings.
- Uses dense neural network layers to learn more complex interaction patterns.

**3. BPR Loss**

- Compares positive interactions with sampled negative items.
- Encourages the model to assign higher scores to positive interactions.

The outputs from GMF and MLP are combined to generate a score for each user–item pair.

## 📂 Datasets

This project uses two recommendation datasets:

| Dataset | Description |
|---|---|
| **Gowalla** | User check-in interactions with locations |
| **Amazon-Book** | User interactions with books |

The notebook downloads the dataset files from the URLs specified in the code and uses the supplied training and test files.

## 🛠️ Tech Stack

- **Language:** Python
- **Deep Learning:** TensorFlow / Keras
- **Numerical Computing:** NumPy
- **Environment:** Google Colab
- **Model:** NeuMF-style architecture with BPR loss

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Training epochs | 5 |
| Embedding dimension | 16 |
| Optimizer | Adam |
| Learning rate | 0.001 |
| Ranking metrics | HR@10, NDCG@10, Recall@10 |

## 📊 Results

The following results were obtained in my current notebook run.

| Dataset | HR@10 | NDCG@10 | Recall@10 |
|---|---:|---:|---:|
| Gowalla | 0.5145 | 0.3186 | 0.5145 |
| Amazon-Book | 0.4520 | 0.2676 | 0.4520 |

### 🔎 Evaluation Details

- Evaluation was limited to a maximum of **2,000 users** for speed.
- Each evaluated user had one held-out positive item.
- The positive item was ranked against 99 sampled negative items.
- HR@10 and Recall@10 are identical in this setup because only one positive target is evaluated per user.

These results describe this implementation and its evaluation protocol. They should not be interpreted as a direct reproduction of published benchmark results.

## 🚀 How to Run the Project

1. Open the notebook in Google Colab.
2. Run the notebook cells in order.
3. Allow the dataset files to download.
4. Train the model for five epochs on each dataset.
5. Review the evaluation metrics printed at the end.

**Requirements:** Python, TensorFlow, and NumPy. The notebook should be checked against the current dataset URLs and package versions before rerunning.

## 📁 Repository Contents

- `Yet_another_copy_of_NMF.ipynb` — Notebook containing the model implementation, training, and evaluation.

## 🔧 Limitations & Future Improvements

There are several ways I would like to improve this project:

- Set random seeds consistently to improve reproducibility.
- Evaluate multiple held-out positive items per user where appropriate.
- Compare the model with a Matrix Factorization baseline.
- Experiment with different embedding dimensions and learning rates.
- Explore alternative negative-sampling strategies.
- Evaluate on a larger user sample and investigate full-catalogue ranking.

## 💡 Key Learnings

Through this project, I explored:

- How collaborative filtering can be implemented using neural networks.
- How GMF and MLP learn different user–item interaction patterns.
- How BPR loss supports personalized ranking.
- How ranking metrics help evaluate recommendation quality.
- Why the evaluation protocol matters when interpreting model performance.

## 👩‍💻 Author

**Bhavya Tolani**

*Interested in machine learning, data science, and recommendation systems.*

---

⭐ *This project is part of my learning journey in deep learning and recommender systems.*
