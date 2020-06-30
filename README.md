# Tmall_Repeat_Buyers

[天猫用户复购预测大赛](https://tianchi.aliyun.com/competition/entrance/231576/introduction?lang=zh-cn "比赛地址链接")

## 背景
业务上属于潜在忠诚问题。有些用户属于羊毛党，优惠卷使用过后并不会继续购买。这些促销优惠对于转换为长期的顾客来说可能收效甚微。
为了解决这个问题，对于复购用户的预测有为重要。因为关注潜在的忠诚消费者，对于商家来说可以降低促销成本，增加投资回报率ROI。
在线推荐对于客户的定位是非常难的，尤其对于新用户。但是天猫已经积累了大量用户行为日志，可以解决这个问题。

## 小量数据跑通流程
采样不可以直接随机取数据。

应该选取一个主键（例如user id筛选一部分 user id作为数据集)

## 数据预处理

1，导入训练集和测试集将两个数据合并到同一个DF中进行接下来的处理。

2，通过user id将用户profile表的信息添加到DF中。

3，对每列类型进行定义（根据内容定义数据类型可以降低内存使用），处理异常值。

4，日志数据按照user id分组，做不同类型统计构造关于user id的特征。

5，日志数据按照merchant_id分组，做不同类型统计构造关于merchant_id的特征。

6，日志数据按照（user id， merchant_id）分组，做不同类型统计构造关于（user id， merchant_id）的特征。

7，使用one hot的方法处理年龄字段。

#### 为DIN和DSIN模型构造sequence

8，把日志数据中同一个user的数据合并到list中，增加两列一个是mechant_id的序列，一个是action type序列

## 使用传统机器学习模型
xgboost
lightGBM
#### 调整超参数
使用GridSearchCV调整参数

## 预测结果
Rank: Top80
Score: 0.683473

## 使用Attention机制的DNN模型
DIN
DSIN

