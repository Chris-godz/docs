## [ torch 参数更多 ]torch.optim.RMSprop

### [torch.optim.RMSprop](https://pytorch.org/docs/stable/generated/torch.optim.RMSprop.html)

```python
torch.optim.RMSprop(params,
                lr=0.01,
                alpha=0.99,
                eps=1e-08,
                weight_decay=0,
                momentum=0,
                centered=False,
                foreach=None,
                maximize=False,
                differentiable=False)
```

### [paddle.optimizer.RMSProp](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/paddle/optimizer/RMSProp_cn.html)

```python
paddle.optimizer.RMSProp(learning_rate,
                    rho=0.95,
                    epsilon=1e-06,
                    momentum=0.0,
                    centered=False,
                    parameters=None,
                    weight_decay=None,
                    grad_clip=None,
                    name=None)
```

PyTorch 相比 Paddle 支持更多其他参数，具体如下：

### 参数映射

| PyTorch                             | PaddlePaddle | 备注                                                                    |
| ----------------------------------- | ------------ | ----------------------------------------------------------------------- |
| params     | parameters           | 表示指定优化器需要优化的参数，仅参数名不一致。                      |
| lr     | learning_rate       | 学习率，用于参数更新的计算。PyTorch 默认为`0.01`，Paddle 无默认值，Paddle 需保持与 PyTorch 一致。          |
| alpha     | rho       | 平滑常数。参数默认值不一致, PyTorch 默认为`0.99`，PyTorch 默认为`0.95`，Paddle 需保持与 PyTorch 一致。     |
| eps       | epsilon        | 保持数值稳定性的短浮点类型值。参数默认值不一致, PyTorch 默认为`1e-08`，PyTorch 默认为`1e-06`，Paddle 需保持与 PyTorch 一致。  |
| weight_decay           | weight_decay     | 表示权重衰减系数。参数默认值不一致, PyTorch 默认为`0`， Paddle 默认为`None`，Paddle 需保持与 PyTorch 一致。         |
| momentum   | momentum   | 动量因子。参数完全一致。                       |
| centered   | centered   | 如果为 True，则通过梯度的估计方差，对梯度进行归一化。参数完全一致。                       |
| foreach     | -           | 是否使用优化器的 foreach 实现。Paddle 无此参数，一般对网络训练结果影响不大，可直接删除                                         |
| maximize           | -     | 根据目标最大化参数，而不是最小化。Paddle 无此参数，暂无转写方式。         |
| differentiable      | -     | 是否应通过训练中的优化器步骤进行自动微分。Paddle 无此参数，一般对网络训练结果影响不大，可直接删除。         |
| -          | grad_clip            | 梯度裁剪的策略。 PyTorch 无此参数，Paddle 保持默认即可。       |
