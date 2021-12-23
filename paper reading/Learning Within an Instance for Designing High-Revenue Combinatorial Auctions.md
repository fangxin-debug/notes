# Learning Within an Instance for Designing High-Revenue Combinatorial Auctions

作者：Maria-Florina Balcan1,Siddharth Prasad1andTuomas Sandholm

期刊：IJCAI-21

### **摘要**

我们发明了一个新的机制，可以为有限的supply获得更多的拍卖收益。

我们的机制在一个实例中learning，它概括并改进了之前研究过的随机采样机制。它首先从bidders(竞选者)中采样出一个参与小组(participatory  group)，然后再从剩余的bidders中采样出几个学习小组，从这几个学习小组学习到一场高收益的拍卖并且将这个拍卖在参与小组上运行。*先前的工作对随机采样机制主要集中在无约束供应（supply）上*（**前人的工作**）。*有限的供应带来了一个非常有挑战性的问题，因为分配给投标人的资源必须是可行的*（**工作的难点**）。

**他们的工作**：

我们证明了一个我们新机制的在市场缩水场景下的表现结果，并且创造了一个新的复杂度衡量方法我们称为部分差异（partition discrepancy）

(*We prove guarantees on the performance of  our  mechanism  based  on  a  market-shrinkage term and a new complexity measure we coin partition discrepancy.*)

Partition Discrepancy可以测量机制类的内部复杂度同时也可以衡量投标者集合的一致性。然后，我们引入了新的拍卖类别，这些类别的参数化方式不依赖于参与竞标者的数量，并为这些类别证明了strong guarantees.

我们展示了如何通过利用实际高效的例程来解决获胜者确定问题，从而有效地实施我们的机制。最后，我们展示了当学习小组(learning group)的数量受到限制时，如何利用结构性收入最大化来决定在我们的框架下使用什么拍卖类别。

