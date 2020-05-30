# 模型训练与验证

### 模型训练

模型训练主要包括以下步骤：

1. Get batch from the training set.从Training Set中获取Batch数据；
2. Pass batch to network.将Batch数据传入到神经网络中；
3. Calculate the loss (difference between the predicted values and the true values). 计算损失（预测值和真实值之间的误差）。
4. Calculate the gradient of the loss function w.r.t the network's weights. 计算损失函数的梯度Gradient。
5. Update the weights using the gradients to reduce the loss.使用计算出来的梯度更新权重Weight以减少损失。
6. Repeat steps 1-5 until one epoch is completed.重复步骤1-5，直到完成一个Batch。
7. Repeat steps 1-6 for as many epochs required to reach the minimum loss.重复步骤1-6，直至达到最小损失Loss所需的epoch数。



### 验证

为什么需要验证Validation环节呢？最主要的原因是我们要防止过拟合Overfitting的发生，即训练出来的模型在Training Set中表现良好，但是在Training Set以外的数据错误率很高。所以我们希望有一种方法可以判断我们训练出来的模型是不是真的那么好, 而验证Validation正是用来解决这个问题的。Validation的常用方法包括：

- Adversarial Validation
- Resubstitution
- Holdout
- K-fold Cross-Validation
- Leave-One-Out Cross-Validation (LOOCV)
- Random Subsampling
- Bootstrapping
- ...



参考资料：

[1] https://deeplizard.com/learn/video/0VCOG8IeVf8

[2] https://deeplizard.com/learn/video/Zi-0rlM4RDs

[3] https://dzone.com/articles/machine-learning-validation-techniques