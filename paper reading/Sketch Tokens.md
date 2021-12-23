# Sketch Tokens: A Learned Mid-level Representation for Contour and Object Detection
作者：Joseph J. Lim、 C. Lawrence Zitnick、Piotr Doll ́ar 2013 CVPR
### 文章创新点
* 在划分轮廓时，通常是二分类，即一个像素点要么是边缘点，要么不是，该文将问题转换为多分类问题，用随机森林作为分类器，输出的像素为哪个类的概率，但是没有“nocontour”的概率，其概率为1-其他类的概率之和。
* 将人工标注的轮廓信息作为多类分类的类标，本文基于daisy特征利用k-means算法得到有限个类标。

## Introduction
mid的意义是相对与图像的低级特征和高级特征的，low-level是pixel-based，high-level是基于人类对于图像的concept，本文提出了一种基于学习和局部边缘探测的中级特征的新方法，并证明了该方法在自底向上和自顶向下的任务中都可行。本文所采取的特征，叫素描令牌，捕获局部边缘结构。素描令牌的类的范围从标准形状 （如直线和交叉点）到更丰富的结构（如曲线和并行线的集合）如下图所示。
<div align=center>
<img src= "https://img-blog.csdn.net/20140404094502656?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZmFuamluZ18xOTkx/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center" width=200/>
</div>

## Sketch Token
我们的目标是定义一组可以代表图像中的各种局部边缘结构的token类。首先将人工标定好的binary图像(人工标注的详细步骤参考*A database of human segmented natural images and its application to evaluating segmentation algorithms and measuring ecological statistics.*)，按照一个35*35的区域提取patch，每个区域中心需要正好在轮廓上，如此，我们可以得到很多的patch，也即是很多的轮廓形状。那么如何将它们分为有限的分类呢？如何分是合理呢？文章用到了k=150的Kmeans算法，那么要用Kmeans，就要有一个距离度量，文章使用的是Daisy特征。\
那么有了合适的类标，即是sketch token，一个样本是一张RGB图像上的一个patch，然后对应的Binary轮廓图像上的patch对应的sketch token。那么接下来怎么训练呢？文中是对RGB图像提取两组feature：
1. features directly indexing into the channels：color channels, gradient magnitude cahnnels(Gaussian Blur), oriented magnitude channels
2. self-similarity features：

接下来文章用随机森林进行分类，分类的目标是各sketch token的possibility。\
\
**模型分类方法**：这样对图像每一个像素进行分类获得各token的possibility以及non-contour的possibility，然后用non-maximal suppression来找到最大响应的contour。
