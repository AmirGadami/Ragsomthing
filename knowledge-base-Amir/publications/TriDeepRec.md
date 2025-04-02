# 📘 TriDeepRec: A Hybrid Deep Learning Approach to Content- and Behavior-Based Recommendation Systems

**Published in**: *User Modeling and User-Adapted Interaction*, 2024  
**Authors**: Amirhossein Ghadami, Thomas Tran  
**DOI**: [10.1007/s11257-024-09418-w](https://doi.org/10.1007/s11257-024-09418-w)

---

## 🧠 Abstract

**TriDeepRec** is a hybrid deep learning recommendation system that combines:
- **CAERS**: A convolutional autoencoder-based model for content-based filtering
- **NCF**: Neural Collaborative Filtering for behavior-based learning
- **MLP**: A multilayer perceptron for fusing both modalities

TriDeepRec effectively addresses challenges such as **cold-start** problems and achieves superior prediction accuracy and ranking performance compared to SOTA models.

---

## 🎯 Key Contributions

1. **CAERS**: Learns complex content patterns using convolutional autoencoders.
2. **NCF**: Captures nonlinear user–item interactions via neural collaborative filtering.
3. **MLP Fusion**: Combines CAERS and NCF outputs for refined prediction.
4. Robust handling of **cold-start** scenarios using content data only.

---

## 🏗️ Model Architecture

### CAERS (Convolutional Autoencoder)
- **Input**: User/item metadata (e.g., age, occupation, movie genres, Wikipedia summaries)
- **Encoder**: Conv + pooling layers extract latent features
- **Decoder**: Deconv + upsampling layers reconstruct rating predictions
- Addresses **cold-start** problem using content alone

### NCF (Neural Collaborative Filtering)
- **GMF**: Learns linear user–item interactions
- **MLP**: Models nonlinear behavior-based interactions
- Final NCF score:  
  \[
  \hat{R}_{NCF} = \alpha \cdot GMF + (1 - \alpha) \cdot MLP
  \]

### TriDeepRec (Hybrid)
- **Fusion**: MLP with concatenated outputs \([R_{CAERS} || R_{NCF}]\)
- Learns optimal integration via backpropagation
- Objective:  
  \[
  \text{MSE Loss} = \frac{1}{N} \sum_{i=1}^{N} (R_i - \hat{R}_{Hybrid,i})^2
  \]

---

## 🧪 Experimental Setup

- **Datasets**: MovieLens 100K and 1M
- **Content Enrichment**: Wikipedia scraping + BERT encoding
- **Embeddings**:
  - Word2Vec for text
  - Custom for categorical and continuous features
- **Training**:
  - CAERS: 2 conv, 2 pool, 3 deconv layers (ReLU/Sigmoid)
  - NCF: 64-dim embeddings, dropout=0.5, 6 epochs
  - MLP: 32 neurons, tuned with ReLU & regularization

---

## 📊 Results

| Dataset        | Model        | RMSE   | MAE    | NDCG@10 |
|----------------|--------------|--------|--------|---------|
| ML-100K        | TriDeepRec   | 0.8845 | 0.6963 | 0.1489  |
|                | CAERS        | 0.9218 | 0.7248 | 0.1430  |
|                | GAP          | 0.9379 | 0.7343 | 0.1357  |
|                | DCN-M        | 0.9552 | 0.7573 | 0.1449  |
| ML-1M          | TriDeepRec   | 0.8099 | 0.6258 | 0.1896  |
|                | CAERS        | 0.8817 | 0.6889 | 0.1795  |

**Cold-start user performance (RMSE)**:
| % New Users | CAERS  | GAP    | DNNRec |
|-------------|--------|--------|--------|
| 10%         | 1.008  | 1.0248 | 1.1077 |
| 20%         | 1.0144 | 1.0377 | 1.1153 |
| 30%         | 1.0173 | 1.0383 | 1.1413 |

---
---

## 🧠 Citation

```bibtex
@article{ghadami2024trideeprec,
  title={TriDeepRec: A Hybrid Deep Learning Approach to Content- and Behavior-Based Recommendation Systems},
  author={Ghadami, Amirhossein and Tran, Thomas},
  journal={User Modeling and User-Adapted Interaction},
  year={2024},
  publisher={Springer},
  doi={10.1007/s11257-024-09418-w}
}