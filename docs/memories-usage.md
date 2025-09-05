# 岁月浅吟功能使用指南

## 功能概述

"岁月浅吟"是一个专门用于记录日常生活的内容类型，已成功集成到你的Astro主题中。

## 已实现的功能

### 1. 导航栏集成
- 在"我的"菜单中添加了"岁月浅吟"选项
- 使用书本图标 (`material-symbols:auto-stories`)
- 链接到 `/memories/` 页面

### 2. 内容管理系统
- 创建了 `memories` 内容集合
- 支持以下字段：
  - `title`: 文章标题
  - `published`: 发布日期
  - `description`: 文章描述
  - `image`: 文章图片
  - `tags`: 标签数组
  - `mood`: 心情标签
  - `weather`: 天气
  - `location`: 地点
  - `featured`: 是否精选
  - `author`: 作者（默认为"周咚咚"）

### 3. 页面结构
- **主页面**: `/memories/` - 显示所有岁月浅吟文章
- **文章页面**: `/memories/[slug]/` - 显示单篇文章

### 4. 图片存储路径
- 文章图片存储在: `public/images/memories/`
- 建议按年份和月份组织: `public/images/memories/2024/09/`

## 使用方法

### 创建新文章

1. 在 `src/content/memories/` 目录下创建新的 `.md` 文件
2. 文件命名格式: `YYYY-MM-DD-文章标题.md`
3. 在文件开头添加 front matter:

```yaml
---
title: "文章标题"
published: 2024-09-05
description: "文章描述"
image: "/images/memories/2024/09/图片名称.jpg"
tags: ["生活", "秋天", "午后"]
mood: "宁静"
weather: "晴朗"
location: "家中"
featured: true
---

# 文章内容

你的文章内容...
```

### 添加图片

1. 将图片保存到 `public/images/memories/` 目录
2. 在文章中使用相对路径引用: `/images/memories/图片名称.jpg`

## 页面特性

### 主页面特性
- 精选文章展示区域
- 按月份分组的文章列表
- 响应式网格布局
- 空状态提示

### 文章页面特性
- 文章标题和元信息
- 心情、天气、地点信息展示
- 标签显示
- 自定义样式的内容区域

## 样式定制

岁月浅吟页面使用了特殊的CSS类：
- `.memories-meta`: 元信息卡片样式
- `.memories-content`: 文章内容样式

你可以在相应的 `.astro` 文件中修改这些样式。

## 部署

构建和部署过程与普通文章相同：
```bash
npm run build
```

构建成功后，岁月浅吟功能将自动包含在静态站点中。

## 注意事项

1. 确保图片路径正确，使用 `/images/memories/` 开头的绝对路径
2. 文章文件名不要包含特殊字符
3. 日期格式必须符合 `YYYY-MM-DD` 格式
4. 标签使用数组格式，每个标签用引号包围
