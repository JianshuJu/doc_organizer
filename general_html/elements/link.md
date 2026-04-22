# `<link>`

## 概述

`<link>` 元素用于指定当前文档与外部资源之间的关系。它最常用于引入样式表（CSS）、网站图标（favicon）以及预加载资源等。`<link>` 是一个空元素（void element），不包含任何子内容，也不需要闭合标签。

- **类型**: 空元素（void element）
- **分类**: 元数据（metadata）
- **规范**: [HTML Standard - The link element](https://html.spec.whatwg.org/multipage/semantics.html#the-link-element)

## 属性

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `rel` | `"favicon"` | 定义当前文档与链接资源之间的关系类型 |
| `href` | `"favicon.ico"` | 指定链接资源的 URL 地址 |
| `type` | `(common)` | 指定链接资源的 MIME 类型，如 `text/css`、`image/x-icon` |
| `media` | `(common)` | 指定链接资源适用的媒体类型，如 `screen`、`print` |
| `sizes` | `(common)` | 指定图标资源的尺寸，如 `16x16`、`32x32` |
| `crossorigin` | `(common)` | 指定 CORS 请求模式，用于跨域资源加载 |
| `integrity` | `(common)` | 提供子资源完整性校验值（SRI），确保资源未被篡改 |
| `as` | `(common)` | 指定预加载资源的类型，配合 `rel="preload"` 使用 |
| `rel` (常见值) | `(common)` | 常见值包括：`stylesheet`（样式表）、`icon`（图标）、`preload`（预加载）、`canonical`（规范链接）等 |

## 子元素

这是一个空元素（void element），不能包含任何子元素。

## 父元素

- [`<head>`](head.md)

## 源码示例

从源文件中提取的 `<link>` 元素使用示例：

```html
<!-- 来自 example/index.html -->
<link rel="favicon" href="favicon.ico">
```

## 备注

- `<link>` 元素只能出现在 `<head>` 中，用于定义文档级别的元数据链接。
- 本例中 `rel="favicon"` 是非标准写法，标准用法应为 `rel="icon"` 并配合 `type="image/x-icon"` 属性。
- `<link>` 元素最核心的属性是 `rel` 和 `href`：`rel` 描述关系类型，`href` 指定资源地址。
- 当 `rel="stylesheet"` 时，`<link>` 用于引入外部 CSS 样式表，是前端开发中使用频率最高的场景之一。
- 浏览器会根据 `rel` 属性的值决定如何处理引用的资源，例如 `preload` 表示预加载、`prefetch` 表示预获取。
