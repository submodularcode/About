
### submodular ###
*submodular* is a python library of **high-performance MPI-parallelized implementations of state-of-the-art algorithms for submodular maximization** written by **Adam Breuer**. It also includes an **experimental comparison framework** to compare algorithms, as well as **additional simple-to-run serial (non-parallel) implementations**. The submodular library can easily scale up to leverage thousands of processors on Amazon’s AWS. It also includes examples that show how to find influential people in large social networks with e.g. millions of users, as well as other classic objectives.


![Map of FAST country usage](https://images.squarespace-cdn.com/content/v1/5ca4254a8ab6dd000136f216/1591498255086-5V12C5SW2YPT5PUMPGA7/ke17ZwdGBToddI8pDm48kL1pTN9lINIBvBTJtDo0hOxZw-zPPgdn4jUwVcJE1ZvWQUxwkmyExglNqGp0IvTJZUJFbgE-7XRK3dMEBRBhUpxBNMYAfPHpb0MbpADVzMmqtLmbFyxlbZXYqOhN4i99ptjmY55CGMPQWiUjSOqbHYs/FAST+1+processor+runtime.png?format=150w)

The *submodular* repo also has GitHub Actions and Teams enabled to make it easy to integrate *submodular* into your workflow.

For details and source, please see instructions at www.adambreuer.com/code. I'm happy to provide a quick **tutorial and examples for running *submodular* on AWS in parallel** or to discuss how to **use *submodular* for your research**. Email me at **breuer `at' harvard.edu**


When citing this libary, please cite our paper:
https://arxiv.org/abs/1907.06173

 - Breuer, A., Balkanski, E., & Singer, Y. "The FAST Algorithm for Submodular Maximization". *International Conference on Machine Learning (ICML) 2020.*


![Map of FAST country usage](https://images.squarespace-cdn.com/content/v1/5ca4254a8ab6dd000136f216/1596839373789-A8DBI9V9H39QZWC6VUNV/ke17ZwdGBToddI8pDm48kD4cM2MDJLBHpNoch_tq4e8UqsxRUqqbr1mOJYKfIPR7LoDQ9mXPOjoJoqy81S2I8N_N4V1vUb5AoIIIbLZhVYwL8IeDg6_3B-BRuF4nNrNcQkVuAT7tdErd0wQFEGFSnIQUvZYQlNhkJjIwPyCHH7PmcYfWGP99ac2HMyu2zsgqbwjHYCUNbcA8I4YYe53tTw/image-asset.png?format=2500w)


### Classic Submodular Maximization Algorithms: ###

**Top K** (Returns the solution containing the top k elements with the highest marginal contribution to the empty set.).
  - topk()
  - topk_parallel()

**Random** (Returns the value of a random set of size k.).
  - randomksolutionval()
  - randomksolutionval_parallel()

**Greedy** (Nemhauser 1978).
  - greedy()
  - greedy_parallel()
    
**Lazy Greedy** (Minoux 1978).
  - lazygreedy()


### State-of-the-art Submodular Maximization Algorithms: ###

**FAST** (Breuer, Balkanski, and Singer, ICML 2020).
  - FAST_knowopt() -- runs FAST (non-parallel) for a single guess of the optimal solution value (OPT)
  - FAST_guessopt() -- runs FAST (non-parallel) when the optimal solution value (OPT) is unknown
  - FAST_knowopt_parallel() -- runs FAST in parallel for a single guess of the optimal solution value (OPT)
  - FAST_guessopt_parallel() -- runs FAST in parallel when the optimal solution value (OPT) is unknown

**Stochastic Greedy** (Mirzasoleiman et al., 2015).
  - stochasticgreedy()
  - stochasticgreedy_parallel()

**Lazier Than Lazy Greedy** (Mirzasoleiman et al., 2015).
  - lazierthanlazygreedy()
  - lazierthanlazygreedy_parallel()

**Amortized Filtering** (Balkanski et al., SODA 2019).
  - amortizedfiltering()
  - amortizedfiltering_parallel()
  - amortizedfilteringOPTS() -- runs amortizedfiltering over various guesses for OPT
  - amortizedfilteringOPTS_parallel() -- runs amortizedfiltering_parallel over various guesses for OPT

**Adaptive Sequencing** (Balkanski, et al., STOC 2019).
  - adapt_sequencing_knowopt_parallel()
  - adapt_sequencing_guessopt_parallel() -- runs Adaptive Sequencing in parallel when the optimal solution value (OPT) is unknown

**Exhaustive Maximization** (Fahrbach et al. Algorithm 3 from "Submodular Maximization with Nearly Optimal Approximation, Adaptivity and Query Complexity").
  - exhaustivemax()
  - exhaustivemax_parallel()

**Binary Search Maximization** (Fahrbach et al. Algorithm 4 from "Submodular Maximization with Nearly Optimal Approximation, Adaptivity and Query Complexity").
  - binseachmax_parallel()

**Randomized Parallel Greedy** (Chekuri et al. 2019, randomized-parallel-greedy for cardinality constraints algorithm from Figure 2 p. 12 of "Submodular Function Maximization in Parallel via the Multilinear Relaxation").
  - randparagreedy()
  - randparagreedy_parallel()
  - randparagreedyOPTS() -- runs randparagreedy() over multiple guesses for OPT
  - randparagreedyOPTS_parallel() -- runs randparagreedy_parallel() over multiple guesses for OPT


### Objective functions: ###
We include several canonical submodular objective functions, such as:
- **Movie Recommendation;**
- **Network Max Cover;**
- **Revenue Maximization on YouTube;**
- **Influence Maximization;** 
- **Traffic Sensor Placement.**
