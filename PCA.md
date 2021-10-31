# **PCA**

**Principal Component Analysis** is a dimensionality-reduction method that is often used to reduce the dimensionality of large data sets by transforming a large set of variables into a smaller one that still contains most of the information in the large set.

1. *Standardization*: standardize the range of the continuous initial variables so that each one of them contributes equally to the analysis.

              z = (value - mean) / standard deviation
              
2. *Compute covariance matrix*: 
  - A covariance matrix expresses the correlation between the different variables in the data set.
  --> identify heavily dependent variables because they contain biased and redundant information which reduces the overall performance of the model.
    * If the covariance value is negative, it denotes the respective variables are indirectly proportional to each other
    * A positive covariance denotes that the respective variables are directly proportional to each other


3. *Compute the eigenvectors and eigenvalues of covariance matrix*: Eigenvectors and eigenvalues are the mathematical constructs that must be computed from the covariance matrix in order to determine the principal components of the data set.
  - Principal components are the new set of variables that are obtained from the initial set of variables. 
  - The principal components are computed in such a manner that newly obtained variables are highly significant and independent of each other. 

4. *Computing the Principal Components*:
  - When we have computed the Eigenvectors and eigenvalues 
  --> order them in the descending order (**the eigenvector with the highest eigenvalue is the most significant <--> the first principal component**).
  - The principal components of lesser significances can thus be removed in order to reduce the dimensions of the data.
  - The final step in computing the Principal Components is to form a matrix known as the feature matrix that contains all the significant data variables that possess maximum information about the data.
  
5. *Reducing the dimensions of the data set*.
  - Re-arrange the original data with the final principal components which represent the maximum and the most significant information of the data set.
 -->  multiply the transpose of the original data set by the transpose of the obtained feature vector.

