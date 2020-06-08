# Tmall_Repeat_Buyers

[天猫用户复购预测大赛](https://tianchi.aliyun.com/competition/entrance/231576/introduction?lang=zh-cn "比赛地址链接")

## 背景
业务上属于潜在忠诚问题。有些用户属于羊毛党，优惠卷使用过后并不会继续购买。这些促销优惠对于转换为长期的顾客来说可能收效甚微。
为了解决这个问题，对于复购用户的预测有为重要。因为关注潜在的忠诚消费者，对于商家来说可以降低促销成本，增加投资回报率ROI。
在线推荐对于客户的定位是非常难的，尤其对于新用户。但是天猫已经积累了大量用户行为日志，可以解决这个问题。

## 小量数据跑通流程
不可以直接随机取数据。
应该选取一个主键（例如user id筛选一部分 user)

## 数据预处理
1，进行特征值转换，离散值转换数值。合并测试集合训练集一起做label encoder和one hot.(避免出现错误所以一起处理，test可能出现train里面没有的数值)
2，embedding到固定纬度作为MLP输入，纬度太大不方便做MLP全连接
3，填充缺失值，数值补全
4，人工构造特征,抽象用户画像，增加一些字段。
增加完用户的特征值，给商家也增加一些特征值。
临时保存特征文件，下次可以直接使用
模型也可以训练一半保存，checkpoint

## 使用传统机器学习模型
xgboost
lightGBM
#### 调整超参数
xgboost
lightGBM

## 预测结果
Rank: Top80
Score: 0.683473

## 使用Attention机制的DNN模型
看一下deepctr的DIN使用案例
DIN
DSIN

