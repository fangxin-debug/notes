# Spatio-Temporal Graph Convolutional Networks: A Deep Learning Framework for Traffic Forecasting

*作者是北大的几名学生*

研究问题：交通问题的主要因素是**速度、流量和密度**，交通预测分为两类，短期的（5-30分钟），长期的（30分钟以上），大多数统计方法，如线性回归、自回归及其变种在短期预测表现的还行。

核心思想：空间信息用图表示，时间序列用完全卷积来提取特征

> 谱图卷积

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211122201412477.png" alt="image-20211122201412477" style="zoom: 50%;" />

STGCN网络结构

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211122202003494.png" alt="image-20211122202003494" style="zoom: 67%;" />

ChetbyNet

不知道为啥又讲回来了

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211122203403898.png" alt="image-20211122203403898" style="zoom:50%;" />

时序维度用Gated CNNs

不用RNN的原因是因为效果一般，而且很耗时。

**本文贡献**

- 该文研在交通研究中第一次应用纯卷积层（TCN）来同时从图结构的时间序列中提取时空信息。
- 该文提出了一个新的由时空块组成的神经网络结构。由于这个架构中是纯卷积操作，它比基于RNN的模型的训练速度快10倍以上，而且需要的参数更少。这个架构可以让我们更有效地处理更大的路网。
- 实验在两个真实交通数据集上验证了提出来的网络。这个实验显示出我们的框架比已经存在的在多长度预测和网络尺度上的模型表现的更好

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201107130657403.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3lpbHVsdnhpbmc=,size_16,color_FFFFFF,t_70#pic_center)

