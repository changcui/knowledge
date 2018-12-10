#### Attention Transfer

考虑选择老师网络中的一些层$i = 1, 2,...,N_L$，以及学生网络中相应的层，对于选定的层$i$，收集每个通道$j$的空间激活值信息向量$\mathbf{a}_{ij}^t$，收集$\mathbf{a}_{ij}^t$形成$A_i^t$，对于学生网络也形成相应的$\mathbf{a}_{ij}^s$和$A_i^s$。
​	然后给定一个映射$\mathbf{f}(A_i)$将$A_i$映射成一个向量，优化下面的损失函数：
$$
	\mathcal{L}_{AT} = \mathcal{L}_{CE}(\mathbf{y}, \delta(\mathbf{s})) + \beta \sum_{i=1}^{N_L}\|\frac{\mathbf{f}(A_i^t)}{{\|\mathbf{f}(A_i^t)\|}_2} - \frac{\mathbf{f}(A_i^s)}{{\|\mathbf{f}(A_i^s)\|}_2}\|
$$
​	其中$\beta$是超参数，对于$\mathbf{f}(A_i)$的选择，推荐使用$\mathbf{f}(A_i) = \frac{1}{N_{A_i}}\sum_{j=1}^{N_{A_j}}{\mathbf{a}_{ij}}^2$。换句话说，这个损失是用来衡量老师网络和学生网络所选层生成的空间注意力图之间的差别。第一项是标准的交叉熵误差，第二项误差当老师网络和学生网络在所选层的空间注意力图相似的时候比较小，也就是说老师网络将自己在特定层的注意力传递给学生网络，而不是直接将自己的特征传递出去。

#### Knowledge Distillation

​	把两个概率向量$\mathbf{p}$和$\mathbf{q}$之间的交叉熵表示为$\mathcal{L}_{CE}(\mathbf{p}, \mathbf{q})=-\Sigma_{k}p_klogq_k$，假设我们有一个数据集，数据集中的一个元素$\mathbf{x}$，拥有对应的one-hot表示的标签$\mathbf{y}$。给定一个$\mathbf{x}$，有一个老师网络$\mathbf{t} = teacher(\mathbf{x})$输出结果表示为$\mathbf{t}$,同样也有一个学生网络$\mathbf{s} = student(\mathbf{x})$输出结果表示为$\mathbf{s}$，要使用知识蒸馏，需要最小化下面的损失函数：
$$
	\mathcal{L}_{KD} = (1 - \alpha)\mathcal{L}_{CE}(\mathbf{y}, \delta(\mathbf{s})) + 2\alpha T^2 \mathcal{L}_{CE}(\delta(\frac{\mathbf{t}}{T}), \delta(\frac{\mathbf{s}}{T}))
$$
​	其中$\delta(.)$是 softmax 函数，$T$是蒸馏的温度，是一个超参数，$\alpha$也是个超参数来控制两项的占比。第一项是标准的交叉熵误差，是标签和学生网络输出之间的误差，用来让学生网络向标签学习，第二项是学生网络输出和老师网络输出之间的误差，目的是让学生网络向老师网络学习。

#### Cheap Convolution

​	Group Conv, Bottleneck, Group Conv + Bottleneck

[Moonshine: Distilling with Cheap Convolutions](https://arxiv.org/abs/1711.02613)