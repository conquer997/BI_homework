# 第二十周

### Thinking1  如果你是某P2P租车的技术负责人，你会如何设计个性化推荐和搜索排序

**一、阐述相似车型，搜索排序的设计方法**

通过在list embedding空间中找到 k个最近邻居，对于学习好的list embedding，通过计算与来自相同目的地的所有车型的向量之间的余弦相似性，找到指定车型的所有可预订的相似车型大于等于最终得到的k个最高相似性的车型组成相似车型列表。

**二、可能的embedding策略**

1. 将每个车型大于等于embedding
2. 数据集由 N 个用户的点击会话组成，其中每个会话定义为一个由用户点击的 M个车型 id 组成的的不间断序列，只要用户连续两次点击时间间隔超过30分钟，就认为是一个新的Session
3. 目标是通过集合S，学习出每个车型listing的32维embedding表示，让相似listing在embedding空间中距离更近

