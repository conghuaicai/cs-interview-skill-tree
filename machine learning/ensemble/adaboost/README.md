# AdaBoost

对于分类问题而言，给定一个训练样本集，求比较粗糙的分类规则（弱分类器）要比求精确的分类规则（强分类器）容易得多。提升方式就是从弱学习算法出发，反复学习，得到一系列弱分类器，然后组合这些弱分类器，构成一个强分类器。

两个基本问题：

1. 每一轮如何改变训练数据的权值或概率分布；
2. 如何将弱分类器组合成一个强分类器；

## 三个基本步骤

### 1. 初始化训练数据集

![](./images/1.png)

### 2. 学习、获得系数、更新权值

![](./images/2.png)

![](./images/3.png)

![](./images/4.png)

### 3. 组合成强分类器

![](./images/5.png)

- 需要注意的的是，每个弱分类器都是该轮样本中最优的分类器。

- 可以认为AdaBoost算法是模型为加法模型、损失函数为指数函数、学习算法为前向分步算法

  ​