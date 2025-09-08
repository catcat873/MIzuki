---
title: SQL-基础-DDL语句
published: 2025-09-06
updated: 2025-09-06
description: 常用SQL通用语法梳理，含注释、DDL 数据库与表操作、常见数据类型与字段变更。
image: "/images/study/mysql/image-20250904101550544.png"
category: 学习
tags: [学习, mysql]
draft: false
---

## 注释语法

- 单行注释：

```sql
-- 这是单行注释（标准 SQL）
# 这是单行注释（MySQL 特有）
```

- 多行注释：

```sql
/*
  多行注释示例
  可用于屏蔽一段 SQL
*/
```

## DDL：数据库操作

### 查询数据库

```sql
-- 查询所有数据库
SHOW DATABASES;

-- 查询当前数据库
SELECT DATABASE();
```

### 创建数据库

```sql
-- 若不存在则创建
CREATE DATABASE IF NOT EXISTS demo_db;

-- 指定字符集与排序规则（示例：utf8mb4 + utf8mb4_general_ci）
CREATE DATABASE IF NOT EXISTS demo_db
  DEFAULT CHARACTER SET utf8mb4
  COLLATE utf8mb4_general_ci;
```

注意：`CREATE` 关键字，不是 `CRETE`；`DATABASE` 单数，不加 `S`。

### 删除数据库

```sql
DROP DATABASE IF EXISTS demo_db;
```

### 使用数据库

```sql
USE demo_db;
```

## DDL：表操作

### 查询表

```sql
-- 查询当前数据库所有表
SHOW TABLES;

-- 查询表结构（字段、类型、是否可空等）
DESC users;

-- 查询指定表的建表语句
SHOW CREATE TABLE users;
```

### 创建表

```sql
CREATE TABLE users (
  id INT PRIMARY KEY COMMENT '编号',
  username VARCHAR(50) NOT NULL COMMENT '用户名',
  age INT NULL COMMENT '年龄',
  created_at DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间'
) COMMENT = '用户表';
```

字段格式参考：`字段名 字段类型 [COMMENT 注释] [约束]`。

## 常见数据类型（示意）

下图示意了常见整数/浮点/日期/字符串等类型的用途与范围（请以实际数据库版本文档为准）。

![数据类型示意一](/images/study/mysql/image-20250904101550544.png)

![数据类型示意二](/images/study/mysql/image-20250904101732706.png)

![数据类型示意三](/images/study/mysql/image-20250904102653638.png)

> 提示：请将图片放在 `public/images/study/mysql/` 目录下，文件名与上方引用一致，即可正常显示。

## DDL：表结构修改

### 添加字段

```sql
ALTER TABLE users
  ADD email VARCHAR(100) COMMENT '邮箱';
```

### 修改字段类型

```sql
ALTER TABLE users
  MODIFY age INT; -- 修改类型/长度/是否可空
```

### 重命名字段并修改定义

```sql
ALTER TABLE users
  CHANGE old_name username VARCHAR(50) COMMENT '用户名';
```
### 删除字段
```sql
alter table 表名 drop 字段名；
```

### 修改表名
```sql
alter table 表名 rename to 表名
```

### 删除表 
```sql
drop table[if exsts] 表名；
```

### 删除指定表，并重新创建该表
```sql
truncate table 表名;
---

## 小结

本文整理了 SQL 通用注释、数据库与数据表的 DDL 常用操作、以及字段与数据类型的示意。建议在实际项目中结合具体数据库版本文档（如 MySQL 8.0 官方手册）核对细节与最佳实践，例如字符集、排序规则、主从键、索引、分区、以及约束的一致性策略等。


