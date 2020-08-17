# SAIC
Single cell RNA-seq analysis with iterative clustering (SAIC) is a method to identify subgroups and signature genes in single cell RNA-seq data. 

1. Installation: You can run the following command to install the package:
                    R CMD INSTALL SAIC-1.0.tar.gz
                    
2. package dependency: You need R package "cluster", "cclust", "clusterSim", and "parallel". please install these packages before installing SAIC.

3. To set up a run of choosing the best parameters, you can start with the following example scripts:

		cluster <- c(2:10)
		pvalue <- c(1e-7,1e-6,1e-5,1e-4,1e-3,1e-2)	
		matrix_kmeans <- para_select(data, cluster, pvalue, method="kmeans")
		result <- do.call("rbind", matrix_kmeans)
    

  	You can then either plot or observe the result matrix to decide what is the best combination of parameters. For example, 

    	result_7_03 <- cluster_analysis(data = data, cluster_number = 7, pvalue = 1e-3, method="kmeans")
