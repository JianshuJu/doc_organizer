# <li>

## Overview

`<li>`（List Item）元素用于定义列表中的条目。它必须嵌套在有序列表（`<ol>`）或无序列表（`<ul>`）中使用。在本源文件中，`<li>` 用于展示导航链接条目以及装饰性气泡动画元素。

- **Type**: block-level（块级元素）
- **Category**: text-content（文本内容）
- **Spec**: [HTML Living Standard - li element](https://html.spec.whatwg.org/multipage/grouping-content.html#the-li-element)

## Attributes

| Attribute | Value in Source | Description |
|-----------|----------------|-------------|
| `value` | _(common)_ | 仅在 `<ol>` 中使用，指定当前列表项的序号值 |
| `type` | _(common)_ | 已废弃，用于指定列表项标记样式 |

本源文件中的 `<li>` 元素未使用任何属性。

## Child Elements

| Child Element | Purpose Under `<li>` |
|---------------|----------------------|
| [`<a>`](a.md) | 在列表项中嵌入超链接，指向外部网址 |
| [`<i>`](i.md) | 在 `<a>` 内部使用，以斜体样式展示链接地址文本 |

`<li>` 还可直接包含纯文本内容。在本源文件中，每个导航 `<li>` 包含描述性纯文本（如 "AGou's Blog"）以及一个内嵌 `<a>` 元素。

## Parent Elements

- [`<ul>`](ul.md)

在本源文件中，所有 `<li>` 均作为 [`<ul>`](ul.md) 的子元素出现，分别位于导航链接区域和装饰性气泡背景区域。

## Source Example

```html
<!-- From example/index.html — 导航链接列表项 -->
<li>
    AGou's Blog
    <a href="https://agou-ops.top" target="_blank"><i>https://agou-ops.top</i></a>
</span></span></li>

<li>
    AGou's Docs
    <a href="https://agou-ops.top/beforeWork" target="_blank"><i>https://agou-ops.top/beforeWork</i></a>
</span></span></li>

<li>
    AGou's StudyNote
    <a href="https://agou-ops.top/myStudyNote" target="_blank"><i>https://agou-ops.top/myStudyNote</a>
</span></span></li>

<li>
    Reward PAGE
    <a href="https://agou-ops.top/reward" target="_blank"><i>https://agou-ops.top/reward</a>
</span></span></li>
```

```html
<!-- From example/index.html — 装饰性气泡列表项（共10个，用于 CSS 动画背景） -->
<ul class="bg-bubbles">
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

## Notes

- `<li>` 元素必须作为 [`<ul>`](ul.md) 或 [`<ol>`](ol.md) 的直接子元素使用，不能独立存在。
- 本源文件中展示了 `<li>` 的两种典型用法：一是包含文本与超链接的内容型列表项，二是仅用于配合 CSS 动画的空列表项（`bg-bubbles` 区域）。
- 源文件中部分 `<li>` 内部包含多余的 `</span>` 闭合标签，这可能是历史遗留的标记错误，不影响页面渲染但不推荐。
- 在 HTML5 中，`<li>` 的闭合标签 `</li>` 可以省略（当紧跟下一个 `<li>` 或父元素闭合时），但为了代码可读性，建议始终显式闭合。
