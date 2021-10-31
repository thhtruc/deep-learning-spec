# **PCA**

**Principal Component Analysis** is a dimensionality-reduction method that is often used to reduce the dimensionality of large data sets by transforming a large set of variables into a smaller one that still contains most of the information in the large set.

1. *Standardization*: tandardize the range of the continuous initial variables so that each one of them contributes equally to the analysis.

              z = (value - mean) / standard deviation
              
2. *Compute covariance matrix*: understand how the variables of the input data set are varying from the mean with respect to each other, or in other words, to see if there is any relationship between them.
3. *Compute the eigenvectors and eigenvalues of covariance matrix* to identify the principal components.
4. *Obtain projected points in low dimension*.
5. *Project data to selected eigenvectors*.
6. *Pick K eigenvectors with highest eigenvalues*.
