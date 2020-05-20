# 对比赛题目的理解

### 比赛要求

从SVHN数据库中找出尽可能多地找出字符位置并尽可能准确地识别这些字符。



### 思路

这个比赛可以看作一个完整的项目。根据 "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow: Concepts, Tools, and Techniques to Build Intelligent Systems"的Appendix B: Machine Learning Project Checklist[1]. 我们可以按照这个checklist去对应地完成每个项目步骤。



1. ###### Frame the problem and look at the big picture.

   完成比赛要求，尽可能地获取高分。

   

2. ###### Get the data.

   经过处理的数据集已由比赛组织方提供，从而降低比赛难度以适应初学者。

   

3. ###### Explore the data to gain insights.

   组织方提供的图片是经过处理后的SVHN数据集，这些图片包含了不同位数长度的门牌号码，即不同长度的0-9组成的一串数字。

   

4. ###### Prepare the data to better expose the underlying data patterns to Machine Learn‐ ing algorithms.

   数据需要处理才能“投喂”给模型去训练和识别。

   找出同一张图片所有的数字所在位置，进行分隔或者其它手段处理（比赛组织方已给出包含数字位置的json文件）。

   在这些过程还需要考虑把图片转成计算机可处理的矩阵或张量的存储模式。

   

5. ###### Explore many different models and short-list the best ones.

   比较不同的模型，可以考虑使用小规模数据集去快速比较几种备选的神经网络或机器学习算法（CNN，SVM等），从而选出最佳的算法。同时也可以考虑使用已经训练好的AlexNet或者ImageNet模型去加速训练。

   

6. ###### Fine-tune your models and combine them into a great solution.

   根据实际情况去微调模型，同时多种方式进行validation，从而避免过拟合。如果可能，可以考虑AutoML的算法。

   

7. ###### Present your solution.

   记录下自己的所有步骤、所用的数学原理和学习心得等。把结果放到csv文件中并提交到比赛平台。

   

8. ###### Launch, monitor, and maintain your system.

   根据比赛平台返回的得分，不停地改进和测试，从而得出分数更高的算法模型。此后，如有精力，可以进行提高算法鲁棒性，提速算法等改进尝试。

