# Spatial Temporal Graph Convolutional Networks for Skeleton-Based Action Recognition

本文为 AAAI 2018 录用论文「Spatial Temporal Graph Convolutional Networks for Skeleton Based Action Recognition」，香港中文大学提出一种时空图卷积网络，并利用它们进行人类行为识别。这种算法基于人类关节位置的时间序列表示而对动态骨骼建模，并将图卷积扩展为时空图卷积网络而捕捉这种时空的变化关系。

<img src="https://img-blog.csdn.net/20180409001958111?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2ODkzMDUy/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width=250, hieght=250>

这项工作的主要贡献在于三个方面：

* 我们提出 ST-GCN，一个基于图的动态骨骼建模方法，这是首个用以完成本任务的基于图形的神经网络的应用。
* 我们提出了在 ST-GCN 中设计卷积核的几个原则，旨在满足骨骼建模的具体要求。
* 在基于骨骼动作识别的两个大规模数据集上，我们的模型与先前使用的手动分配部分或遍历规则的方法相比，需要相当少的手动设计，实现了更优越的性能。

