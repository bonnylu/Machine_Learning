# 聚类

在**无监督学习（unsupervised learning）**中，训练样本的标记信息是未知的，学习的目的是揭示数据的内在性质及规律，为进一步的数据分析提供基础。这类学习任务中研究最多，应用最广的是**聚类（clustering）**。

这一章的内容大致如下：

- **聚类任务**：聚类过程是怎样的？聚类有什么用途？聚类的两个基本问题是什么？

- **性能度量**：聚类的目标是什么？聚类性能度量的两大类指什么？各包含哪些度量指标？

- **距离计算**：距离度量需要满足哪些基本性质？怎样度量有序属性？怎样度量无序属性？相似度度量和距离度量有什么区别？

- **原型聚类**：什么是原型聚类？k均值算法是怎样的？学习向量量化算法是怎样的？高斯混合聚类是怎样的？

- **密度聚类**：什么是密度聚类？DBSCAN算法是怎样的？

- **层次聚类**：什么是层次聚类？AGNES算法是怎样的？

## 聚类任务

聚类试图将数据集中的样本划分为若干个通常是不相交的子集，每个子集称为一个**簇（cluster）**。通常来说每个簇可能对应一些特征，比方说音乐可以聚类成古典音乐、摇滚乐、流行乐等等。但**聚类过程仅产生簇结构，簇对应的概念语义需要使用者来把握和定名**。

简单来说，聚类可以分为两种用途：

- 作为一个单独过程，用于寻找数据内在的分布结构；
- 作为其他学习任务的前驱过程，比方说根据聚类结果定义类标记，然后再进行分类学习；

聚类算法的两大基本问题是**性能度量**和**距离计算**。

## 习题

#### 9.1

> 问：试证明： <img src="http://latex.codecogs.com/gif.latex?p \geq 1" />  时，闵可夫斯基距离满足距离度量的四条基本性质；<img src="http://latex.codecogs.com/gif.latex?0 \leq p \leq 1" />  时，闵可夫斯基距离不满足直递性，但满足非负性、同一性、对称性；<img src="http://latex.codecogs.com/gif.latex?p" />  趋向无穷大时，闵可夫斯基距离等于对应分量的最大绝对距离，即

<img src="http://latex.codecogs.com/gif.latex?\lim_{p \rightarrow + \inf} (\sum_{u=1}^n |x_{iu}-x_{ju}|^p)^{\frac{1}{p}} = \max_u |x_{iu}-x_{ju}|" />



#### 9.2

> 问：同一样本空间中的集合 X 与 Z 之间的距离可通过 “豪斯多夫距离”（Hausdorff distance） 计算：

<img src="http://latex.codecogs.com/gif.latex?dist_H(X,Z) = \max (dist_h(X,Z),dist_h(Z,X))" />

> 其中

<img src="http://latex.codecogs.com/gif.latex?dist_h(X,Z) = \max_{x \in X} \min_{z \in Z} \Vert \mathbf{x} - \mathbf{z} \Vert_2" />

> 试证明：豪斯多夫距离满足距离度量的四条基本性质。

#### 9.3

> 问：试析 <img src="http://latex.codecogs.com/gif.latex?k" />  均值算法能否找到最小化式（9.24）的最优解。



#### 9.4

> 问：试编程实现 <img src="http://latex.codecogs.com/gif.latex?k" />  均值算法，设置三组不同的 <img src="http://latex.codecogs.com/gif.latex?k" />  值、三组不同初始中心点，在西瓜数据集4.0上进行实验比较，并讨论怎样的初始中心有利于取得好结果。



#### 9.5

> 问：基于 DBSCAN 的概念定义，若 <img src="http://latex.codecogs.com/gif.latex?\mathbf{x}" />  为核心对象，由 <img src="http://latex.codecogs.com/gif.latex?\mathbf{x}" />  密度可达的所有样本构成的集合为 X，试证明：X满足连接性（9.39）与最大性（9.40）。



#### 9.6

> 问：试析 AGNES 算法使用最小距离和最大距离的区别。



#### 9.7

> 问：聚类结果中若每个簇都有一个凸包（包含蔟样本的凸多面体），且这些凸包不相交，则称为凸聚类。试析本章介绍的哪些聚类算法只能产生凸聚类，哪些能产生非凸聚类。



#### 9.8

> 问：试设计一个聚类性能度量指标，并与9.2节中的指标比较。



#### 9.9*

> 问：试设计一个能用于混合属性的非度量距离。



#### 9.10*

> 问：试设计一个能自动确定聚类数的改进 <img src="http://latex.codecogs.com/gif.latex?k" />  均值算法，编程实现并在西瓜数据集4，0上运行。


