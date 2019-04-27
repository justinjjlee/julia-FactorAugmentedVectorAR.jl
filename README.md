# julia-FactorAugmentedVectorAR.jl
Implementation of Factor-augmented Vector Autoregressive process (FAVAR(p)) based on [Bernanke, Boivin, and Eliasz (2005)](https://academic.oup.com/qje/article-abstract/120/1/387/1931468)

```julia
import Pkg

using LinearAlgebra, Distributions, Statistics, MultivariateStats;
using ProgressMeter;
using Gadfly, Colors;

include('func_FAVAR.jl');
```
Test dataset is downloaded from Federal Reserve Bank of St. Louis - [Federal Reserve Economic Database (FRED) - FAVAR-1](https://research.stlouisfed.org/pdl/763)

Author: Justin J. Lee (justin.j.lee3411@gmail.com)
