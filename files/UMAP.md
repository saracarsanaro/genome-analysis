A Basic Example of a UMAP
```install.packages("umap")
library("umap")
training_data ← iris[,1:4] #prepare a training dataset
real_data ← training_data + matrix(rnorm(nrow(training_data)*4,0,0.1), ncol=4) #real data (training dataset with some fluctuations)
view(real_data)
training_data_umap_results ← umap(training_data) #umap on training data
real_data_umap_results ← predict(training_data_umap_results, real_data) #predict the clustering of real_data based on training data's umap results
#ggplot for visualization
X_values_umap ← real_data_umap_results[,1]
Y_values_umap ← real_data_umap_results[,2]
XY_values_umap_as_dataframe ← data.frame(X_values_umap, Y_values_umap)
library(ggplot2)
ggplot(data = XY_values_umap_as_dataframe, aes(x=X_values_umap, y=Y_values_umap)) + geom_point()```
