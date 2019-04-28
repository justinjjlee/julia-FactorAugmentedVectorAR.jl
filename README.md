# julia-FactorAugmentedVectorAR.jl
Implementation of Factor-augmented Vector Autoregressive process (FAVAR(p)) based on [Bernanke, Boivin, and Eliasz (2005)](https://academic.oup.com/qje/article-abstract/120/1/387/1931468)

```julia
import Pkg;
Pkg.update();

using LinearAlgebra, Distributions, Statistics, MultivariateStats;
using ProgressMeter;
using Gadfly, Colors;

include('func_FAVAR.jl');
```
Test dataset is downloaded from Federal Reserve Bank of St. Louis - [Federal Reserve Economic Database (FRED) - FAVAR-1](https://research.stlouisfed.org/pdl/763)

```julia
y = open("bernanke_etal_2005_qje.txt");   # Data from Bernanke et al. (2005)
kₘ = 14;                                  # Number of variables in the main - VAR
yₘ = y[:, 1:kₘ];                          # Variables in the macro block
yₚ = y[:, (kₘ + 1):end];                  # Variables in the factor structure

# Other paramters needed.;
p = 12;                                   # Lag order
ζ = 3;                                    # Number of factors to be extracted

# Coefficient matrix, residuals, and covariance matrix.;
# (In order): coefficient, residual, covariance matrix - residual, factors, factor loadings.;
𝚩, 𝞄, 𝝨, 𝔽₁, ℾ₁ = func_favar(yₘ, yₚ, p, ζ);
```

Author: Justin J. Lee (justin.j.lee3411@gmail.com)
