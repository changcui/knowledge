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

## torch.nn.functional

- 归一化

  `normalize(a, dim=2)`对第2维进行归一化



