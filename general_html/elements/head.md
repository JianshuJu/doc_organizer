# `<head>`

## 概述

`<head>` 元素是 HTML 文档的元数据容器，包含文档的标题、样式表、脚本、字符编码声明以及其他元信息。`<head>` 中的内容不会直接在页面上显示，但对浏览器解析和渲染页面至关重要。

- **类型**: 元数据容器（metadata container）
- **分类**: 文档结构（document-structure）
- **规范**: [HTML Standard - The head element](https://html.spec.whatwg.org/multipage/semantics.html#the-head-element)

## 属性

`<head>` 元素本身在源文件中没有使用特定属性。

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `profile` | `(common)` | 曾用于指定元数据配置文件的 URL，HTML5 中已废弃 |

## 子元素

`<head>` 元素在源文件中包含以下子元素类型：

| 子元素 | 在 `<head>` 下的用途 |
|---------------|------------------------|
| [`<meta>`](meta.md) | 定义文档的元数据，如字符编码、作者、关键字、描述和视口设置 |
| [`<link>`](link.md) | 引用外部资源，如网站图标（favicon） |
| [`<title>`](title.md) | 定义文档标题，显示在浏览器标签页上 |
| [`<style>`](style.md) | 包含文档的内联 CSS 样式规则 |

## 父元素

- [`<html>`](html.md)

## 源码示例

从源文件中提取的 `<head>` 元素完整使用示例：

```html
<!-- 来自 example/index.html -->
<head>
    <meta charset="utf-8">
    <meta name="Author" content="Noah">
    <meta name="Keywords" content="">
    <meta name="Description" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <link rel="favicon" href="favicon.ico">
    <title>AGou-ops 网址发布页面</title>
    <style>/* 内联 CSS 样式 */</style>
</head>
```

## 备注

- `<head>` 元素是 `<html>` 的直接子元素，通常位于 `<body>` 之前。
- 每个 HTML 文档有且仅有一个 `<head>` 元素。
- `<head>` 中至少应包含 `<title>` 元素（除非文档是 iframe 文档）。
- 常见的子元素包括 `<meta>`、`<link>`、`<title>`、`<style>`、`<script>`、`<base>` 和 `<template>` 等。
- `<meta charset="utf-8">` 应尽可能靠前放置，以确保字符编码尽早被浏览器识别。
