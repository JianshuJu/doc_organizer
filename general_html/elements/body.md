# `<body>`

## 概述

`<body>` 元素表示 HTML 文档的主体内容区域，包含文档中所有可见的页面内容，如文本、图像、链接、表格、列表等。每个 HTML 文档只能有一个 `<body>` 元素。

- **类型**：块级元素（block-level）
- **分类**：文档结构（document-structure）
- **规范**：[HTML Living Standard - The body element](https://html.spec.whatwg.org/multipage/sections.html#the-body-element)

## 属性

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `class` | *(common)* | 为 `<body>` 元素指定一个或多个类名，用于 CSS 样式控制 |
| `id` | *(common)* | 为 `<body>` 元素指定唯一的标识符 |
| `onload` | *(common)* | 页面加载完成时触发的脚本事件 |
| `onunload` | *(common)* | 页面卸载时触发的脚本事件 |

在源文件中，`<body>` 元素未使用任何特定属性。

## 子元素

| 子元素 | 在 `<body>` 下的用途 |
|---------------|------------------------|
| [`<div>`](div.md) | 作为页面主要内容的容器，用于布局和结构化页面元素 |
| [`<script>`](script.md) | 包含或引用 JavaScript 脚本，用于页面统计和分析功能 |

## 父元素

- [`<html>`](html.md)

## 源码示例

从源文件中提取 `<body>` 元素的实际使用代码：

```html
<!-- 来自 example/index.html -->
<body >
    <div id="all">
        <div class="wrapper">
            <div class="main">
                <h1>网址发布页</h1>
                <div class="content">
                    <div class="content-top">
                        <h2>请 Ctrl+D 收藏本页到浏览器收藏夹</h2>
                        <ul>
                            <li>
                                AGou's Blog
                                <a href="https://agou-ops.top" target="_blank"><i>https://agou-ops.top</i></a>
                            </li>
                            ...
                        </ul>
                    </div>
                </div>
                <p class="footer">© 2020 AGou . All Rights Reserved</p>
            </div>
            <ul class="bg-bubbles">
                <li></li>
                ...
            </ul>
        </div>
    </div>
    <div style='display:none'>
        <script type="text/javascript" src="https://s4.cnzz.com/z_stat.php?id=1278893351&web_id=1278893351"></script>
    </div>
</body>
```

## 备注

- `<body>` 元素是 HTML 文档中所有可见内容的容器，与 [`<head>`](head.md) 互补，后者包含文档的元数据信息。
- 每个 HTML 文档中 `<body>` 元素是可选的，但如果存在则只能有一个。
- 在本源文件中，`<body>` 包含两个主要 `<div>` 区块：一个用于页面可见内容（导航链接发布页），另一个为隐藏的统计分析脚本容器。
- 建议将 `<script>` 元素放置在 `<body>` 的末尾（如本例所示），以避免阻塞页面渲染。
