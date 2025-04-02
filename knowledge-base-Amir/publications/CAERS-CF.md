# 📚 CAERS-CF: Enhancing Convolutional Autoencoder Recommendations through Collaborative Filtering

**Published in**: Knowledge and Information Systems (Springer), 2024  
**Authors**: Amirhossein Ghadami, Thomas Tran  
**DOI**: [10.1007/s10115-024-02204-5](https://doi.org/10.1007/s10115-024-02204-5)

---

## 🧠 Overview

**CAERS-CF** is a **hybrid recommendation system** that combines:
- A novel **deep learning-based model (CAERS)** leveraging **convolutional autoencoders**
- A **collaborative filtering (CF)** approach based on **singular value decomposition (SVD)**

The model aims to merge content and behavior-based recommendation strategies using **linear regression** to dynamically weigh their outputs, yielding state-of-the-art accuracy on benchmark datasets.

---

## 🧩 Key Contributions

1. **CAERS** (Convolutional Autoencoder Recommendation System):  
   Captures nonlinear, high-order relationships from users' and items' **content data** via CAE architecture.

2. **CAERS-CF** Hybrid Model:  
   Integrates CAERS and collaborative filtering predictions using **linear regression**, enhancing performance by learning optimal combination weights.

---

## 🏗️ System Architecture

### 1. CAERS Workflow

- **Input**: Content data from users (age, occupation, gender) and items (movie title, genre, overview)
- **Steps**:
  - Feature extraction (e.g., Wikipedia scraping, BERT embeddings)
  - Content embedding (categorical and continuous)
  - Dot product → user-item interaction matrix
  - Pass through **CAE**:
    - **Encoder**: Convolution + pooling → compressed representation
    - **Decoder**: Transposed convolution + upsampling → predicted ratings

### 2. Collaborative Filtering Workflow

- Uses **SVD-based matrix factorization**
- Learns latent user/item vectors (matrices E and G)
- Predicts ratings using dot product \( \hat{R}_2 = EG^T \)

### 3. Hybrid Integration

- Combines predictions \( \hat{R}_1 \) and \( \hat{R}_2 \) via linear regression:
  \[
  \hat{R} = W_0 + W_1 \cdot \hat{R}_1 + W_2 \cdot \hat{R}_2
  \]
- Optimized via **gradient descent** to minimize MSE loss

---

## 🧪 Experimental Setup

- **Datasets**:
  - MovieLens 100K
  - MovieLens 1M
- **Evaluation Metrics**: RMSE, MAE
- **Training Details**:
  - CAERS optimizer: Adam (lr = 0.01)
  - CF optimizer: SGD (lr = 0.01)
  - Batch size: 32, Train/Val/Test split: 80/10/10
  - Hyperparameter tuning via **grid search**

---

## 📊 Results

| Dataset         | Model      | RMSE   | MAE   |
|----------------|------------|--------|--------|
| MovieLens 100K | **CAERS-CF** | **0.8801** | **0.6852** |
|                | CAERS      | 0.9218 | 0.7248 |
|                | CF         | 0.9439 | 0.7451 |
| MovieLens 1M   | **CAERS-CF** | **0.8398** | **0.6540** |
|                | CAERS      | 0.8817 | 0.6889 |
|                | CF         | 0.8860 | 0.6965 |

### 🔬 Comparison with SOTA

CAERS-CF significantly outperforms:
- GAP, ECAE, DNNRec, DCN-M, URP-CF-SIM, ExtKNNCF  
- Achieves **up to ~9% RMSE/MAE improvement**


---

## 📌 Citation

```bibtex
@article{ghadami2024caerscf,
  title={CAERS-CF: enhancing convolutional autoencoder recommendations through collaborative filtering},
  author={Ghadami, Amirhossein and Tran, Thomas},
  journal={Knowledge and Information Systems},
  volume={66},
  number={11},
  pages={6717–6738},
  year={2024},
  publisher={Springer}
}