# `<i>`

## 概述

`<i>` 元素（Idiomatic Text 元素）用于表示因某种原因而与普通文本区分开的文本，例如技术术语、外文短语或 URL 地址。在本源文件中，`<i>` 元素被嵌套在 [`<a>`](a.md) 链接内部，用于以斜体样式展示 URL 地址文本。

- **类型**：行内元素（inline）
- **分类**：文本内容（text-content）
- **规范**：[HTML Living Standard - The i element](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-i-element)

## 属性

本元素在源文件中未使用任何特定属性。

## 子元素

这是叶元素，仅包含文本内容（URL 地址字符串），不包含任何子元素。

## 父元素

- [`<a>`](a.md)

## 源码示例

```html
<!-- From example/index.html -->
<a href="https://agou-ops.top" target="_blank"><i>https://agou-ops.top</i></a>
<a href="https://agou-ops.top/beforeWork" target="_blank"><i>https://agou-ops.top/beforeWork</i></a>
<a href="https://agou-ops.top/myStudyNote" target="_blank"><i>https://agou-ops.top/myStudyNote</i></a>
<a href="https://agou-ops.top/reward" target="_blank"><i>https://agou-ops.top/reward</i></a>
```

## 备注

- 源文件中所有 `<i>` 元素均位于 [`<a>`](a.md) 元素内部，作为链接的可点击文本，以斜体样式展示 URL 地址。
- 部分源文件中的 `<i>` 标签缺少闭合标签（如第三、四个链接中 `</i>` 被省略），但浏览器会自动补全并正确渲染。
- 语义上，HTML5 建议使用 `<i>` 表示"不同语气或情绪"的文本，此处用于标记 URL 地址属于合理用法。
