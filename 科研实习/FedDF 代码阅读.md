# Master

## init

* 创建模型和对应的state_dict以及三种hashmap

* 创建dataset和potential data_partitioner

* 创建validation loader和test loader

* 定义criterion和metrics

  > 什么是metrics？
  >
  > 性能指标，通过衡量模型输出y_predict和y_true之间的某种距离得出。如准确率，召回率等。

* 定义master的aggregator和coordinator（）

  > 什么是coordinator？

* 定义early_stopping_tracker
* 将所有参数保存到磁盘

## run

* 获取随机的n_local_epochs
* 随机从clients中选取子集
* 检测early stopping
* ***init the activation tensor and broadcast to all clients (either start or stop).***
* 将model发送给activated clients
* 等待local models
* **aggregate the local models and evaluate on the validatin dataset**
* evaluate the aggregated model
* 上述步骤完成为一次communication round