## Introduction

- Variograms are sensitive to outliers and strongly influenced by marginal distributions. So our inference will change a lot depending on what we assume the marginals are?


- Copulas describe dependence between random variables independently of their marginals.


- Spatial modeling frequently relies on the Gaussian assumption which isn’t met with environmental data
- This paper generalizes the Bardossy paper to allow for covariates in spatial copula models and for discrete marginals

## Section 2 Copulas

- From Sklar a Copulas is an n-dim distribution on the unit cube with uniform marginals. By Sklars theorem though a copula is also the function linking the marginals to the joint. Can be constructed by applying the joint to the inverse of the marginals if both are known. Otherwise I think we would choose a copula family and estimate which one fits the observed data?


- Variables are independent if the copula is the product copula

## Section 3 Spatial Modeling with Copulas

- Assume a second-order stationary field in R^2
- let Fz denote a univariate spatial process. By SOS and Sklar we can model the multivariate distribution of x1..xn by setting F1=…=Fn and using spatial copula Ch. h representing the distance between 2 points. 
- Thus the copula describes the spatial dependence between all quantiles of the field and not just mean dependence like the variogram
- Some requirements on a useful spatial copula
  1. Symmetric
  2. A function of h alone
  3. Converges to the product copula as h -> inf  (independence)
  4. converges the Frechet upper bound as h -> 0 (no nugget)


- Gaussian random fields are the most important class of random fields (used in modeling). They are a special case where the copula is the Gaussian Copula with Gaussian marginals (and hence gaussian joints). All of the requirements of a spatial copulas are met if we assume the covariance follows a known parametric model such as the matern model.
- The disadvantages through are that they have zero tail dependence even if the variables are highly correlated and the copula is radially symmetric (isotropic) and hence too restrictive.
- Bardossy introduces a non-gaussian copula family constructed from non-central X^2. Another suggestion is to use elliptical copulas but they can’t be described by h and are therefore unsuitable for spatial.
- Liebscher instead constructs copulas as the product of known copulas applied to monotonic transformations g(u) of the variables. With the restriction that the product of the g(u) = u.
- Commonly the gaussian copula is used so that all the properties of a spatial copula are inherited. These resulting product copulas though are non-gaussian, have tail dependence, are radially asymmetric, etc once the covariance of each known copula has been parameterized.
- in order to incorporate spatial trend we cannot assume all marginals are identical. Instead we assume each Fz belongs to the class of Exponential Dispersion models. The mean can then be parameterized as a surface with a link function.

## Section 4 Parameter Estimation

- There are 3 types of parameters to estimate:
  1. Theta - the covariance model parameters for the joint
  2. Beta - the mean parameters for each marginal
  3. Lambda - the copula parameters (monotonic function parameters)

- geometric anisotropy can be handled with additional coordinate transformation parameters