# 数据读取与数据扩增

### 数据读取

在做AI项目中，我们可能需要处理数以万记，甚至亿计的数据。这时候如何在有限的硬件资源中高效地读取数据是一个我们不可忽视的问题。

读取数据我们需要考虑数据本身的格式（比如数据是图片、是文本还是语音；图片中的物体数量、文本的长度和语音文字的长度是不是相同），还需要考虑硬件设备（比如内存的大小，GPU的通道数，CPU的通道数等）等因素。



Tensorflow的读取机制可参考[1].



PyTorch主要是应用了ImageFolder类与DataLoader类去读取数据，具体可参考[2]。





### 数据扩增

根据BAIR的介绍， 数据扩增的定义如下：

Data augmentation is a strategy that enables practitioners to significantly increase the diversity of data available for training models, without actually collecting new data[3].



我们可以从其定义中得出数据扩增并不实际采集新的数据而是通过对原有数据的变形从而增加数据的样本数和多样性。数据扩增可以增加训练集的样本，同时也可以有效环节模型过拟合的情况，也可以给模型带来的更强的泛化能力[4]。

数据扩增多用于计算机视觉领域的项目。数据扩增方法可分为单样本扩增和多样本扩增[5]。

单样本扩增包括：图像翻转、图像旋转、图像扭曲、图像仿射变换、图像缩放、图像压缩、图像随机crop、图像随机padding、图像对比度调整、亮度调整、色度调整、饱和度调整、色彩抖动、添加噪声、图像模糊、图像区域随机擦除、风格转换、生成对抗网络生成等。

多样本扩增包括：SamplePairing和mixup，二者思路很相近。



参考文献：

[1]. 知乎用户何之源, *十图详解tensorflow数据读取机制（附代码）*,  https://zhuanlan.zhihu.com/p/27238630, Jun. 2017.

[2]. 知乎用户Sherlock, *PyTorch实现自由的数据读取*, https://zhuanlan.zhihu.com/p/30385675, Oct. 2017.

[3]. Daniel Ho, Eric Liang, Richard Liaw, *1000x Faster Data Augmentation*, https://bair.berkeley.edu/blog/2019/06/07/data_aug/, Sep. 2019.

[4]. 知乎用户阿水, *Kaggle知识点：数据扩增方法*, https://zhuanlan.zhihu.com/p/133270667, Apr. 2020.

[5]. 知乎用户zzq, *图像数据扩增技术*, https://zhuanlan.zhihu.com/p/71140833, Jun. 2019.



