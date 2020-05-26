# 理解CNN中的C

CNN全称是Convolutional Neural Network(s). CNN常用于计算机视觉中图像分析任务。 

CNN也是一种Artificial Neural Network, 但使其有别于传统的DNN和MLP的是其Convolutional Layer。正是Convolutional Layer使CNN在识别图像特征的时候特别出色。





### 卷积核（Filter or Kernel)与卷积操作

可以通过图像的特征去区分和分类图像。图像的特征包括边沿轮廓、形状、纹路、颜色、曲线及图中的物体等。而识别不同的特征通常有不同的卷积核。最常见的卷积核是用于边沿检测，这种卷积核也被称之为edge detector.

除了检测边沿，有的卷积核还可以检测角、方或圆形等。通过一个或多个这样的卷积核，可以进一步检测出一些物品或形状，比如眼睛、耳朵等，甚至还能识别出更复杂的物体或形状，比如区分狗与猫。



下面就其中的原理来展开解释一下卷积核是如何通过卷积操作来达到上述功能的。我们知道图像是由多个像素点组成的，为了简化，我们假设图片是单通道的，也就是灰度图像，其像素亮度级别是0至255，即纯黑是0，纯白是255。

假设我们有一张图片（数字7）如下：

![mnist 7](/Users/lzhong/Downloads/Datasets/MChar/mnist 7.png)



我们把其作normalization后的像素值放到Excel表格中，可以看到上图最白的地方值是1.0。黑色部分是0.0。

![image-20200526222011251](/Users/lzhong/Downloads/Datasets/MChar/image-20200526222011251.png)



如果我们通过以下4个filters去对上图进行卷积操作：

![image-20200526222816601](/Users/lzhong/Downloads/Datasets/MChar/image-20200526222816601.png)

则得到对应的结果分别是：

![image-20200526222902586](/Users/lzhong/Library/Application Support/typora-user-images/image-20200526222902586.png)

我们可以看出第一、三个filters能对横向的轮廓加深其特征；而第二、四个filters则是对纵向有加深作用。



为什么会产生这样不同的作用呢？其实本质上是在图像中找出与filter形状相似的特征。把filter和图片都展开成两个一维向量，然后对他们进行逐步逐步进行点积操作。跟cosine similarity类似，如果两个向量越接近（相似）则其乘积越大，因此可以突出其特征。

![image-20200526223743347](/Users/lzhong/Downloads/Datasets/MChar/image-20200526223743347.png)

进一步说，如果能从把图片和filter都展开成一维向量去理解，那么其实不难理解其跟fully connected layer是相通的，也从而不难理解卷积层是如何进行梯度下降和反向传播的了。