# Recommendation Algo Notes


## 1 Background
The repository contains models in personalized recommendation
    , with simple implementation with PyTorch
    , toolkits for file parsing, sampling, and evaluation.

Detailed notes on models are available in my Notion attached.


## 2 Requirements
pytorch >= 1.10.0
numpy >= 1.22.3


## 3 Models Covered
### 3.1 Matrix Factorization based 
- **`Funk SVD`**, **`Biased SVD`**: Koren, Y., Bell, R., & Volinsky, C. (2009). Matrix factorization techniques for recommender systems. Computer, 42(8), 30-37.
  - `Funk SVD` model users and items into latent vectors, and estimate rating via their inner product. Minimizing RMSE between estimated and observed ratings to achieve optimization.
  - `biased SVD` add user, item, and global bias over Funk SVD.
 
- **`PMF`**, **`Logistic PMF`**, **`Constrained PMF`**: Mnih, A., & Salakhutdinov, R. R. (2007). Probabilistic matrix factorization. Advances in neural information processing systems, 20.
  - `PMF` add normal priors over FunkSVD, assuming latent vectors are normally distributed.
  - `Logistic PMF` treats the inner product as score, and further project that score with sigmoid function to approximate the sclared ground truth.
  - `Constrained PMF`

### 3.2 Ranking based Model
- **`BPR`**: Rendle, S., Freudenthaler, C., Gantner, Z., & Schmidt-Thieme, L. (2012). BPR: Bayesian personalized ranking from implicit feedback. arXiv preprint arXiv:1205.2618.

### 3.3 Deep Neural Network based
- **`User-based AutoEncoder`**, **`Item-based AutoEncoder`**: Sedhain, S., Menon, A. K., Sanner, S., & Xie, L. (2015, May). Autorec: Autoencoders meet collaborative filtering. In Proceedings of the 24th international conference on World Wide Web (pp. 111-112).
  - `User-based AutoEncoder` and `Item-based AutoEncoder` resembles each other. The only difference lies in rating vector from which viewpoint the modle tries to restore from the paritally observed rating vector via encoder-decoder structure.
-  **`NeuMF`**: He, X., Liao, L., Zhang, H., Nie, L., Hu, X., & Chua, T. S. (2017, April). Neural collaborative filtering. In Proceedings of the 26th international conference on world wide web (pp. 173-182).
   - **`NeuMF`**: Stands for Neural Matrix Factorization, a fusion architecture of `GMF` (Generalized Matrix Factorization) and `MLP` (Multiple-Layer Perceptron).
