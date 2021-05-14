```R
training_data ← iris[,1:4] #prepare a training dataset
real_data ← training_data + matrix(rnorm(nrow(training_data)*4,0,0.1), ncol=4) #real data (training dataset with some fluctuations)
view(real_data)
library(ggplot2)
PCA_results ← prcomp(perturbed.embedding)
X_values_PCA ← PCA_results$x[,1]
Y_values_PCA ← PCA_results$x[,2]
XY_values_PCA_as_dataframe ← data.frame(X_values_PCA, Y_values_PCA)
ggplot(data = XY_values_PCA_as_dataframe, aes(x=X_values_PCA, y=Y_values_PCA)) + geom_point()
```
