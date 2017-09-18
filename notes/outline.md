## Goal from O3

Develop multivariate spatial copula models that can account for non-Gaussianity, teleconnections and other non-stationarity to jointly model the random processes of temperature, precipitation and proxies, and then use this model to reconstruct the spatially varying bivariate distribution of temperatures and precipitation given the proxy data. The CFR derived from O2 will be used in this objective to help with the nonidentifyability issue.



### Steps

1. Model the covariance structure in the Gaussian Copula
   1. Model time with an AR process
   2. Model space with SRE (Spatial Random Effects)
      1. Requires Estimating random effects AND spatial basis functions
2. Predict Precipitation and Temperature at new spatial locations
   1. Given the data and some proxy value at S estimate the conditional distribution of Precip and Temp at S
   2. Calculate the predictive density at S with a transformation of the conditional



### Questions

1. How can we be using a Guassian copula if the marginals are non guassian?
   1. https://stats.stackexchange.com/questions/114786/in-definition-of-gaussian-copula-does-the-marginals-also-have-to-be-gaussian
   2. ​