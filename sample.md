# Fully Convolutional Networks for Semantic Segmentation

论文：[Fully Convolutional Networks for Semantic Segmentation](C:\Users\fangxin\Desktop\论文\Long_Fully_Convolutional_Networks_2015_CVPR_paper.pdf)(2015 CVPR)

作者：Jonathan Long   Evan Shelhamer  Trevor Darrell    -UC Berkeley

图像分割领域的开山之作

1.1 研究成果

- 将分类网络改变为全卷积神经网络，具体包括全连接层转换为卷积层以及通过反卷积进行上采样
- 使用迁移学习的方法进行微调
- 使用跳跃结构使得语义信息和表征信息相结合，产生准确而精细的分割
- FCN证明了端到端、像素到像素训练方式下的卷积神经网络超过了现有语义分割方向最先进的技术
- FCN成为PASCAL VOC上最出色的分割方法，较2011和2012的state-of-the-art分割算法的MIOU提高了将近20%，如图1所示



**难点**：

> 跳跃结构是什么，连接全局信息和局部信息，怎么连接？什么是全局信息和局部信息。

**Introduction & Related work总结：**

在以往的分割方法中，主要有两大类缺点：

(1)基于图像块的分割虽然常见，但是效率低，且往往需要前期或者后期处理(例如超像素、检测框、局部预分类等)

(2)语义分割面临着语义和位置不可兼得的问题。全局信息解决的"是什么"，而局部信息解决的是"在哪里"

为了解决上面这两个问题，本文主要有三个**创新点：**

(1)将分类网络改编为全卷积神经网络，具体包括全连接层转化为卷积层以及通过反卷积进行上采样

(2)使用迁移学习的方法进行微调

(3)使用跳跃连接结构使得语义信息可以和表征信息相结合，产生准确而精细的分割