* 声明性语言

  ![image-20220817161237997](笔记图片/image-20220817161237997.png)

* 基础语法

  ![image-20220817161923127](笔记图片/image-20220817161923127.png)

# 语法讲解

## select

![image-20220817162340494](笔记图片/image-20220817162340494.png)

## Naming Tables

![image-20220817162451152](笔记图片/image-20220817162451152.png)

## Project Tables 从现有列表创建新的列表

![image-20220817162929917](笔记图片/image-20220817162929917.png)

## Arithmetic in Select Expressions

![image-20220817171216671](笔记图片/image-20220817171216671.png)

## Joining Two Tables

![image-20220817172043253](笔记图片/image-20220817172043253.png)

## Aliases and Dot Expressions

* 处理不同table中有相同名字的column

![image-20220817172857657](笔记图片/image-20220817172857657.png)

## Joining Multiple Tables

![image-20220817173356841](笔记图片/image-20220817173356841.png)

## Numerical Expressions

![image-20220817174137498](笔记图片/image-20220817174137498.png)

## String Expressions

![image-20220817174506145](笔记图片/image-20220817174506145.png)

## Aggregate Functions 聚合函数

* min， max， count， avg等函数作用于某一列的所有行或者用where指定行
* distinct 表示不同种类， 可以用count计算种类，也可以用sum计算所有种类之和，去除重复种类的row

![image-20220817175809669](笔记图片/image-20220817175809669.png)

## Grouping Rows

![image-20220818102421327](笔记图片/image-20220818102421327.png)

* having 作用于group，where作用于每一个单行

![image-20220818102843207](笔记图片/image-20220818102843207.png)

## Create Table

![image-20220818103212089](笔记图片/image-20220818103212089.png)

## Drop Table

![image-20220818103249299](笔记图片/image-20220818103249299.png)

## Modifying Tables

### Insert

![image-20220818103454685](笔记图片/image-20220818103454685.png)

* 当向表格中只添加部分column的时候其他的column如果有default会默认为default

![image-20220818103734933](笔记图片/image-20220818103734933.png)

### Update

![image-20220818103913166](笔记图片/image-20220818103913166.png)

![image-20220818104103931](笔记图片/image-20220818104103931.png)

![image-20220818104123021](笔记图片/image-20220818104123021.png)

### Delete

![image-20220818104136704](笔记图片/image-20220818104136704.png)

eg：delete from primes where prime = 0; 会删除primes中所有素数column为0的row

## Python and SQL

![image-20220818104751139](笔记图片/image-20220818104751139.png)

commit负责将修改提交到文件中

## SQL Injection Attack

* 尽量用excute来对database进行操作

![image-20220818105434960](笔记图片/image-20220818105434960.png)

## Database Connections

* 21点

![](笔记图片/image-20220818110311959.png)![image-20220818110404394](笔记图片/image-20220818110404394.png)

![image-20220818110255930](笔记图片/image-20220818110255930.png)