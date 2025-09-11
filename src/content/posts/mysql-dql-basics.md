---
title: SQL-基础-DQL语句
published: 2025-09-11
updated: 2025-09-11
description: DQL 数据查询语言速查，涵盖 SELECT 基本/条件/分组/排序/分页语法与执行顺序。
image: "/images/study/mysql/image-20250908150312124.png"
category: 学习
tags: [学习, mysql]
draft: false
---

> 说明：文中的示意图请放在 `public/images/study/mysql/` 目录下，并保持下列文件名一致即可正常显示。

## DQL 是什么

DQL 全称 Data Query Language（数据查询语言），用于查询数据库中表的记录。

## DQL 基本语法

```
SELECT 字段列表
FROM 表名列表
WHERE 条件列表
GROUP BY 分组字段列表
HAVING 分组后条件列表
ORDER BY 排序字段列表
LIMIT 分页参数
```

## 基本查询

### 查询多个字段

```sql
SELECT 字段1, 字段2, 字段3 ... FROM 表名;
SELECT * FROM 表名;
```

### 设置别名

```sql
SELECT 字段1 AS 别名1, 字段2 AS 别名2 FROM 表名;
```

### 去除重复记录

```sql
SELECT DISTINCT 字段列表 FROM 表名;
```

## 条件查询（WHERE）

```sql
SELECT 字段列表 FROM 表名 WHERE 条件列表;
```

![条件示意一](/images/study/mysql/image-20250908150312124.png)
![条件示意二](/images/study/mysql/image-20250909105245721.png)
![条件示意三](/images/study/mysql/image-20250909105447322.png)
![条件示意四](/images/study/mysql/image-20250909105415884.png)
![条件示意五](/images/study/mysql/image-20250909105738336.png)
![条件示意六](/images/study/mysql/image-20250909105809469.png)

## 排序（ORDER BY）

```sql
SELECT 字段列表 FROM 表名
ORDER BY 字段1 [ASC|DESC], 字段2 [ASC|DESC];
```

## 分页（LIMIT）

```sql
-- 语法：LIMIT 偏移量, 行数
SELECT 字段 FROM 表名 LIMIT 起始索引, 查询行数;
```

![分页示意](/images/study/mysql/image-20250910112628488.png)

## 案例练习

![案例练习](/images/study/mysql/image-20250911102611899.png)

## DQL 执行顺序（理解）

![执行顺序示意](/images/study/mysql/image-20250911102806779.png)


