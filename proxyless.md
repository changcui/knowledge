# ProxylessNAS: Direct Neural Architecture Search on Target Task and Hardware

Han Cai, Ligeng Zhu, Song Han

### Introduction

In this paper, we present ProxylessNAS that can directly learn the architectures for large-scale target tasks and target hardware platforms. We address the high memory consumption issue of differentiable NAS and reduce the computational cost (GPU hours and GPU memory) to the same level of regular training while still allowing a large candidate set. ![1](/Users/cc/Desktop/1.png)

We formulate NAS as a path-level pruning process. Specifically, we directly train an over-parameterized network that contains all candidate paths (Figure 2). During training, we explicitly introduce architecture parameters to learn which paths are redundant, while these redundant paths are pruned at the end of training to get a compact optimized architecture. In this way, we only need to train a single network without any meta-controller (or hypernetwork) during architecture search.![2](/Users/cc/Desktop/2.png)

Thus, GPU memory-wise, we binarize the architecture parameters (1 or 0) and force only one path  Normal Train NAS  DARTS & One-shot Proxyless (Ours)  to be active at run-time, which reduces the required memory to the same level of training a compact model.  

Furthermore, to handle non-differentiable hardware objectives(using latency as an example) for learning specialized network architectures on target hardware, we model network latency as a continuous function and optimize it as regularization loss.Additionally, we also present a REINFORCE-based (Williams, 1992) algorithm as an alternative strategy to handle hardware metrics.

### Method



