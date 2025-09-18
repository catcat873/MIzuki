---
title: HTML-CSS 基础学习
published: 2025-01-20
updated: 2025-01-20
description: HTML和CSS基础知识学习，包括标签使用、样式设置、布局技巧等前端开发必备技能。
image: "https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/frontend/html-css-img/html-css-basics.png"
category: 学习
tags: [学习, 前端, frontend, html, css]
draft: false
---

> 说明：文中的示意图请放在 `public/images/study/frontend/html-css-img/` 目录下，并保持下列文件名一致即可正常显示。

# HTML-CSS 基础学习

## HTML 基础标签

### 标题标签
```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
```

### 超链接标签
```html
<a href="" target="">链接文本</a>
```

**属性说明：**
- `href`: 指定资源访问的URL
- `target`: 指定何处打开资源链接
  - `_self`: 默认值，在当前页面打开
  - `_blank`: 在空白页面打开

## CSS 样式基础

### 选择器类型

最常见的三类选择器的写法：

1. **元素选择器**: `标签名{...}`
2. **类选择器**: `.class属性值{...}`
3. **ID选择器**: `#id属性值{...}`

> 优先级最高的是ID选择器

![CSS选择器示意图](https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/frontend/html-css-img/css-selectors.png)

### 媒体元素

#### 引入视频
```html
<video controls>
  <source src="视频文件路径" type="video/mp4">
  您的浏览器不支持视频标签。
</video>
```

#### 引入图片
```html
<img src="图片路径" alt="图片描述" width="宽度" height="高度">
```

### 字符实体

常用的HTML字符实体：

| 字符 | 实体名称 | 实体编号 | 描述 |
|------|----------|----------|------|
| < | `&lt;` | `&#60;` | 小于号 |
| > | `&gt;` | `&#62;` | 大于号 |
| & | `&amp;` | `&#38;` | 和号 |
| " | `&quot;` | `&#34;` | 引号 |
| ' | `&apos;` | `&#39;` | 撇号 |
| 空格 | `&nbsp;` | `&#160;` | 不间断空格 |

## CSS 布局技术

### 整体居中显示

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
```

### CSS 盒子模型

盒子模型由四个部分组成：
1. **内容（content）**: 元素的实际内容
2. **内边距（padding）**: 内容与边框之间的空间
3. **边框（border）**: 围绕内边距的边框
4. **外边距（margin）**: 边框外的空间

![CSS盒子模型示意图](https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/frontend/html-css-img/css-box-model.png)

```css
.box {
    width: 200px;
    height: 100px;
    padding: 20px;
    border: 2px solid #000;
    margin: 10px;
}
```

### Flex 布局

Flex布局是Flexible Box的缩写，意为"弹性布局"，是一种一维的布局模型。Flex布局可以为元素之间提供强大的布局和对齐能力。

![Flex布局示意图](https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/frontend/html-css-img/flex-layout.png)

```css
.flex-container {
    display: flex;
    flex-direction: row; /* 主轴方向 */
    justify-content: center; /* 主轴对齐方式 */
    align-items: center; /* 交叉轴对齐方式 */
    flex-wrap: wrap; /* 是否换行 */
}

.flex-item {
    flex: 1; /* 弹性增长 */
    margin: 10px;
}
```

## 表单标签

### 表单基础
```html
<form action="提交地址" method="提交方式">
    <!-- 表单项 -->
</form>
```

**表单属性：**
- `action`: 表单数据提交的URL地址
- `method`: 表单提交方式
  - `get`: 表单数据拼接在URL后面，大小有限制
  - `post`: 表单数据在请求中携带，大小没有限制

> 注意：表单项必须有name属性才可以提交。

### 表单项类型

#### input 标签的 type 属性
```html
<input type="text" name="username" placeholder="请输入用户名">
<input type="password" name="password" placeholder="请输入密码">
<input type="radio" name="gender" value="male"> 男
<input type="checkbox" name="hobby" value="reading"> 阅读
<input type="file" name="avatar">
<input type="date" name="birthday">
<input type="email" name="email">
<input type="submit" value="提交">
<input type="reset" value="重置">
```

#### 其他表单元素
```html
<!-- 下拉列表 -->
<select name="city">
    <option value="beijing">北京</option>
    <option value="shanghai">上海</option>
</select>

<!-- 文本域 -->
<textarea name="message" rows="4" cols="50" placeholder="请输入留言"></textarea>
```

## 表格标签

![HTML表格结构示意图](https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/frontend/html-css-img/html-table-structure.png)

```html
<table>
    <thead>
        <tr>
            <th>姓名</th>
            <th>年龄</th>
            <th>职业</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>张三</td>
            <td>25</td>
            <td>程序员</td>
        </tr>
    </tbody>
</table>
```

## 实战案例：员工管理系统

以下是一个完整的员工管理页面示例，展示了HTML和CSS的综合应用：

![员工管理系统效果图](https://cdn.jsdelivr.net/gh/catcat873/mizuki-assets@main/public/images/study/frontend/html-css-img/employee-management-demo.png)

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tlias智能学习辅助系统</title>
    <style>
        /* 顶部导航栏样式 */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 30px;
            background-color: #6c757d;
            border-bottom: 1px solid #eaeaea;
        }
        
        .navbar h1 {
            font-size: 24px;
            font-weight: bold;
            margin: 0;
            color: white;
            font-family: "KaiTi", "楷体", serif;
        }
        
        .logout-link {
            text-decoration: none;
            color: white;
            font-size: 16px;
        }
        
        .logout-link:hover {
            text-decoration: underline;
        }

        /* 搜索表单区域样式 */
        .search-container {
            padding: 20px 30px;
            background-color: #f8f9fa;
            border-bottom: 1px solid #eaeaea;
        }

        .search-form .form-row {
            display: flex;
            align-items: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .search-form .form-group {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .search-form .form-group label {
            white-space: nowrap;
        }

        .search-form .form-control {
            padding: 8px;
            border: 1px solid #ced4da;
            border-radius: 4px;
        }

        .search-form .form-control#employeeName {
            width: 200px;
        }

        .search-form .form-control#employeeGender {
            width: 150px;
        }

        .search-form .form-control#employeePosition {
            width: 200px;
        }

        .button-group {
            display: flex;
            gap: 25px;
            margin-left: 100px;
        }

        .btn {
            padding: 8px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            color: white;
        }

        .btn-primary {
            background-color: #007bff;
        }

        .btn-secondary {
            background-color: #6c757d;
        }

        .btn:hover {
            opacity: 0.9;
        }

        /* 表格展示区域样式 */
        .table-container {
            padding: 20px 30px;
            background-color: #ffffff;
        }

        .table-title {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 15px;
            color: #333;
        }

        .data-table {
            width: 100%;
            border-collapse: collapse;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
            overflow: hidden;
        }

        .data-table thead {
            background-color: #6c757d;
            color: white;
        }

        .data-table th,
        .data-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #eaeaea;
        }

        .data-table th {
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            font-size: 14px;
        }

        .data-table tbody tr:hover {
            background-color: #f8f9fa;
        }

        .data-table tbody tr:last-child td {
            border-bottom: none;
        }

        .avatar-img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            object-fit: cover;
        }

        .operation-btn {
            padding: 5px 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 13px;
            margin-right: 5px;
        }

        .edit-btn {
            background-color: #ffc107;
            color: #212529;
        }

        .delete-btn {
            background-color: #dc3545;
            color: white;
        }

        .edit-btn:hover,
        .delete-btn:hover {
            opacity: 0.8;
        }

        /* 页脚版权展示区样式 */
        .footer {
            background-color: #6c757d;
            color: white;
            text-align: center;
            padding: 20px 30px;
            flex-shrink: 0;
            margin-bottom: 10px;
        }

        .footer .company-name {
            font-size: 16px;
            margin-bottom: 5px;
        }

        .footer .copyright {
            font-size: 14px;
            opacity: 0.8;
        }
    </style>
</head>
<body>
    <!-- 第一部分：顶部导航栏 -->
    <nav class="navbar">
        <h1>Tlias智能学习辅助系统</h1>
        <a href="#" class="logout-link">退出登录</a>
    </nav>

    <!-- 第二部分：搜索表单区域 -->
    <div class="search-container">
        <form id="searchForm" class="search-form" action="/search" method="GET">
            <div class="form-row">
                <!-- 员工姓名输入框 -->
                <div class="form-group">
                    <label for="employeeName">姓名:</label>
                    <input type="text" id="employeeName" name="employeeName" placeholder="请输入员工姓名" class="form-control">
                </div>
                
                <!-- 性别下拉选择 -->
                <div class="form-group">
                    <label for="employeeGender">性别:</label>
                    <select id="employeeGender" name="employeeGender" class="form-control">
                        <option value="">全部</option>
                        <option value="男">男</option>
                        <option value="女">女</option>
                    </select>
                </div>
                
                <!-- 职位下拉选择 -->
                <div class="form-group">
                    <label for="employeePosition">职位:</label>
                    <select id="employeePosition" name="employeePosition" class="form-control">
                        <option value="">全部</option>
                        <option value="班主任">班主任</option>
                        <option value="讲师">讲师</option>
                        <option value="学工主管">学工主管</option>
                        <option value="教研主管">教研主管</option>
                        <option value="咨询师">咨询师</option>
                    </select>
                </div>
                
                <!-- 操作按钮 -->
                <div class="button-group">
                    <button type="submit" class="btn btn-primary">查询</button>
                    <button type="reset" class="btn btn-secondary">清空</button>
                </div>
            </div>
        </form>
    </div>

    <!-- 第三部分：表格展示区域 -->
    <div class="table-container">
        <div class="table-title">员工列表</div>
        <table class="data-table">
            <thead>
                <tr>
                    <th>姓名</th>
                    <th>性别</th>
                    <th>头像</th>
                    <th>职位</th>
                    <th>入职日期</th>
                    <th>最后操作时间</th>
                    <th>操作</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>令狐冲</td>
                    <td>男</td>
                    <td><img src="https://via.placeholder.com/40x40/cccccc/ffffff?text=L" alt="令狐冲头像" class="avatar-img"></td>
                    <td>讲师</td>
                    <td>2020-03-15</td>
                    <td>2023-10-20 14:30</td>
                    <td>
                        <button class="operation-btn edit-btn">编辑</button>
                        <button class="operation-btn delete-btn">删除</button>
                    </td>
                </tr>
                <tr>
                    <td>任盈盈</td>
                    <td>女</td>
                    <td><img src="https://via.placeholder.com/40x40/ffcccc/ffffff?text=R" alt="任盈盈头像" class="avatar-img"></td>
                    <td>教研主管</td>
                    <td>2019-07-01</td>
                    <td>2023-10-21 09:15</td>
                    <td>
                        <button class="operation-btn edit-btn">编辑</button>
                        <button class="operation-btn delete-btn">删除</button>
                    </td>
                </tr>
                <tr>
                    <td>岳不群</td>
                    <td>男</td>
                    <td><img src="https://via.placeholder.com/40x40/ccffcc/ffffff?text=Y" alt="岳不群头像" class="avatar-img"></td>
                    <td>班主任</td>
                    <td>2018-05-10</td>
                    <td>2023-10-19 16:45</td>
                    <td>
                        <button class="operation-btn edit-btn">编辑</button>
                        <button class="operation-btn delete-btn">删除</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>

    <!-- 第四部分：页脚版权展示区 -->
    <footer class="footer">
        <div class="company-name">黑马程序员有限公司</div>
        <div class="copyright">© 2023 Tlias智能学习辅助系统. 保留所有权利.</div>
    </footer>
</body>
</html>
```

## CSS 样式调整技巧

### 外边距和内边距的区别

- **margin**: 外边距，控制元素与其他元素之间的距离
- **padding**: 内边距，控制元素内容与边框之间的距离

### 表单控件宽度调整

```css
.search-form .form-control#employeeName {
    width: 150px; /* 姓名输入框宽度 */
}

.search-form .form-control#employeeGender {
    width: 100px; /* 性别选择框宽度 */
}

.search-form .form-control#employeePosition {
    width: 150px; /* 职位选择框宽度 */
}
```

### 按钮间距控制

```css
.button-group {
  display: flex;
  gap: 10px; /* 控制两个按钮之间的距离 */
}
```

## 总结

HTML和CSS是前端开发的基础，掌握这些基础知识对于构建现代化的网页应用至关重要。通过本文的学习，你应该能够：

1. 熟练使用HTML基础标签
2. 理解CSS选择器和样式规则
3. 掌握盒子模型和布局技术
4. 能够创建完整的表单和表格
5. 运用Flex布局进行页面排版
6. 通过实战案例巩固所学知识

继续深入学习JavaScript，你将能够创建更加动态和交互性强的网页应用。
