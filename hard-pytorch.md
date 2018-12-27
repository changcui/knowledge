# Pytorch

## Tensor

- 给 Tensor 添加梯度

  `a.requires_grad_()`

- 给 Tensor 去除梯度

  `a.detach_()`

- 查询 Tensor 是否有梯度

  `a.requires_grad return false`

  `a.is_leaf return true `

- 维度置换

  `a.permute(0, 2, 1)` 调换1，2维

- 求范数

  `a.norm(p=2, dim=2)`对第2维求二范数

- 求均值

  `a.mean(dim=2)` 对第2维求平均值

- 收缩维度

  `a.squeeze()`不加参数去除所有是1的维度

- 按标号选择

  `a.index_select(dim=1, b)`但要求 b 必须是1维的，如果是高维的需要 cat

## torch.nn.functional

- 归一化

  `F.normalize(a, dim=2)`对第2维进行归一化

- 全局平均值池化

  `F.adaptive_avg_pool2d(x, (1, 1))`将 NCHW 变成 NC11

- softmax

  `F.softmax(x, dim=1)`在第1维执行 softmax

  `F.log_softmax(x, dim=1)`在第1维执行 log_softmax

- KL 散度

  `F.kl_div(F.log_softmax(a, dim=1), F.softmax(b, dim=1))`计算 KL 散度，注意第1个参数要使用 log_softmax

