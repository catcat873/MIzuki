---
title: SQL-基础-DCL语句
published: 2025-09-11
updated: 2025-09-11
description: DCL 数据控制语言速查，包含用户管理与权限控制（GRANT/REVOKE）。
image: "https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/mysql/哆啦a梦-DCL.png"
category: 学习
tags: [学习, mysql]
draft: false
---

> 说明：将文中配图放在 `public/images/study/mysql/` 目录，文件名保持一致即可正常显示。

## DCL 是什么

DCL 是 Data Control Language（数据控制语言），用于管理用户与控制权限。

## 管理用户

```sql
USE mysql;

-- 查看用户表（仅示意）
SELECT * FROM user;
```

### 创建用户

```sql
CREATE USER '用户名'@'主机名' IDENTIFIED BY '密码';
```

### 修改用户密码

```sql
ALTER USER '用户名'@'主机名' IDENTIFIED WITH mysql_native_password BY '新密码';
```

### 删除用户

```sql
DROP USER '用户名'@'主机名';
```

![用户管理示意](https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/mysql/image-20250911110137218.png)

## 权限控制

![权限控制示意](https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/mysql/image-20250911110311727.png)

### 查询权限

```sql
SHOW GRANTS FOR '用户名'@'主机名';
```

### 授予权限

```sql
GRANT 权限列表 ON 数据库名.表名 TO '用户名'@'主机名';
```

### 撤销权限

```sql
REVOKE 权限列表 ON 数据库名.表名 FROM '用户名'@'主机名';
```


