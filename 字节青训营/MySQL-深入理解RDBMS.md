# 经典案例

![image-20230211144532780](笔记图片/image-20230211144532780.png)

# 发展历史

## DBMS时代

### 网状模型

![image-20230211145735285](笔记图片/image-20230211145735285.png)

### 层次模型

![image-20230211145804027](笔记图片/image-20230211145804027.png)

### 关系模型

![image-20230211150014050](笔记图片/image-20230211150014050.png)

![image-20230211150036704](笔记图片/image-20230211150036704.png)

# 关键技术

## 一条SQL的一生

![image-20230211151711661](笔记图片/image-20230211151711661.png)

## SQL引擎

### Parser

![image-20230211151903612](笔记图片/image-20230211151903612.png)

### Optimizer

![image-20230211152316483](笔记图片/image-20230211152316483.png)

![image-20230211152513895](笔记图片/image-20230211152513895.png)

### Executor

![image-20230211152822046](笔记图片/image-20230211152822046.png)

![image-20230211152949695](笔记图片/image-20230211152949695.png)

![image-20230211153144086](笔记图片/image-20230211153144086.png)

## 存储引擎

### InnoDB(eg)

![image-20230211153726982](笔记图片/image-20230211153726982.png)

### Buffer Pool

![image-20230211153828486](笔记图片/image-20230211153828486.png)

### Page

* 一条数据在磁盘上的存储形式

![image-20230211154107122](笔记图片/image-20230211154107122.png)

### B+ Tree

![image-20230211154232961](笔记图片/image-20230211154232961.png)

* 范围查询比较好使

## 事务引擎

### Atomicity 与 Undo Log

![image-20230211154444941](笔记图片/image-20230211154444941.png)

### Isolation 与 MVCC

![image-20230211154700317](笔记图片/image-20230211154700317.png)

### Durability 与 Redo Log

![image-20230211154844672](笔记图片/image-20230211154844672.png)

# 企业实践

## 大流量-Sharding

![image-20230211155342858](笔记图片/image-20230211155342858.png)

## 流量突增-扩容

![image-20230211155723546](笔记图片/image-20230211155723546.png)

## 流量突增-代理连接池

![image-20230211155831252](笔记图片/image-20230211155831252.png)

## 稳定性&可靠性

![image-20230211160143064](笔记图片/image-20230211160143064.png)

![image-20230211160324726](笔记图片/image-20230211160324726.png) 

# 总结

![image-20230211160336248](笔记图片/image-20230211160336248.png)