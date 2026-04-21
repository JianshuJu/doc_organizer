# <title>

## Overview

`<title>` 元素用于定义文档的标题，该标题会显示在浏览器标签页、书签和搜索引擎结果中。每个 HTML 文档中必须包含且仅包含一个 `<title>` 元素。

- **类型**：元数据元素（metadata）
- **分类**：文档元信息（document-metadata）
- **规范**：[HTML Living Standard - The title element](https://html.spec.whatwg.org/multipage/semantics.html#the-title-element)

## Attributes

该元素在源文件中未使用任何属性。`<title>` 元素仅支持全局属性（Global Attributes），没有特有的元素属性。

## Child Elements

`<title>` 是叶子元素，不能包含子元素。其内容为纯文本，用于表示文档标题。在本源文件中，文本内容为 "AGou-ops 网址发布页面"。

## Parent Elements

- [`<head>`](head.md)

## Source Example

```html
<!-- From example/index.html -->
<title>AGou-ops 网址发布页面</title>
```

## Notes

- 每个 HTML 文档有且仅有一个 `<title>` 元素，且必须位于 [`<head>`](head.md) 内部。
- `<title>` 的内容应当简洁明了，有助于 SEO 和用户识别页面。推荐长度不超过 60 个字符。
- 该元素不支持任何子元素，内容必须是纯文本，HTML 标签会被解析为文本而非元素。
