---
title: SQL-基础-DML语句
published: 2025-09-11
updated: 2025-09-11
description: DML 数据操作语句速查，包含 INSERT、UPDATE、DELETE 的常见用法与批量写法。
image: "https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/mysql/哆啦a梦-DML.png"
category: 学习
tags: [学习, mysql]
draft: false
---

## DML：添加数据（INSERT）

### 给指定字段添加数据

```sql
INSERT INTO 表名 (字段名1, 字段名2, ...) VALUES (值1, 值2, ...);
```

### 给全部字段添加数据

```sql
INSERT INTO 表名 VALUES (值1, 值2, ...);
```

### 批量添加数据

```sql
INSERT INTO 表名 (字段名1, 字段名2, ...)
VALUES
  (值1, 值2, ...),
  (值1, 值2, ...),
  (值1, 值2, ...);

-- 或者（当表的所有字段都按顺序提供）
INSERT INTO 表名
VALUES
  (值1, 值2, ...),
  (值1, 值2, ...),
  (值1, 值2, ...);
```

> 提示：若存在自增主键字段，通常无需在字段列表中显式提供该列。

### 插入示意图

> 下图来自你本地文档，请将图片文件放到 `public/images/study/mysql/` 目录，并命名为 `image-20250908103420630.png`。

![插入示意图](https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/mysql/image-20250908103420630.png)

## DML：修改数据（UPDATE）

```sql
UPDATE 表名
SET 字段名1 = 值1,
    字段名2 = 值2,
    ...
WHERE 条件;
```

> 强烈建议带上 `WHERE` 条件，避免误更新整表数据。

## DML：删除数据（DELETE）

```sql
DELETE FROM 表名
WHERE 条件;
```

> 不加 `WHERE` 会删除整张表的数据，请谨慎执行。

---

## 小结

本文整理了 MySQL 中最常用的 DML 操作：新增、更新与删除的单条与批量写法。生产环境操作前请先在测试环境验证语句，并确保关键更新/删除语句具备合适的条件与备份/回滚策略。


