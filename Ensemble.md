# Ensemble

集成学习是战略性地生成并组合多个模型Model（例如分类器Classifier或专家Expert）以解决特定的计算智能问题的过程。集成学习主要用于提高模型的（分类，预测，函数逼近等）性能，或减少不幸选择不良模型的可能性[1]。



常用的模型集成算法主要可分成两大类[2]：

1. 个体学习器之间存在强的依赖关系且必须串行生成的序列化方法，代表算法有Boosting等；
2. 个体学习器之间不存在强的依赖关系，可同时生成的并行化方法，代表算法有Bagging和Random Forest等。



### Boosting

Boosting的思想是先训练出一个基学习器Base Learner, 然后根据这个基学习器去给予预测错误的样本更大的几率在下一个基学习器里出现，即更重视错误的样本。多次反复进行之后，直到基学习器的数目达到阈值，则将所有的基学习器进行加权结合[2]。

### Bagging

Bagging是bootstrap agrregatting的缩写，其采用的方法是自助采样法bootstrap sampling。它先随机从整体数据集中提取一个样本，然后进行有放回地重复取样$m$次得出数量为$m$的采样集合。需要注意的是这些每次选出的样本即可能之前被选中过，也可能从未被选中过，也就是说有可能是重复的。我们重复上述步骤$T$次，也就是说我们一共会有$T$个含有$m$个样本的小训练集。把这些小的训练集进行训练后得到$T$个基学习器，最后对这些学习器采用投票法（分类任务）或平均法（回归任务）来选出最佳学习器[2]。

### Random Forest

Random Forest (RF)是在以决策树为基学习器构建Bagging的基础上，进一步在Decision Tree的训练过程中引入随机选择。也就是说在RF中，对Decision Tree的每个节点，是先从该节点的属性集合中随机选择一个包含$k$个属性的属性子集，其中 $k \in [1, d] $, $d$为该节点所有属性的数量[2]。



参考文献（资料）：

[1]Robi Polikar (2009) <a href="http://www.scholarpedia.org/article/Ensemble_learning">Ensemble learning</a>. <a href="http://www.scholarpedia.org/">Scholarpedia</a>, 4(1):2776.

[2]  周志华 著. 机器学习, 北京: 清华大学出版社, 2016年1月.



