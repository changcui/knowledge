#### Contribution



#### Attention Transfer

考虑选择老师网络中的一些层，以及学生网络中相应的层，对于选定的层，收集每个通道的空间激活值信息向量，对于学生网络也形成相应的。
然后给定一个映射将矩阵映射成一个向量，优化下面的损失函数：
$$
\mathcal{L}_{AT} = \mathcal{L}_{CE}(\mathbf{y}, \delta(\mathbf{s})) + \beta \sum_{i=1}^{N_L}\|\frac{\mathbf{f}(A_i^t)}{{\|\mathbf{f}(A_i^t)\|}_2} - \frac{\mathbf{f}(A_i^s)}{{\|\mathbf{f}(A_i^s)\|}_2}\|
$$
其中\beta是超参数，对于\mathbf{f}(A_i)的选择，推荐使用$ \mathbf{f}(A_i) = \frac{1}{N_{A_i}}\sum_{j=1}^{N_{A_j}}{\mathbf{a}_{ij}}^2 $。换句话说，这个损失是用来衡量老师网络和学生网络所选层生成的空间注意力图之间的差别。第一项是标准的交叉熵误差，第二项误差当老师网络和学生网络在所选层的空间注意力图相似的时候比较小，也就是说老师网络将自己在特定层的注意力传递给学生网络，而不是直接将自己的特征传递出去。

#### Cheap Convolution

Group Conv, Bottleneck, Group Conv + Bottleneck.

[Moonshine: Distilling with Cheap Convolutions](https://arxiv.org/abs/1711.02613)