# `<html>`

## 概述

`<html>` 元素是 HTML 文档的根元素，也称为顶层元素。所有其他 HTML 元素都必须嵌套在 `<html>` 元素内部。它告知浏览器该文档是一个 HTML 文档，并作为整个文档对象模型（DOM）树的起点。

- **类型**: 块级（block-level）
- **分类**: 文档结构（document-structure）
- **规范**: [HTML Living Standard - The html element](https://html.spec.whatwg.org/multipage/semantics.html#the-html-element)

## 属性

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `lang` | _(未使用)_ | 声明文档的语言，有助于搜索引擎和屏幕阅读器识别页面语言（common） |
| `dir` | _(未使用)_ | 指定文档文本的方向，如 `ltr`（从左到右）或 `rtl`（从右到左）（common） |

当前源文件中 `<html>` 元素未使用任何属性。

## 子元素

`<html>` 元素直接包含以下子元素类型：

| 子元素 | 在 `<html>` 下的用途 |
|---------------|------------------------|
| [`<head>`](head.md) | 定义文档的元数据，包括字符编码、标题、样式表等 |
| [`<body>`](body.md) | 包含页面中所有可见的内容，如文本、图片、链接等 |

## 父元素

这是根元素，没有父元素。

## 源码示例

以下是从源文件中提取的 `<html>` 元素使用示例：

```html
<!-- From example/index.html -->
<html>
<head>
    <meta charset="utf-8">
    <meta name="Author" content="Noah">
    <meta name="Keywords" content="">
    <meta name="Description" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <link rel="favicon" href="favicon.ico">
    <title>AGou-ops 网址发布页面</title>
    <style>...</style>
</head>
<body>
    ...
</body>
</html>
```

## 备注

- 每个 HTML 文档有且仅有一个 `<html>` 元素，且必须位于文档的顶层。
- `<html>` 元素应紧跟在 `<!DOCTYPE html>` 声明之后。
- 强烈建议始终在 `<html>` 元素上设置 `lang` 属性，以改善网页的可访问性和搜索引擎优化（SEO）。
- `<html>` 元素只能包含两个直接子元素：[`<head>`](head.md) 和 [`<body>`](body.md)，其中 `<head>` 必须在 `<body>` 之前。
