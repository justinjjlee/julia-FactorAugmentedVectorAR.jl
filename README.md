# julia-FactorAugmentedVectorAR.jl
Implementation of Factor-augmented Vector Autoregressive process (FAVAR(p)) based on [Bernanke, Boivin, and Eliasz (2005)](https://academic.oup.com/qje/article-abstract/120/1/387/1931468)

```julia
import Pkg

using LinearAlgebra, Distributions, Statistics, MultivariateStats;
using ProgressMeter;
using Gadfly, Colors;

include('func_FAVAR.jl');
```

Author: Justin J. Lee (justin.j.lee3411@gmail.com)
