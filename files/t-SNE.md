```training_data ← iris[,1:4] #prepare a training dataset
real_data ← training_data + matrix(rnorm(nrow(training_data)*4,0,0.1), ncol=4) #real data (training dataset with some fluctuations)
view(real_data)
#t-SNE#
library(Rtsne), library(ggplot2)
tSNE_results ← Rtsne(perturbed.embedding, header=T)
X_values_tsne ← tSNE_results$Y[,1]
Y_values_tsne ← tSNE_results$Y[,2]
XY_values_tsne_as_dataframe ← data.frame(X_values_tsne, Y_values_tsne)
ggplot(data = XY_values_tsne_as_dataframe, aes(x=X_values_tsne, y = Y_values_tsne)) + geom_point()```
