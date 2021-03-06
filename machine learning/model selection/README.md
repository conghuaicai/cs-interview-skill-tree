# 模型选择

## 交叉验证

假设有K折，就有K个结果，最后把这K个结果平均。

## 超参数选择

### 网格搜索

## 评价函数

### 精度

$acc(f;D)=\frac{1}{m}\sum_{i=1}^{m}I(f(x_i)=y_i)$

### 查准率

$P=\frac{TP}{TP+FP}$

### 查全率

$R=\frac{TP}{TP+FN}$

### F1-score

$F1=\frac{2*P*R}{P+R}$

### marco-P、marco-R、marco-F1

| 真实情况 |  预测结果   |  预测结果   |
| :--: | :-----: | :-----: |
|      |   正例    |   负例    |
|  正例  | TP（真正例） | FN(假反例) |
|  负例  | FP（假正例） | TN（真反例） |

很多时候我们有多个二分类混淆矩阵，我们希望在n个二分类混淆矩阵上综合考察查准率和查全率。

$macro-P=\frac{1}{n}\sum_{i=1}^{n}P_i$

$macro-R=\frac{1}{n}\sum_{i=1}^{n}R_i$

$macro-F1=\frac{2*macro-P*macro-R}{macro-P+macro-R}$

### ROC_AUC

![](data:image/jpeg;base64,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)

ROC曲线纵轴是TRP，横轴是FPR：

- $TPR=\frac{TP}{TP+FN}$
- $FPR=\frac{FP}{FN+FP}$

ROC曲线下方的面积越大，该模型越好，该面积定义为：

$AUC=\frac{1}{2}\sum_{i=1}^{m-1}(x_{i+1}-x_i)(y_i+y_{i+1})$

## 模型状态

模型状态验证工具：学习曲线；

### 过拟合

- 找更多的数据来学习；
- 增大正则化系数；
- 减少特征个数（不是太推荐）

### 欠拟合

- 找更多的特征；
- 减少正则化系数。

### 