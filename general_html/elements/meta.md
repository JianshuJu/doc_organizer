# `<meta>`

## 概述

`<meta>` 元素用于提供关于 HTML 文档的元数据（metadata），例如字符编码、页面描述、关键词、作者信息以及视口设置等。元数据不会在页面上直接显示，但会被浏览器、搜索引擎和其他 Web 服务解析和使用。

- **类型**: 空元素（void element），无需闭合标签
- **类别**: 元数据（metadata）
- **规范**: [HTML Standard - The meta element](https://html.spec.whatwg.org/multipage/semantics.html#the-meta-element)

## 属性

| 属性 | 源文件中的值 | 说明 |
|-----------|-----------------------------|------|
| `charset` | `"utf-8"` | 声明文档使用的字符编码，推荐使用 UTF-8 |
| `name` | `"Author"`, `"Keywords"`, `"Description"`, `"viewport"` | 定义元数据的名称标识符，用于与 `content` 属性配对使用 |
| `content` | `"Noah"`, `""`, `""`, `"width=device-width, initial-scale=1, shrink-to-fit=no"` | 提供与 `name` 或 `http-equiv` 属性关联的元数据值 |

`name` 属性在源文件中出现的值说明：
- **Author**: 标识页面作者
- **Keywords**: 为搜索引擎提供页面关键词
- **Description**: 提供页面内容的简短描述，常用于搜索引擎结果摘要
- **viewport**: 控制页面在移动设备上的视口大小和缩放行为

## 子元素

这是一个空元素（void element），不能包含任何子元素。

## 父元素

- [`<head>`](head.md)

## 源码示例

```html
<!-- 来自 example/index.html -->
<meta charset="utf-8">
<meta name="Author" content="Noah">
<meta name="Keywords" content="">
<meta name="Description" content="">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
```

## 备注

- `<meta>` 标签应始终放置在 [`<head>`](head.md) 元素内部。
- `charset` 声明应尽早出现在 `<head>` 中（最好在前 1024 字节内），以确保正确解析页面内容。
- `viewport` 元标签对响应式设计至关重要，`width=device-width` 使页面宽度匹配设备屏幕宽度，`initial-scale=1` 设置初始缩放比例为 100%。
- `shrink-to-fit=no` 是为兼容旧版 Safari 浏览器而添加的值，防止页面自动收缩以适应视口。
- `<meta>` 为空元素，不需要也不应有闭合标签（即不要写成 `</meta>`）。
