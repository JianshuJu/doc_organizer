# <div>

## 概述

`<div>` 是 HTML 中最常用的通用容器元素，用于将内容进行分组以便应用样式（通过 `class` 或 `id` 属性）或进行脚本操作。它本身不具有语义含义，是一个纯粹的块级包装元素。

- **类型**：块级元素（block-level）
- **分类**：文档结构 / 通用容器
- **规范**：[HTML Living Standard - The div element](https://html.spec.whatwg.org/multipage/grouping-content.html#the-div-element)

## 属性

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `id` | `"all"` | 为元素指定唯一标识符，用于 CSS 选择器或 JavaScript 操作 |
| `class` | `"wrapper"`, `"main"`, `"content"`, `"content-top"` | 为元素指定一个或多个类名，用于 CSS 样式和选择器匹配 |
| `style` | `"display:none"` | 行内样式，直接在元素上应用 CSS 样式规则 |

## 子元素

| 子元素 | 在 `<div>` 下的用途 |
|---------------|------------------------|
| [`<div>`](div.md) | 嵌套的分区容器，用于构建多层级的页面布局结构 |
| [`<h1>`](h1.md) | 一级标题，作为页面主标题展示 |
| [`<h2>`](h2.md) | 二级标题，作为分区子标题展示 |
| [`<ul>`](ul.md) | 无序列表，用于展示链接列表内容 |
| [`<p>`](p.md) | 段落文本，用于展示页脚版权信息 |
| [`<script>`](script.md) | 脚本元素，用于加载统计代码等外部脚本 |

## 父元素

- [`<body>`](body.md)
- [`<div>`](div.md)（自身可以嵌套）

## 源码示例

```html
<!-- 来自 example/index.html -->
<!-- 最外层容器 -->
<div id="all">
    <div class="wrapper">
        <div class="main">
            <h1>网址发布页</h1>
            <div class="content">
                <div class="content-top">
                    <h2>请 Ctrl+D 收藏本页到浏览器收藏夹</h2>
                    <ul>
                        <li>...</li>
                    </ul>
                </div>
            </div>
            <p class="footer">© 2020 AGou . All Rights Reserved</p>
        </div>
        <ul class="bg-bubbles">
            <li></li>
        </ul>
    </div>
</div>

<!-- 隐藏的统计脚本容器 -->
<div style='display:none'>
    <script type="text/javascript" src="https://s4.cnzz.com/z_stat.php?id=1278893351&web_id=1278893351"></script>
</div>
```

## 备注

- `<div>` 是没有语义的通用容器，应优先考虑使用具有语义的 HTML5 元素（如 `<section>`、`<article>`、`<nav>`、`<aside>` 等），仅在找不到合适的语义元素时才使用 `<div>`。
- 在本源文件中，`<div>` 被大量用于构建多层嵌套的页面布局结构，形成了 `#all > .wrapper > .main > .content > .content-top` 的层级关系。
- `style="display:none"` 用于隐藏包含统计脚本的 `<div>`，这是一种常见的页面统计代码隐藏方式。
- `<div>` 元素支持所有全局属性（如 `id`、`class`、`style`、`title`、`lang` 等）。
