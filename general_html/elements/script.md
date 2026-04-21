# <script>

## 概述

`<script>` 元素用于在 HTML 文档中嵌入或引用可执行脚本（通常是 JavaScript）。它可以包含内联脚本代码，也可以通过 `src` 属性引用外部脚本文件。

- **类型**：元数据/脚本元素
- **分类**：嵌入式内容
- **规范**：[HTML Living Standard - The script element](https://html.spec.whatwg.org/multipage/scripting.html#the-script-element)

## 属性

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `type` | `"text/javascript"` | 指定脚本的 MIME 类型，`text/javascript` 为 JavaScript 的标准类型 |
| `src` | `"https://s4.cnzz.com/z_stat.php?id=1278893351&web_id=1278893351"` | 指定外部脚本文件的 URL |
| `async` | _(common)_ | 异步加载脚本，不阻塞页面渲染 |
| `defer` | _(common)_ | 延迟执行脚本，在文档解析完成后执行 |
| `crossorigin` | _(common)_ | 设置跨域资源共享（CORS）模式 |
| `integrity` | _(common)_ | 子资源完整性校验，确保脚本未被篡改 |
| `nomodule` | _(common)_ | 标识脚本不应在支持 ES 模块的浏览器中执行 |

## 子元素

这是空元素，当使用 `src` 属性引用外部脚本时，`<script>` 标签内不应包含任何内容。

当不使用 `src` 属性时，可以包含内联的 JavaScript 代码作为文本内容。

## 父元素

- [`<div>`](div.md)

在标准 HTML 文档中，`<script>` 元素常见于以下父元素内：

- [`<head>`](head.md)
- [`<body>`](body.md)

## 源文件示例

从源文件中提取的实际使用示例：

```html
<!-- From example/index.html -->
<script type="text/javascript" src="https://s4.cnzz.com/z_stat.php?id=1278893351&web_id=1278893351"></script>
```

该脚本嵌套在一个隐藏的 `<div>` 容器中，用于加载第三方网站统计工具（CNZZ）：

```html
<!-- From example/index.html - 完整上下文 -->
<div style='display:none'>
    <script type="text/javascript" src="https://s4.cnzz.com/z_stat.php?id=1278893351&web_id=1278893351"></script>
</div>
```

## 备注

- 当 `src` 属性存在时，浏览器会忽略 `<script>` 标签内的任何内联内容，仅加载并执行外部脚本。
- 在本源文件中，`<script>` 被放置在 `<body>` 末尾的隐藏 `<div>` 中，这是一种常见的第三方统计代码嵌入方式，将统计脚本隐藏以避免影响页面布局。
- 现代开发中推荐使用 `defer` 或 `async` 属性来优化脚本加载性能，而非手动将脚本放在页面底部。
