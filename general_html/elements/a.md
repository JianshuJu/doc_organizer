# <a>

## 概述

`<a>` 元素（锚点元素）用于创建超链接，指向其他网页、文件或其他内部资源。点击后可导航至 `href` 属性所指定的目标地址。

- **类型**：行内元素（inline）
- **分类**：文本内容（text-content）
- **规范**：[HTML Living Standard - The a element](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-a-element)

## 属性

| 属性 | 源文件中的值 | 说明 |
|-----------|----------------|-------------|
| `href` | `"https://agou-ops.top"`, `"https://agou-ops.top/beforeWork"`, `"https://agou-ops.top/myStudyNote"`, `"https://agou-ops.top/reward"` | 指定链接的目标 URL |
| `target` | `"_blank"` | 指定在何处打开链接文档，`_blank` 表示在新窗口/标签页中打开 |

## 子元素

| 子元素 | 在 `<a>` 下的用途 |
|---------------|------------------------|
| [`<i>`](i.md) | 以斜体样式展示链接文本（URL 地址） |

## 父元素

- [`<li>`](li.md)

## 源文件示例

```html
<!-- From example/index.html -->
<a href="https://agou-ops.top" target="_blank"><i>https://agou-ops.top</i></a>
<a href="https://agou-ops.top/beforeWork" target="_blank"><i>https://agou-ops.top/beforeWork</i></a>
<a href="https://agou-ops.top/myStudyNote" target="_blank"><i>https://agou-ops.top/myStudyNote</i></a>
<a href="https://agou-ops.top/reward" target="_blank"><i>https://agou-ops.top/reward</i></a>
```

## 备注

- 所有源文件中的 `<a>` 元素均设置了 `target="_blank"`，表示链接将在新标签页中打开。
- 每个链接内部都包含一个 `<i>` 子元素，用于以斜体样式显示 URL 地址文本。
- `<a>` 元素的直接父元素为 [`<li>`](li.md)，即它们作为列表项的一部分，用于在列表中展示多个导航链接。
- 源文件中部分 `<i>` 标签缺少闭合标签（如第三、四个链接），但浏览器会自动处理并正确渲染。
