# LLE-Manifold-Learning
Locally Linear Embedding (LLE) sits under the Unsupervised branch of Machine Learning within the group of dimensionality reduction algorithms.
How does Locally Linear Embedding work?
The high-level steps
Similar to Isomap, LLE combines several steps to produce the lower-dimensional embedding. These are:
1. Use a KNN approach to find the k nearest neighbors of every data point. Here, “k” is an arbitrary number of neighbors that you can specify within model hyperparameters.
2. Construct a weight matrix where every point has its weights determined by minimizing the error of the cost function shown below. Note that every point is a linear combination of its neighbors, which means that weights for non-neighbors are 0.

3- Find the positions of all the points in the new lower-dimensional embedding by minimizing the cost function shown below. Note, here we use weights (W) from step two and solve for Y. The actual solving is performed using Partial Eigenvalue Decomposition.
LLE variants:
You should be aware of a few LLE variants, which improve upon the original setup. However, note that these improvements come at the cost of efficiency, making the algorithm slower. Here is how scikit-learn describes these variants:
•	Modified LLE (MLLE) — One well-known issue with LLE is the regularization problem. A way to address it is to use multiple weight vectors in each neighborhood. This is the essence of MLLE.
•	Hessian LLE (HLLE)— Hessian Eigenmapping is another method of solving the regularization problem of LLE. It revolves around a hessian-based quadratic form at each neighborhood used to recover the locally linear structure.
The best method to model manifolds is to treat the curved surface as being composed of several neighborhoods. If each data point manages to preserve the distance not with all the other points but only the ones close to it, the geometric relationships can be maintained in the data.
