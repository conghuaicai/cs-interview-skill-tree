# 马尔科夫随机场

概率图模型是由图表示的概率分布，设有联合概率分布$P(Y)$，$Y$是**一组**随机变量。由无向图$G=(V,E)$表示概率分布$P(Y)$，即在图$G$中，节点$v \in V$表示一个随机变量$Y_v$，$Y=(Y_v)_{v \in V}$；边$e \in E$表示随机变量之间的概率依赖关系。如果联合概率分布$P(Y)$满足成对、局部或全局马尔科夫性，就称此联合概率分布为概率无向图模型，或**马尔科夫随机场**。

## 三个关系

### 成对马尔科夫性

设$u$和$v$是无向图G中任意两个**没有边**连接的结点，结点$u$和$v$分别对应随机变量$Y_u$和$Y_v$，其他所有结点为$O$，对应的随机变量组是$Y_o$.成对马尔科夫性是指给定随机变量组$Y_o$的条件下随机变量$Y_u$和$Y_v$是条件独立的，即：$P(Y_u,Y_v|Y_o)=P(Y_u|Y_o)P(Y_v|Y_o)$

### 局部马尔科夫性

设$v\in V$是无向图G中任意一个结点，W是与v有边连接的所有结点，$O$是$v$，$W$以外的其他所有结点。$v$表示的随机变量是$Y_v$，W表示的随机变量组是$Y_W$，$O$表示的随机变量组是$Y_o$，局部马尔科夫性是指在给定随机变量组$Y_w$的条件下，随机变量$Y_v$与随机变量组$Y_o$是独立的，即：$P(Y_v,Y_o|Y_w)=P(Y_v|Y_w)P(P_o|Y_w)$

### 全局马尔科夫性

设结点集合$A,B$是在无向图$G$中被结点结合$C$分开的任意结点集合，结点集合$A,B$和$C$所对应的随机变量组分别是$Y_A,Y_B$和$Y_C$，全局马尔科夫性是指给定随机变量组$Y_C$条件下随机变量组$Y_A$和$Y_B$是条件独立的，即：$P(Y_A,Y_B|Y_C)=P(Y_A|Y_C)P(Y_B|Y_C)$

成对的、局部的、全局的马尔科夫性定义是等价的。

## 因式分解

无向图$G$中任何两个结点均有边连接的结点子集称为**团**。若C是无向图G的一个团，并且不能再加进任何一个G的结点使其成为一个更大的团，则称此C为**最大团**。

联合概率分布$P(Y)$可写作途中所有最大团$C$上的函数$\psi_c(Y_c)$的乘积：$P(Y)=\frac{1}{Z}\prod\psi_c(Y_c)$，其中，$Z$是规范化因子：$Z=\sum_y\prod\psi_c(Y_c)$

# 条件随机场

**条件随机场**是给定随机变量X条件下，随机变量Y的马尔科夫随机场。

设$X$与$Y$是随机变量，$P(Y|X)$是在给定$X$的条件下$Y$的条件概率分布，若随机变量$Y$构成了一个由无向图$G=(V,E)$表示的马尔科夫随机场，即：$P(Y_v|X,Y_w,w\neq v)=P(Y_v|X,Y_w,w\sim v)$

对任意结点$v$成立，则称条件概率分布$P(Y|X)$为条件随机场。式中$w \sim v$表示与结点$v$有边连接的所有节点$w$，$w\neq v$表示结点$v$以外的所有结点。